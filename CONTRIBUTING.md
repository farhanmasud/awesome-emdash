# Contributing to Awesome EmDash

Thank you for your interest in contributing to **Awesome EmDash**! We welcome all contributions that help developers, editors, and creators explore and build with the EmDash ecosystem.

Please take a few moments to review these guidelines before submitting a pull request.

---

## Guidelines for Inclusion

To maintain high quality across this list, resources should meet the following criteria:

### General Rules
1. **Relevance**: Items must be specifically relevant to EmDash CMS or directly beneficial when building an EmDash + Astro site.
2. **Quality & Maintenance**: Repositories should have a clear README, installation instructions, and an open-source license. Deprecated or broken projects will be removed.
3. **Format Consistency**: Follow the standardized markdown link format:
   ```markdown
   - [Item Name](https://github.com/user/repo) — Concise, third-person description highlighting key capabilities.
   ```
4. **Alphabetical / Categorical Order**: Place additions in the most appropriate section in alphabetical order (or under the appropriate subcategory).

### For Plugins
- **Sandboxed Plugins**: Provide links to the GitHub repository and mention if it is published on the AT Protocol registry or npm.
- **Native Plugins**: Clearly state the extension points used (e.g. React admin widgets, Portable Text components, custom hooks).
- Ensure required capability permissions are listed if applicable.

### For Starters & Themes
- The template must be compatible with EmDash 1.0+.
- Specify whether the starter is configured for **Cloudflare** (D1/R2) or **Node.js** (SQLite/local disk).
- A live demo link is strongly encouraged!

### For Astro Integrations
- Since EmDash is an Astro integration, generic Astro plugins should only be added if they solve a common, practical requirement for EmDash-powered sites (e.g., UI islands, SEO, search, styling, or sitemaps).

---

## How to Submit a Pull Request

1. **Fork** this repository.
2. **Create a branch** for your change:
   ```bash
   git checkout -b add-my-awesome-resource
   ```
3. **Edit `README.md`**:
   - Add your resource to the relevant section.
   - Ensure markdown formatting and capitalization adhere to existing entries.
4. **Commit** your change with a concise message:
   ```bash
   git commit -m "Add [Resource Name] to [Section Name]"
   ```
5. **Push** to your fork and submit a **Pull Request**.
6. In your PR description, briefly explain what the resource does and why it belongs in the list.

Thank you for helping make the EmDash community awesome!
