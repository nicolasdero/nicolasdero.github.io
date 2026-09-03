# nicolasdero.github.io

This repository contains the source code for my personal website. While this is not a GitHub template *per se*, feel free to use, adapt, and share the source code anywhere you like.

## General information

The initial design is based on the [minimal-light](https://github.com/yaoyao-liu/minimal-light) template by [yaoyao-liu](https://github.com/yaoyao-liu/), which itself derives from the [minimal](https://github.com/orderedlist/minimal) theme. I have simplified and customized the layout to my own taste, including adding the necessary structure for a bilingual website (in this case, English and French). For more information on the underlying backbone, please refer to the documentation of the original templates.

The website is aimed at being simple and elegant for presenting oneself, while also being versatile and supporting mobile displays. Judge for yourself here: [nicolasdero.com](https://nicolasdero.com).

 The repository has the following structure:

```text
.
├── _data                    # YAML files with structured site data
│   ├── navigation.yml       # Configures navigation menu items, titles, target URLs, and alignment
│   ├── publications.yml     # Data for publications
│   ├── publications_fr.yml  # " in French
│   ├── softwares.yml        # Data for software
│   └── softwares_fr.yml     # " in French
├── _includes                # Markdown snippets and partials for each section
│   ├── CV.md                # Content snippets for CV
│   ├── CV_fr.md             # " in French
│   ├── mountains.md         # Content snippets for mountain activities 
│   ├── mountains_fr.md      # " in French
│   ├── navigation.md        # Content snippets for navigating across the website
│   ├── publications.md      # Content snippets for publications
│   ├── publications_fr.md   # " in French
│   ├── softwares.md         # Content snippets for softwares 
│   └── softwares_fr.md      # " in French
├── _layouts                 # HTML templates for page layouts
│   ├── default.html         # Base HTML layout used across the site
│   └── homepage.html        # Custom layout for the homepage
├── assets                   # Static web assets
│   ├── css                  # CSS stylesheets
│   ├── documents            # PDF documents
│   ├── GPX                  # GPX files for hikes
│   ├── img                  # Images and icon
│   └── js                   # JavaScript code
├── fr                       # Directory containing wrapper files for French localized pages
├── _config.yml              # Main configuration file for Jekyll
├── Gemfile                  # Defines Ruby gem dependencies required by Jekyll
├── Gemfile.lock             # Pins exact versions of Ruby dependencies
├── index.md                 # Root entry point that generates the homepage
├── CV.md                    # Short page wrapper for CV section
├── publications.md          # Short page wrapper for publications section
├── softwares.md             # Short page wrapper for softwares section
├── mountains.md             # Short page wrapper for mountains section
├── LICENSE
└── README.md
```

The [`_data`](./_data/) folder contains structured data files read by Jekyll. This data is made available to Liquid templates to dynamically generate the site's HTML pages. The [`_includes`](./_includes/) folder contains the Markdown files and reusable snippets that structure each section of the website. The [`_layouts`](./_layouts/) folder provides the HTML templates for the site's layout and customization. Finally, [`assets`](./assets/) contains CSS files for styling, JavaScript code, and other media or documents (PNG, PDF, SVG, etc.).

See below for an explanation of how to interact with the repository to create your website version.

## Installation

First, clone the repository using the method of your choice. For example, using HTTPS:

    git clone https://github.com/nicolasdero/nicolasdero.github.io.git
    cd nicolasdero.github.io

Then, install [Ruby](https://www.ruby-lang.org/fr/), [Jekyll](https://jekyllrb.com/) and [Bundler](https://bundler.io/). In a few words, Ruby is a widely used programming language for building modern applications and services, Jekyll (written in Ruby) is a static site generator, and Bundler is a dependency manager for Ruby. Please refer to the official documentation of each for installation instructions for your specific operating system. Once the setup is installed, run the site locally using the command

    bundle exec jekyll serve

This should open a server address of the form http://0.0.0.0:4000 that you can open in any browser. If modifications are made to the code, refreshing the page is sufficient to see the corresponding changes on the site. 

## Interacting with the code

If you want to modify the site, follow these steps. 

First, create a short page wrapper that is stored at the top-level of the directory containing the value of basic Jekyll variables. You have two options from then on: either the HTML code is written in that file (as it is for [`index.md`](./index.md), for example), or the HTML is written in one of the files in the [`_includes`](./_includes/) folder and then imported in the corresponding page wrapper. 

The only exception to this are the [Publications](https://nicolasdero.github.io/publications) and [Software](https://nicolasdero.github.io/softwares) sections, which follow a specific template with variables that have to be assigned corresponding values in YAML files stored in [`_data`](./_data). 

To change the overall layout of the site, you can modify the HTML code of the [`homepage.html`](./_layouts/homepage.html) for the homepage and [`default.html`](./_layouts/default.html) for the rest of the site. 

For color and stylistic customization, the corresponding CSS files have to be modified. They can be found in the [`css`](./assets/css/) folder, which contains four files: one for the style of the navigation bar, [`nav.css`](./assets/css/nav.css), one for the overall style of the site, [`style.css`](./assets/css/style.css), and two for the specific style of the [Publications](https://nicolasdero.github.io/publications) and [Software](https://nicolasdero.github.io/softwares) pages.

## Deployment

The website is designed to be hosted using GitHub Pages. The `main` branch contains the Jekyll source files, which GitHub Pages builds and serves automatically.

For local development, see the [Installation](#installation) section above.

## License

This project is distributed under the [MIT License](./LICENSE).
