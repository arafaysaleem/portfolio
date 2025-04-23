# Academic Portfolio

A personal portfolio website showcasing academic projects and research from my Master's in Computer Science program.

## Features

- Clean, developer-friendly design
- Expandable course sections
- Support for various media types (YouTube videos, GitHub repositories, research papers)
- Responsive layout

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (version 16 or later)
- npm or yarn

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/portfolio.git
   cd portfolio
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm run dev
   ```

4. Open your browser and navigate to `http://localhost:4321` to see the website.

## Customization

1. Update personal information in `src/components/Header.astro`
2. Modify course data in `src/data/courses.js`
3. Customize styling as needed in individual component files

## Deployment

### GitHub Pages

1. Update the `astro.config.mjs` file with your GitHub username:
   ```javascript
   export default defineConfig({
     site: 'https://yourusername.github.io',
     base: '/portfolio',
   });
   ```

2. Build the website:
   ```bash
   npm run build
   ```

3. Deploy to GitHub Pages:
   - Create a new repository on GitHub named `portfolio`
   - Push your code to this repository
   - Set up GitHub Pages in the repository settings to deploy from the `gh-pages` branch

4. Alternatively, you can use GitHub Actions for automatic deployment. Create a file `.github/workflows/deploy.yml` with the following content:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [main]

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v3

      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: 18

      - name: Install dependencies
        run: npm install

      - name: Build
        run: npm run build

      - name: Deploy
        uses: JamesIves/github-pages-deploy-action@v4
        with:
          folder: dist
          branch: gh-pages
```

### Other Hosting Options

The built website is static, so it can be deployed to any static site hosting service such as:
- Netlify
- Vercel
- Cloudflare Pages
- AWS S3

## License

This project is licensed under the MIT License - see the LICENSE file for details.