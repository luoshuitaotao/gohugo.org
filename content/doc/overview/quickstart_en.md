---
date: 2013-07-01
lastmod: 2016-01-09
linktitle: Quickstart
menu:
  main:
    parent: getting started
next: /doc/overview/installing
prev: /doc/overview/introduction
title: Hugo Quickstart Guide
weight: 10
---

> _Note: This quickstart depends on features introduced in Hugo v0.11.  If you have an earlier version of Hugo, you will need to [upgrade](/doc/overview/installing/) before proceeding._

{{% youtube w7Ft2ymGmfc %}}

## Step 1. Install Hugo

Go to [Hugo Releases](https://github.com/spf13/hugo/releases) and download the
appropriate version for your OS and architecture.

Save the main executable as `hugo` (or `hugo.exe` on Windows) somewhere in your `PATH` as we will be using it in the next step.

More complete instructions are available at [Installing Hugo](/doc/overview/installing/).

## Step 2. Have Hugo Create a site for you

Hugo has the ability to create a skeleton site:

{{< nohighlight >}}$ hugo new site <i>path/to/site</i>
{{< /nohighlight >}}

For the rest of the operations, we will be executing all commands from within the site directory.

{{< nohighlight >}}$ cd <i>path/to/site</i>
{{< /nohighlight >}}

The new site will have the following structure

{{< nohighlight >}}  ▸ archetypes/
  ▸ content/
  ▸ data/
  ▸ layouts/
  ▸ static/
    config.toml
{{< /nohighlight >}}

Currently the site doesn’t have any content, nor is it configured.

## Step 3. Create Some Content

> If you used a different blogging platform such as Jekyll, Ghost or Wordpress and you
want convert your content, take a look at this list of [ migration tools]({{< relref "doc/tools/index.md#migration-tools" >}}).

Hugo also has the ability to create a skeleton content page:

    $ hugo new about.md

A new file is now created in `content/` with the following contents:

```
+++
date = "2015-01-08T08:36:54-07:00"
draft = true
title = "about"

+++

```

Notice the date is automatically set to the moment you created the content.

Place some content in Markdown format below the `+++` in this file.
For example:

```markdown
## A headline

Some Content
```

For fun, let’s create another piece of content and place some Markdown in it as well.

    $ hugo new post/first.md

The new file is located at `content/post/first.md`

We still lack any templates to tell us how to display the content.

## Step 4. Install some themes

Hugo has rich theme support and a growing set of themes to choose from.
To install the latest version of all of the available Hugo themes, simply clone the entire **hugoThemes** repository from within your working directory:

```bash
$ git clone --depth 1 --recursive https://github.com/spf13/hugoThemes.git themes
```

## Step 5. Run Hugo

Hugo contains its own high-performance web server. Simply run `hugo
server` and Hugo will find an available port and run a server with
your content:

    $ hugo server --theme=hyde --buildDrafts
    2 of 2 drafts rendered
    0 future content
    2 pages created
    0 paginator pages created
    0 tags created
    0 categories created
    in 15 ms
    Watching for changes in /home/user/exampleHugoSite/{data,content,layouts,static,themes}
    Serving pages from memory
    Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)
    Press Ctrl+C to stop

We specified two options here:

 * `--theme` to pick which theme;
 * `--buildDrafts` because we want to display our content, both set to draft status.

To learn about what other options hugo has, run:

    $ hugo help

To learn about the server options:

    $ hugo help server

## Step 6. Edit Content

Not only can Hugo run a server, but it can also watch your files for
changes and automatically rebuild your site. Hugo will then
communicate with your browser and automatically reload any open page.
This even works in mobile browsers.

Stop the Hugo process by hitting <kbd>Ctrl</kbd>+<kbd>C</kbd>. Then run the following:

    $ hugo server --theme=hyde --buildDrafts
    2 pages created
    0 tags created
    0 categories created
    in 5 ms
    Watching for changes in exampleHugoSite/content
    Serving pages from exampleHugoSite/public
    Web Server is available at http://localhost:1313
    Press Ctrl+C to stop

Open your [favorite editor](http://vim.spf13.com/), edit and save your content, and watch as Hugo rebuilds and reloads automatically.

It’s especially productive to leave a browser open on a second monitor
and just glance at it whenever you save. You don’t even need to tab to
your browser. Hugo is so fast that the new site will be there before
you can look at the browser in most cases.

Change and save this file. Notice what happened in your terminal:

    Change detected, rebuilding site
    2015-11-27 15:13 +0100
    2 of 2 drafts rendered
    0 future content
    2 pages created
    0 paginator pages created
    0 tags created
    0 categories created
    in 11 ms

## Step 7. Have fun

The best way to learn something is to play with it.

Things to try:

 * Add a [new content file](/doc/content/organization/)
 * Create a [new section](/doc/content/sections/)
 * Modify [a template](/layout/templates/)
 * Create content with [TOML front matter](/doc/content/front-matter/)
 * Define your own field in [front matter](/doc/content/front-matter/)
 * Display that [field in the template](/layout/variables/)
 * Create a [new content type](/doc/content/types/)
