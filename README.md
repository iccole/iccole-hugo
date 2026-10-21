# ic-dev

My personal site. It's a plain static page built with [Hugo](https://gohugo.io/) and the [Bear Blog theme](https://github.com/janraasch/hugo-bearblog), hosted on GitHub Pages.

Live at: https://iccole.github.io/iccole-hugo/

## why this and not something fancier

I could have asked an AI agent to build me a slick JavaScript site with animations, a framework, and a build pipeline. It would have taken an afternoon. That's kind of the point.

When building almost anything is cheap, the hard part isn't building anymore. The hard part is deciding what's worth building, and how. So I made a choice on purpose:

- **It loads instantly.** It's just HTML and a little CSS. No JavaScript bundle to download, no spinner, no layout jumping around.
- **It works everywhere.** Slow phone, bad connection, old browser, screen reader, JavaScript turned off. It still works.
- **There's almost nothing to maintain.** No dependencies to update, no security patches for packages I don't use, nothing that breaks in a year because a library changed.
- **It fits the job.** This site is a few paragraphs and a resume. It doesn't need to be an app.
- **It's easy to change.** Content is a Markdown file. Edit it, push, done.

A heavy site isn't wrong. I've built big dynamic apps and that's the right tool when the problem calls for it. This problem doesn't. Picking the simple thing when the simple thing is enough is a skill, and it matters more now that "just build it" costs almost nothing.

## how it works

- `content/_index.md` is the home page.
- `hugo.toml` is the site config.
- `static/` holds the favicon, share image, and resume PDF.
- `layouts/partials/custom_head.html` has a small dark mode color tweak.
- The theme lives in `themes/hugo-bearblog` as a git submodule.
- Pushing to `main` runs `.github/workflows/hugo.yaml`, which builds the site and deploys it to GitHub Pages.

## run it locally

You need [Hugo](https://gohugo.io/installation/) installed.

```sh
git clone --recurse-submodules https://github.com/iccole/iccole-hugo.git
cd iccole-hugo
hugo server
```

Then open http://localhost:1313/iccole-hugo/.

If you already cloned without submodules, run `git submodule update --init` first.
