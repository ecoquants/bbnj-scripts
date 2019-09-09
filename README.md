# bbnj-scripts
migrating bbnj:inst/scripts to save space in R package bbnj

## index of rendered html files

{% for file in site.static_files %}
  {% if file.extname == '.html' %}
* [{{ file.path }}]({{ site.baseurl }}{{ file.path }})
  {% endif %}
{% endfor %}

### jekyll info on creating html listing


#### jekyll quickstart

- [Quickstart of Jekyll](https://jekyllrb.com/docs/)

install:

```bash
gem install jekyll bundler
```

run:

```bash
bundle exec jekyll serve
```

#### Gemfile setup

- [Setting up your GitHub Pages site locally with Jekyll - GitHub Help](https://help.github.com/en/articles/setting-up-your-github-pages-site-locally-with-jekyll)


Contents of new `Gemfile`:

```
source 'https://rubygems.org'
gem 'github-pages', group: :jekyll_plugins
```

```bash
bundle install
```

#### jekyll index listing

- [jekyll - How to list files in a directory with Liquid? - Stack Overflow](https://stackoverflow.com/questions/17446472/how-to-list-files-in-a-directory-with-liquid/31885127#answer-34023126)

```html
{% raw %}
{% for file in site.static_files %}{% if file.extname == '.html' %}
* [{{ file.path }}]({{ site.baseurl }}{{ file.path }})
{% endif %}{% endfor %}
{% endraw %}
```