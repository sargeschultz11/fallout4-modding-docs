
---
title: Contributing
layout: default
---

# Contributing to Fallout 4 Modding Documentation Hub

Thank you for considering contributing to this project! This guide will walk you through the process of forking the repo, submitting a pull request, adding content to the site, and modifying the navigation.

---

## 1. Fork the Repository

To contribute, you first need to **fork** the repository and clone it to your local machine:

1. Visit the GitHub repository: [Fallout 4 Modding Docs](https://github.com/sargeschultz11/fallout4-modding-docs).
2. Click the **Fork** button in the top-right corner to create your own copy of the repository.
3. Clone the forked repository to your local machine:

   ```bash
   git clone https://github.com/<your-username>/fallout4-modding-docs.git
   cd fallout4-modding-docs
   ```

4. Set the original repository as the upstream source to keep your fork updated:

   ```bash
   git remote add upstream https://github.com/sargeschultz11/fallout4-modding-docs.git
   ```

---

## 2. Create a New Branch

Always work on a new branch for your contributions to keep things organized:

```bash
git checkout -b my-new-feature
```

Replace `my-new-feature` with a meaningful branch name, like `add-new-page` or `fix-typos`.

---

## 3. Make Your Changes and Submit a Pull Request

Once your changes are ready, follow these steps to submit a Pull Request (PR):

1. Stage and commit your changes:

   ```bash
   git add .
   git commit -m "Add [your feature or fix]"
   ```

2. Push your changes to your fork:

   ```bash
   git push origin my-new-feature
   ```

3. Open a Pull Request on GitHub:
   - Go to your forked repository.
   - Click **"Compare & Pull Request"**.
   - Provide a description of your changes.
   - Submit the PR for review!

---

## 4. Adding a New Page

To add a new page to the site:

1. Create a new Markdown file in the root directory or the `docs/` folder:

   ```bash
   touch new-page.md
   ```

2. Add the following front matter at the top of the file:

   ```yaml
   ---
   title: [Your Page Title]
   layout: default
   ---
   ```

3. Add your content in Markdown below the front matter.

4. **Link to the new page** by updating `index.md` or any other page:

   ```markdown
   [New Page](./new-page.md)
   ```

---

## 5. Modifying Navigation Links

To add the new page to the site's navigation menu:

1. Open the `_config.yml` file in the repository.
2. Add a new entry under the `nav` section:

   ```yaml
   nav:
     - title: New Page
       url: /new-page
   ```

3. Save the file and commit your changes.

This will add a link to your new page in the navigation menu.

---

## 6. Testing Your Changes Locally

If you want to preview your changes before submitting a PR:

1. Install Jekyll and its dependencies (you need Ruby installed):

   ```bash
   gem install bundler jekyll
   bundle install
   ```

2. Serve the site locally:

   ```bash
   bundle exec jekyll serve
   ```

3. Open `http://localhost:4000` in your browser to see the site.

---

## 7. Keeping Your Fork Updated

To keep your forked repository up to date with the main repository:

1. Fetch the latest changes from the upstream repository:

   ```bash
   git fetch upstream
   ```

2. Merge the changes into your branch:

   ```bash
   git merge upstream/main
   ```

---

## Final Notes

Thank you for helping improve this documentation hub! Your contributions make the Fallout 4 modding community even better.

If you have any questions or need assistance, feel free to open an issue or reach out in your Pull Request.

