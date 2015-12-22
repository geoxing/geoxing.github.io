title: hexo tips
date: 2015-12-10 11:13:50
categories: 
- Job  
tags:
- Tips  
- Hexo
---
# Markdown engine sucks
When the post "Build static blog using github & hexo on windows" was generated,I privew in the
brower,  it sucks,many element of markdown can't be rightly compiled,for instance,"quote",
but in the issue of github,it's ok(finally i choosed the issue)  
So,I try to replace the "hexo-renderer-marked" by "hexo-renderer-markdown-it",but the same result,
how could it be ?  

# Add tags  
In hexo , the tags's  format is:
```
tags: 
- Requirements;
- Develop
- Design
- Integration
- Operation
- Analysis
- Cycle
```
the separator is not semicolon or comma    

# Add Categories
like "add tags"  

<!-- more -->  

# Add "about"
## make a about page
excute:
```
hexo new page "about"
```
hexo will generate a category of "about", include a index.md file
## write about you
edit the "index.md",introduce youself

# Add excerpt_link(that is , namely Read More)  
In hexo excerpt_link position is up to writor by adding 
```
<!-- more --> 
```
any where you want  

# Add favicon.ico for your website 
## make a icon 
using http://www.bitbug.net/  ,you can get 32*32(recommend) or 16*16 icon
## add gerenated favicon.ico file  into /theme/yourtheme/source/  
## edit theme's _config.xml 
  "favicon: /favicon.ico",it will be requested by browser automatically.

# hexo markdown tips
##  code
pay Attention to code case 

# _config.xml of hexo
```
# Hexo Configuration
## Docs: http://hexo.io/docs/configuration.html
## Source: https://github.com/hexojs/hexo/

# Site
title: Debug
subtitle: One day,One post  
description:
author: GeoXing
language:
timezone:

# URL
## If your site is put in a subdirectory, set url as 'http://yoursite.com/child' and root as '/child/'
url: http://yoursite.com
root: /
permalink: :year/:month/:day/:title/
permalink_defaults:

# Directory
source_dir: source
public_dir: public
tag_dir: tags
archive_dir: archives
category_dir: categories
code_dir: downloads/code
i18n_dir: :lang
skip_render:

# Writing
new_post_name: :title.md # File name of new posts
default_layout: post
titlecase: true # Transform title into titlecase
external_link: true # Open external links in new tab
filename_case: 0
render_drafts: false
post_asset_folder: false
relative_link: false
future: true
highlight:
  enable: true
  line_number: true
  auto_detect: true
  tab_replace:

# Category & Tag
default_category: All
category_map:
tag_map:

# Date / Time format
## Hexo uses Moment.js to parse and display date
## You can customize the date format as defined in
## http://momentjs.com/docs/#/displaying/format/
date_format: YYYY-MM-DD
time_format: HH:mm:ss

# Pagination
## Set per_page to 0 to disable pagination
per_page: 10
pagination_dir: page

# Extensions
## Plugins: http://hexo.io/plugins/
## Themes: http://hexo.io/themes/
theme: minos

# Deployment
## Docs: http://hexo.io/docs/deployment.html
deploy:
  type: git
  repository: https://github.com/geoxing/geoxing.github.io.git
  branch: master

toc:
  maxDepth: 10

#fix_cjk_spacing: true
```
 

