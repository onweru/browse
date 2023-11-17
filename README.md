# Browse

**Browse** is a responsive [Hugo](https://gohugo.io/) Hugo theme. It's a fork of the Hugo [Mainroad theme](https://github.com/Vimux/Mainroad).

**[Demo](https://browse.neuralvibes.com/)** • **[Docs](https://browse.neuralvibes.com/docs/)**

![screenshot](https://raw.githubusercontent.com/onweru/browse/master/images/screenshot.png)

**Features:**

+ Main & secondary menus
+ Widgetized sidebar
+ Configurable theme settings (sidebar position, author box, post navigation, highlight color) via `hugo.toml`
+ Custom Google Fonts support, MathJax, Table of Contents, SVG icons and much more…
+ Dark Mode

## Installation

*Before starting, please be sure that you have
[installed Hugo](https://gohugo.io/getting-started/quick-start/#step-1-install-hugo) and
[created a new site](https://gohugo.io/getting-started/quick-start/#step-2-create-a-new-site). After that, you are ready
to install **Browse**.*

You could go with the options right below.

### Option 1 (my favorite)

This option enables you to load browse theme as a hugo module. First things first, ensure you have `go` binary [installed on your machine](https://golang.org/doc/install).

```shell
$ git clone https://github.com/onweru/browse/
cd browse/exampleSite/
hugo server
```

To pull in theme updates, run `hugo mod get -u ./...` from the theme folder. If unsure, [learn how to update hugo modules](https://gohugo.io/hugo-modules/use-modules/#update-modules)

{{< tip "warning" >}}
The exampleSite uses the theme as a hugo module by default.

If you choose __Option 2__ or __Option 3__ below, ensure you edit [these lines in the hugo.toml file](https://github.com/onweru/browse/blob/b3e30e0816621223224897edc45eeeabd0d9cd16/exampleSite/hugo.toml#L4-L7) as advised on the comments. Else, you will not be able to pull theme updates.
{{< /tip >}}

### Option 2 (recommended)

Generate a new Hugo site and add this theme as a Git submodule inside your themes folder:

```bash
hugo new site yourSiteName
cd yourSiteName
git init
git submodule add https://github.com/onweru/browse/ themes/browse
cp -a themes/browse/exampleSite/* .
```

Then run

```bash
hugo server
```

Hurray!

### Option 3 (Great for testing quickly)

You can run your site directly from the `exampleSite`. To do so, use the following commands:

```bash
git clone https://github.com/onweru/browse/
cd browse/exampleSite/
hugo server --themesDir ../..
```

{{< tip >}}
Although, option 3 is great for quick testing, it is somewhat problematic when you want to update your theme. You would need to be careful not to overwrite your changes.
{{< /tip >}}

Once set, jump over to the [hugo.toml](https://github.com/onweru/browse/blob/afdf1cd76408aeac11547a6abd51bdc5138a295f/exampleSite/hugo.toml#L4-L7) file and start configuring your site.

## Configuration
Please see the config files inside `exampleSite/config/_default`

#### Override font-family sets

```toml
fontFamilyPrimary = "'Open Sans', Helvetica, Arial, sans-serif"
fontFamilySecondary = "SFMono-Regular, Menlo, Monaco, Consolas, 'Liberation Mono', 'Courier New', monospace"
```

```toml
[logo]
image = "img/placeholder.png" # Logo image. Path relative to "static"
title = "Browse" # Logo title, otherwise will use site title
subtitle = "Just another site" # Logo subtitle

[thumbnail]
visibility = ["list", "post"] # Control thumbnail visibility
```

```toml
[sidebar]
home = "right" # Configure layout for home page
list = "left"  # Configure layout for list pages
single = false # Configure layout for single pages
# Enable widgets in given order
widgets = ["search", "recent", "categories", "taglist", "social", "languages"]
```

```toml
[widgets]
recent_num = 5 # Set the number of articles in the "Recent articles" widget
categories_counter = false # Enable counter for each category in "Categories" widget
tags_counter = false # Enable counter for each tag in "Tags" widget
```

#### Enable parts of social widget

```
[widgets.social]
facebook = "username"
twitter = "username"
instagram = "username"
linkedin = "username"
telegram = "username"
github = "username"
gitlab = "username"
bitbucket = "username"
email = "example@example.com"
```

####  Custom social links

```toml
[[widgets.social.custom]]
title = "Youtube"
url = "https://youtube.com/user/username"
icon = "youtube.svg" # Optional. Path relative to "layouts/partials"
rel = "noopener noreferrer" # Set to false to remove the rel attribute

[[widgets.social.custom]]
title = "My Home Page"
url = "https://example.com"

[widgets.search]
url = "https://google.com/search"
[widgets.search.input]
  name = "sitesearch"
  pre = ""
```

**Do not copy example config as-is**. Use only those parameters that you need.

For more information about all available standard configuration settings, please read
[All Hugo Configuration Settings](https://gohugo.io/getting-started/configuration/#all-configuration-settings).

### Front Matter example

```yaml
---
# Common-Defined params
title: "Example article title"
date: "2017-08-21"
description: "Example article description"
categories:
  - "Category 1"
  - "Category 2"
tags:
  - "Test"
  - "Another test"
menu: main # Optional, add page to a menu. Options: main, side, footer

# Theme-Defined params
thumbnail: "img/placeholder.png" # Thumbnail image
lead: "Example lead - highlighted near the title" # Lead text
comments: false # Enable Disqus comments for specific page
authorbox: true # Enable authorbox for specific page
pager: true # Enable pager navigation (prev/next) for specific page
toc: true # Enable Table of Contents for specific page
mathjax: true # Enable MathJax for specific page
sidebar: "right" # Enable sidebar (on the right side) per page
widgets: # Enable sidebar widgets in given order per page
  - "search"
  - "recent"
  - "taglist"
---
```

For more information about all available standard front matter variables, please read
[Hugo Front Matter](https://gohugo.io/content-management/front-matter).

### Matomo site analytics

If you prefer using Matomo Analytics, configure the `matomo_analytics` global parameters in your site with the following.

`enable` To enable matomo analytics change to `true`.

`websiteDomain` Set the domain name of your website, in most cases same as your base URL this is required.

`matomoDomain`   Set to Matomo domain

`matomoSiteID`  Default is set to 1, change this to the siteid being tracked

## Contributing

Have you found a bug or got an idea for a new feature? Feel free to use the
[issue tracker](https://github.com/onweru/browse/issues) to let me know. Or make directly a
[pull request](https://github.com/onweru/browse/pulls), but please respect the following
[contributing guide](https://github.com/onweru/browse/blob/master/CONTRIBUTING.md).

## License

This theme is released under the [GPLv2 license](https://github.com/onweru/browse/blob/master/LICENSE.md).
