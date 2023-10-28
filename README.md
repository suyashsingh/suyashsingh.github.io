# Codebase for `suyashsingh.github.io`
+ To omit a page from the navigation menu, don't define `order` variable in page frontmatter.

## Jekyll Installation

```bash
Jekyll Local Installation
https://jekyllrb.com/docs/installation/ubuntu/

sudo apt-get install ruby-full build-essential zlib1g-dev

echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc

gem install jekyll bundler
```

If you get error gem not found:
sudo apt-get install ruby-rubygems

Also check /usr/bin folder: ls *gem* before installing ruby-rubygems
If you see gem3.0 create a softlink to it, else you will have to
use gem3.0 for all the commands instead of gem

ln -s gem3.0 gem

Check by creating a site locally

```
jekyll new myblog
cd myblog
bundle exec jekyll serve --host=0.0.0.0
```


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
 
