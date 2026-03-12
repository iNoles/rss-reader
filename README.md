# RSS Reader

![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=for-the-badge)
![Vue](https://img.shields.io/badge/Vue_3-35495E?logo=vuedotjs&logoColor=4FC08D&style=for-the-badge)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white&style=for-the-badge)
![Vite](https://img.shields.io/badge/Vite-646CFF?logo=vite&logoColor=white&style=for-the-badge)
![pnpm](https://img.shields.io/badge/pnpm-F69220?logo=pnpm&logoColor=white&style=for-the-badge)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-38B2AC?logo=tailwindcss&logoColor=white&style=for-the-badge)

A lightweight RSS Reader built with Vue 3, TypeScript, TailwindCSS, and Vite, designed to make following your favorite websites effortless. It integrates with a feed API to fetch and display RSS content in a clean, responsive interface.

## Features

- Fetch and display RSS feeds from any valid source.
- Built with the Vue 3 Composition API for clarity and maintainability.
- Fully typed with TypeScript.
- Styled using TailwindCSS for fast, utility‑first UI development.
- Powered by Vite for instant dev server startup and optimized builds.
- Uses pnpm for fast, disk‑efficient dependency management.

## Getting Started

To set up and run this project locally, follow these steps:

### Prerequisites

- pnpm installed
- Node.js installed

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/iNoles/rss-reader.git
   cd rss-reader
   ```
2. Install dependencies using Bun:

   ```bash
   pnpm install
   ```

### Available Scripts

- ``pnpm dev``: Start the development server.
- ``pnpm build``: Create a production build.
- ``pnpm preview``: Preview the production build.

## Usage

1. Enter the URL of the RSS feed you want to fetch in the input box.
2. Click on the "Fetch RSS" button.
3. The feed items will be displayed below, showing the title and description of each item.

### Tech Stack

- Vue 3 — UI framework
- TypeScript — Static typing for safer code
- Vite — Fast dev/build tooling
- pnpm — Efficient package manager
- TailwindCSS — Utility-first styling

### Contributing

Contributions are welcome! Here's how you can help:
1. Fork the repository.
2. Create your feature branch (``git checkout -b feature/YourFeature``).
3. Commit your changes (``git commit -m 'Add YourFeature'``).
4. Push to the branch (``git push origin feature/YourFeature``).
5. Open a pull request.
