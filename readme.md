# Image Slideshows

![Refinery Image Slideshows](http://refinerycms.com/system/images/0000/0876/news.png)

## About

__Image Slideshows allows you to create groups of images for use by a JavaScript image slider.__

Suggested image slider: [Nivo Slider](http://nivo.dev7studios.com)

## Requirements

[Refinery CMS](http://refinerycms.com) "core" engine version 2.0.0 or later.

### Gem Installation

Include the latest [gem](http://rubygems.org/gems/refinerycms-image_slideshows) into your Refinery CMS application's Gemfile:

```ruby
gem "refinerycms-image_slideshows", '~> 1.0'
```

Then type the following at the command line inside your Refinery CMS application's root directory:

    bundle install
    rails generate refinery:image_slideshows
    rake db:migrate
    rake db:seed
    
## How to display a slideshow with [Nivo Slider](http://nivo.dev7studios.com):

```html
  <body>
    <div id="wrapper">
      <div class="slider-wrapper theme-default">
        <div id="slider" class="nivoSlider">
          <% main_slideshow.image_slides.each do |image_slide| %>
            <%= link_to image_slide.link_url do %>
              <img src="<%= image_slide.image.url %>" alt="<%= image_slide.title %>" title="<%= image_slide.caption %>" />
            <% end %>
          <% end %>
        </div>
      </div>
    </div>
    <script type="text/javascript" src="/javascripts/jquery-1.7.1.min.js"></script>
    <script type="text/javascript" src="/javascripts/jquery.nivo.slider.js"></script>
    <script type="text/javascript">
      $(window).load(function() {
          $('#slider').nivoSlider({
            <%= raw main_slideshow.js_config %>
          });
      });
    </script>
  </body>
```
    





