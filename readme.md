## Alloy Hugo Demo

This is a prototype for migrating the current [alloytools](http://alloytools.org/) website to [hugo](https://gohugo.io/).  You can see the current prototype website [here](https://hwayne.github.io/alloy-hugo-demo/).

### Why the migration

Alloytools is currently on [jekyll](https://jekyllrb.com/). Jekyll is very difficult to set up, especially if you're not on Linux. Hugo, by contrast, comes in precompiled binaries per OS. All you need to do is download the appropriate binary and you're good to go. This way you can run the site locally and test for changes

The migration blocker, as discussed in the (May?) Alloyboard meeting, is that Jekyll natively integrates with Github pages, making it easy to deploy. To address this, we set up a [github action](https://github.com/hwayne/alloy-hugo-demo/actions) on the official repo. After every merge to master, the action will build the site and put the html files in the [`gh-pages`](https://github.com/hwayne/alloy-hugo-demo/tree/gh-pages) branch. Build times are typically less than 30 seconds.

## Setup

### Download the appropiate binary

Download the appropriate **hugo extended** [for your OS](https://github.com/gohugoio/hugo/releases). Currently, this is `hugo_extended_0.87.0`.

(We need hugo extended because we ported over SASS CSS files from the old site)

### Set up the repo

First clone the repo:

```bash
git clone https://github.com/hwayne/alloy-hugo-demo.git
```

Then, while in the repo root folder, download [the ananke theme](https://themes.gohugo.io/themes/):


```bash
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
git submodule init
git submodule update
```

### Run the repo

You can create a local instance of the site with 

```bash
./hugo_binary serve
```

It will automatically update whenever you save a change to a file.  If you just want to build the site without running a local dev server, just do

```bash
./hugo_binary
```
https://github.com/peaceiris/actions-hugo

## Contributing

### TODO 

* Explain layout of hugo folder
* Explain drafts
* Explain shortcodes
