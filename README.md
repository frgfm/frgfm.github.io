![Build status](https://github.com/frgfm/frgfm.github.io/workflows/build/badge.svg) 
![Deploy status](https://github.com/frgfm/frgfm.github.io/workflows/GH-Pages%20Status/badge.svg) 

# Technical blog


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
