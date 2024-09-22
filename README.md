## Build and serve

```
1. Install latest stable version of Ruby (Ruby+Devkit)
2. Run the ridk install step on the last stage of the installation wizard. From the options choose: MSYS2 and MINGW development toolchain.
3. Open a new command prompt window from the start menu, so that changes to the PATH environment variable becomes effective. Install Jekyll and Bundler using: gem install jekyll bundler
4. Replace the contents of the Gemfile with the following:
gem "jekyll"
gem "jekyll-feed"
gem "jekyll-paginate"

5. Remove rain.gemspec

6. Execute the following commands:
bundle install
bundle exec jekyll serve
```

Head over to http://127.0.0.1:4000/ to see your page.

