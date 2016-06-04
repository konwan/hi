---
title:   "Github pages with jekyll"
excerpt: "memo for building blog with github pages and jelly "
layout:  archive
author_profile: true
categories: 
  - life
tags:
  - jekyll
  - git
  - liquid
  - markdown
---


#####**[introduction]**    
1. GitHub Pages =>  
a public web pages and freely hosted on GitHub’s github.io domain or on a custom domain name of your choice. GitHub Pages are powered by Jekyll behind the scenes, so in addition to supporting regular HTML content, they’re also a great way to host your Jekyll-powered website for free.

2. Jekyll =>
a simple, blog-aware, static site generator. It takes a template directory containing raw text files in various formats, runs it through a converter (like Markdown) and our Liquid renderer, and spits out a complete, ready-to-publish static website suitable for serving with your favorite web server.

*structure:*

|-- _config.yml  
|-- _includes  
|-- _layouts  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   |-- default.html  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   |-- post.html      
|-- _posts  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   |-- 2016-05-31-firstpost.xx  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   |-- 2016-05-31-secondpost.xx  
|-- _site  
|-- index.html  

>_config.yml  
config file 

>_includes  
template partials such as header, footer

>_layouts  
define by YAML front matter，{ { content }} used to insert data to th layout

>_posts  
blog content(mf/html/textfile) naming with year-month-date-title.md  

>_site  
Jekyll output 

##### **[local jekyll]**      
1. install ruby  (ruby -v)
2. gem install jekyll
3. gem install bundler
4. empty =>   
    > jekyll new my-site  
    > cd my-site && jekyll serve   
    > theme => bundler install (download needy package)
    > bundle exec jekyll serve  
    > **add " gem 'package-name' " to Gemfile if bundle install some package fail**

##### **[steps]**
1. create new repository on github (select add readme.md / setting check "launch automatic page generator")  
   - username.github.io   
   - username.github.io/project-name  
2. git clone new-repository.git and jekyll-theme.git 
3. cd new-repository switch to branch gh-pages
4. cp jekyll-theme file to new-repository
5. change _config.yml
6. update menu _data/navigation.yml and link to _pages/file  （change minimal-mistakes config）

##### **[markdown]**  
online editor [Md Edit]   
* empty line : 2 tabs        
* title      : 1~6 #     
* list       : * / -     
* indent     : >         
* split line       : \- - -   
* bold       : **    
* link       : "[" words "]" (link)      
* photo      : !"[" alt text "]"(link)   
* change color : \`    
* color line   : \`\`\`         
* use html     : \`\`\` html / sh       


   
[GitHub Pages]:     https://pages.github.com/   
[Jekyll]:           https://jekyllrb.com/   
[Jekyll Doc]:       http://jekyllcn.com/docs/templates/
[Jekyll Sites]:     https://github.com/mojombo/jekyll/wiki/Sites    
[Jekyll Bootstrap]: http://jekyllbootstrap.com/ 
[Md Edit]:          http://dillinger.io/    
[MadeMistakes]:     https://mademistakes.com/work/
[Liquid]:           https://github.com/Shopify/liquid/wiki/Liquid-for-Designers
