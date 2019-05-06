# Enrichment Analysis workshop base

This is the source for the _Enrichment Analysis workshop_ website.
 
# Quickstart

```bash
git clone --recurse-submodules https://github.com/MonashBioinformaticsPlatform/enrichment_analysis_workshop
cd enrichment_analysis_workshop
# For hugo v0.55, currently used version
brew install https://raw.githubusercontent.com/Homebrew/homebrew-core/b1e187384baf6b50960ceed7d0964c151d14eada/Formula/hugo.rb

# brew install hugo
# sudo apt-get install hugo

hugo server
```

To update the site:

* Edit the Markdown in `content` (and possibly files in `static` or `config.toml`)
* Check that the site builds and looks correct by locally running `hugo server`.
* `git commit` your changes and `git push`.

Deployment to the live site at [monashbioinformaticsplatform.github.io/enrichment_analysis_workshop/](https://monashbioinformaticsplatform.github.io/enrichment_analysis_workshop) happens automatically

# Detail

## Dependencies

You'll need [Hugo](https://gohugo.io/getting-started/installing/).

## Cloning
```bash
git clone --recurse-submodules https://github.com/MonashBioinformaticsPlatform/enrichment_analysis_workshop.git
```

## Editing

```bash
hugo server

# or if you want to see pages marked as drafts
# hugo server -D
```

* Content is in `content/`
* Images and CSS are in `static/`
* Some theme customization and overrides lives in `layouts/`

### Updating for past / new events

We want past events to automatically appear as a list of 'posts' at the bottom of the events page. To do this:

* Create a new page in the `content/module` folder (eg `basics.md`). Include the date at the end of the file as shown.


## Custom template features

### In config.toml

```toml
# Add the page here

## Main menu
[[menu.main]]
    name = "Basics"
    weight = 100
    identifier = "basics"
    url = "/module/basics"

```




You need to build and deploy the live site manually, do:
```bash
# This builds the static pages, commits and pushes to the Github pages site (using the 'public' git submodule).
# It doesn't commit or push any changes to your Markdown source - do that yourself.

./deploy.sh
```


