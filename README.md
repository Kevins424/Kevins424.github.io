# Kevin's GitHub Pages Site

This repository contains the source for my personal website powered by [GitHub Pages](https://pages.github.com/) and [Jekyll](https://jekyllrb.com/).

## Structure

- **`index.md`** – Home page that lists recent posts.
- **`_posts/`** – Folder for blog posts written in Markdown.
- **`assets/`** – Optional folder to store images or other media.
- **`_config.yml`** – Site configuration file.

## Writing a Post

1. Create a new Markdown file in the `_posts/` directory using the format `YYYY-MM-DD-title.md`.
2. Add Jekyll front matter at the top of the file:
   ```markdown
   ---
   layout: post
   title: "My Title"
   ---
   ```
3. Write your content below the front matter using regular Markdown.
4. Commit the file to Git and push to GitHub. GitHub Pages will automatically update your site.

## Adding Images

Place images in the `assets/` folder (create it if it doesn't exist). Reference them in your Markdown posts like so:

```markdown
![Alt text](/assets/my-image.png)
```

---

Edit this README with additional instructions as needed.
