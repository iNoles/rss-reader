# RSS Reader

RSS Reader is a web application built with Vue.js, TypeScript, and Tailwind CSS that enables users to effortlessly follow and read RSS feeds from their favorite websites. The app integrates with a feed API to fetch and display content in a clean, user-friendly interface.

## Features

- Fetch and display RSS feeds from various sources.
- Developed with **Vue 3 Composition API** and **TypeScript** for type-safe, maintainable code.
- Styled with **TailwindCSS** for a utility-first, responsive design.
- Powered by **Vite** for super-fast development and build times.
- Utilizes **Bun.sh** for rapid JavaScript execution and bundling.

## Getting Started

To set up and run this project locally, follow these steps:

### Prerequisites

- [Bun.sh](https://bun.sh/) installed.
- (Optional) Node.js, though **Bun.sh** handles most tasks.

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/iNoles/rss-reader.git
   cd rss-reader
   ```
2. Install dependencies using Bun:

   ```bash
   bun install
   ```

### Available Scripts

- ``bun dev``: Start the development server.
- ``bun build``: Create a production build.
- ``bun preview``: Preview the production build.

## Usage

1. Enter the URL of the RSS feed you want to fetch in the input box.
2. Click on the "Fetch RSS" button.
3. The feed items will be displayed below, showing the title and description of each item.

### Tech Stack

- Vue 3: JavaScript framework for building user interfaces.
- TypeScript: A statically typed superset of JavaScript.
- Vite: Build tool that provides fast development and bundling.
- Bun.sh: A high-speed JavaScript runtime.
- TailwindCSS: Utility-first CSS framework for responsive design.

### Contributing

Contributions are welcome! Here's how you can help:
1. Fork the repository.
2. Create your feature branch (``git checkout -b feature/YourFeature``).
3. Commit your changes (``git commit -m 'Add YourFeature'``).
4. Push to the branch (``git push origin feature/YourFeature``).
5. Open a pull request.
