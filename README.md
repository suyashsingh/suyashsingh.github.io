# Codebase for `suyashsingh.github.io`
+ To omit a page from the navigation menu, don't define `order` variable in page frontmatter.

## Running the local version
+ Instaling Plugins: Add them to `Gemfile` and `_config.yml`.
`bundle install`

+ Serving the site locally:
`bundle exec jekyll serve`

## Learnings
1. When a plain jekyll site is deployed on github, `github-pages` comes into action.
It sets a default theme, that injects a css file onto the site.This was causing
a blank entry in the navigation bar. Setting `theme` as blank in `_config.yml` fixes it.
**Many thanks to [Manoj](https://www.linkedin.com/in/manumani07/) for helping me out with this.**
Github issue link to a [similar problem.](https://github.com/github/pages-gem/issues/482) 
