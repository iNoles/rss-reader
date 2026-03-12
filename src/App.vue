<template>
  <div
    class="
      min-h-screen
      flex
      justify-center
      p-6
      bg-gray-100
      dark:bg-gray-900
      text-black
      dark:text-white
      transition
    "
  >
    <div
      class="
        w-full
        max-w-2xl
        rounded-xl
        p-6
        shadow-lg
        bg-white
        dark:bg-gray-800
      "
    >
      <h1 class="text-3xl font-bold mb-6 text-center">
        RSS Reader
      </h1>

      <form @submit.prevent="fetchRSS" class="space-y-3">

        <input
          v-model="rssUrl"
          placeholder="Enter RSS feed URL"
          class="
            border
            rounded-lg
            p-2
            w-full
            bg-transparent
            focus:outline-none
            focus:ring-2
            focus:ring-blue-600
          "
        />

        <button
          type="submit"
          class="
            w-full
            bg-blue-700
            hover:bg-blue-800
            text-white
            font-semibold
            p-2
            rounded-lg
          "
        >
          Fetch RSS
        </button>

      </form>

      <div v-if="loading" class="mt-4 text-center">
        Loading...
      </div>

      <div v-if="error" class="mt-4 text-red-500 text-center">
        {{ error }}
      </div>

      <div v-if="feed" class="mt-6">

        <h2 class="text-xl font-semibold mb-4">
          {{ feed.title }}
        </h2>

        <ul class="space-y-4">

          <li
            v-for="item in feed.items"
            :key="item.link"
            class="
              border
              rounded-lg
              p-4
              hover:bg-gray-100
              dark:hover:bg-gray-700
              border-gray-200
              dark:border-gray-700
              transition
            "
          >

            <a
              :href="item.link"
              target="_blank"
              class="text-blue-600 dark:text-blue-400 font-semibold hover:underline"
            >
              {{ item.title }}
            </a>

            <div
              v-html="truncate(item.description)"
              class="text-sm mt-2 opacity-80"
            />

          </li>

        </ul>

      </div>

    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'

interface FeedItem {
  title: string
  link: string
  description: string
}

interface Feed {
  title: string
  items: FeedItem[]
}

export default defineComponent({
  name: 'App',

  setup() {
    const rssUrl = ref<string>('')
    const feed = ref<Feed | null>(null)
    const loading = ref(false)
    const error = ref<string | null>(null)

    const fetchRSS = async () => {

      if (!rssUrl.value) return

      loading.value = true
      error.value = null
      feed.value = null

      try {

        const response = await fetch(
          `https://api.rss2json.com/v1/api.json?rss_url=${rssUrl.value}`
        )

        const data = await response.json()

        if (data.status !== "ok") {
          throw new Error("Invalid RSS feed")
        }

        feed.value = {
          title: data.feed.title,
          items: data.items.map((item: any) => ({
            title: item.title,
            link: item.link,
            description: item.description
          }))
        }

      } catch (err) {

        error.value = "Failed to load RSS feed"

      } finally {

        loading.value = false

      }

    }

    const truncate = (html: string) => {
      const text = html.replace(/<[^>]*>?/gm, '')
      return text.length > 200
        ? text.substring(0, 200) + "..."
        : text
    }

    return {
      rssUrl,
      feed,
      loading,
      error,
      fetchRSS,
      truncate
    }

  }

})
</script>