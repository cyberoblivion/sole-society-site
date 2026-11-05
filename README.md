# Sole Society: Shoe Cleaning

Open-source Jekyll site for **Sole Society**, a hand-done sneaker cleaning shop.
Hosted on GitHub Pages: https://solesociety.cyberoblivion.com/

## Run locally

```sh
bundle install
bundle exec jekyll serve --livereload
# open http://localhost:4000/
```

## Add a before & after post

1. Resize and strip metadata (removes phone GPS location) from photos:

   ```sh
   mkdir -p assets/images/posts/my-post
   magick in.jpg -auto-orient -strip -resize 1600x1600\> -quality 82 assets/images/posts/my-post/out.jpg
   ```

2. Create `_posts/YYYY-MM-DD-my-post.md`:

   ```markdown
   ---
   title: "Pair name"
   cover: /assets/images/posts/my-post/out.jpg
   excerpt: "One-line summary for the card."
   ---

   {% include figure.html src="/assets/images/posts/my-post/out.jpg" alt="..." caption="Before (left) vs after (right)" %}
   ```

   Wrap several figures in `<div class="gallery"> ... </div>` for a grid.

3. Commit and push to `master`. The GitHub Action builds and deploys.

## Settings

Edit `_config.yml` and set `email`, `instagram`, `tiktok` to show them in the footer.
If you move to a custom domain, set `url` to it, `baseurl` to `""`, and add a `CNAME` file.

## Deploy setup (one time)

Repo → Settings → Pages → Source: **GitHub Actions**.

## License

Code: MIT. Brand name, logo, and photos: all rights reserved. See [LICENSE](LICENSE).
