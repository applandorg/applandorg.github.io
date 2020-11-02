---
layout: post
title:  "AppMap Auto-configuration"
author: Jared Kreppein
permalink: /code-gallery/:title/
category: gallery
thumb: /code-gallery/assets/img/appmap-json-thumb.jpg
image: /code-gallery/assets/img/appmap-json.jpg
excerpt_separator: <!--more-->
---
A Ruby script that automatically adds the required dependencies to your Ruby project so you can begin AppMapping right away. Check out an [example](https://github.com/jaredKreppein/appmap_auto_dependencies#see-it-in-action) of using this script with the `appmap-ruby` client and `appland-cli` tool to map and visualize a project from scratch in just a few minutes.

<!--more-->

{: .btn.btn-primary}
[Check out the repo &raquo;](https://github.com/jaredKreppein/appmap_auto_dependencies)

## Components used
This project is used in conjunction with the `appmap-ruby` client, which is available in the open source [appmap-ruby](https://github.com/applandinc/appmap-ruby/) repository.

## Customizations
This script streamlines the process of preparing a Ruby project for AppMapping. Normally the `appmap.yml` and other dependencies are added manually, see [here](https://github.com/applandinc/appmap-ruby#configuration), but this script automates most of it allowing you to visualize your project ASAP.

## Data sources
The example shown maps the open source application [Ruby on Rails Tutorial Sample Application](https://github.com/mhartl/sample_app_6th_ed), which is a “reference implementation of the sample application from Ruby on Rails Tutorial: Learn Web Development with Rails (6th Edition) by Michael Hartl.” The application was mapped with the  [appmap-ruby](https://github.com/applandinc/appmap-ruby) client and then uploaded to the [AppLand sandbox](https://app.land) using the [appland-cli](https://github.com/applandinc/appland-cli) tool.

## Related work
Want to explore the mapset generated from the example? Check it out [here](https://app.land/applications/219?mapset=1932) or explore other mapsets by going to [https://app.land/explore](https://app.land/explore).


[&laquo; Back to the code gallery](/code-gallery)
