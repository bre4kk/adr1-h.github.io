---
layout: post
title: "Setup Jekyll Rain Theme"
description: "In this article we are going to see how to configure the Rain theme for Jekyll. We will also cover how to create new pages and update the Font Awesome icons."
author: "gh0st"
---
## Setup
Here are the steps I followed to configure the website locally as it gave me plenty of errors with the default configuration.
1. Install the latest stable version of Ruby (Ruby+Devkit)
2. Run the ridk install step on the last stage of the installation wizard. From the options choose:
   ```
   MSYS2 and MINGW development toolchain
   ```
3. Open a new command prompt window from the start menu, so that changes to the PATH environment variable becomes effective. Install Jekyll and Bundler using:
   ```ruby
   gem install jekyll bundler
   ```
4. Replace the contents of the Gemfile with the following:
   ```ruby
   gem "jekyll"
   gem "jekyll-feed"
   gem "jekyll-paginate"
   ```
5. Remove rain.gemspec file.
6. Go into the project directory and execute the following commands:
   ```ruby
   bundle install
   bundle exec jekyll serve
   ```
7. Head over to http://127.0.0.1:4000/ to see your page.

## Create new page
Here is how to create an additional page. In this case I will create an ‘About me’ page.
1. Create a new folder called _pages
2. Create a new file inside this folder called, for example, aboutme.md
3. Add the following content inside the aboutme.md file:
   ```markdown
   ---
   layout: default    # Reference to the layout file in _layouts/default.html
   title: "About Me"
   permalink: /aboutme/
   ---

   <!-- Content of the About Me page -->
   Welcome to my About Me page!
   ```
4. Make sure the layout is set to "default" (or whatever layout name you are using) in the _layouts directory.
5. Update the navigation bar at _layouts/default.html. Add the following element to the navigation bar:
   ```html
   <li><a href="{{ site.url }}/aboutme/">About Me</a></li>
   ```
6. Add the following to your _config.yml file:
   ```yml
   include:
  - _pages
   ```

## Update fontawesome icons
Update _includes/head.html:
```html
<link rel="stylesheet" href="https://use.fontawesome.com/releases/v6.6.0/css/all.css" crossorigin="anonymous">
<!-- Required for Buy Me a Coffee icon -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/fork-awesome@1.2.0/css/fork-awesome.min.css" integrity="sha256-XoaMnoYC5TH6/+ihMEnospgm0J1PM/nioxbOUdnM8HY=" crossorigin="anonymous">
```
The first link is updated with the new version 6.6.0 of fontawesome which includes new logos such as the Twitter/X logo.  
The second link is only required if you want to use the Buy Me a Coffee icon in your website.

