# Archived technical blog

My personal website is now [fgfm.dev](https://fgfm.dev/).

The original Quarto source is kept here, including
[`posts/laptop-selection.qmd`](posts/laptop-selection.qmd).
It is no longer published. Only [`docs/`](docs/) contains the redirect site,
including a fallback for old blog URLs.

After merging this change, set **Settings → Pages → Deploy from a branch**
to **`main` / `/docs`**. This replaces the old `gh-pages` deployment and keeps
the blog source out of the published site. Project sites in other repositories
keep their own publishing settings.


_powered by [Quarto](https://github.com/quarto-dev/quarto-cli)_



## Setup

### Prerequisites

[Quarto](https://quarto.org/docs/get-started/) & [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) are required to run this blog.

### Installation

Now you only need to clone the repository:

```shell
git clone https://github.com/frgfm/frgfm.github.io.git
cd frgfm.github.io/
```


## Modifying the blog

### Which files should I modify

The project is organized in a rather simple way:
- [`./assets`](assets/): where general asset files are stored
- [`./projects`](projects/): the projects of the author
- [`./posts`](posts/): the posts


### Render your post

In order to preview your changes, run the following command:

```shell
quarto preview
```
Every change operated while the preview is running will refresh the website content.


## License

Distributed under the Apache 2.0 License. See [`LICENSE`](LICENSE) for more information.
