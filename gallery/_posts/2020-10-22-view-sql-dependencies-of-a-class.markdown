---
layout: post
title:  "View SQL dependencies of a class"
author: Kevin Gilpin
permalink: /gallery/:title/
category: gallery
thumb: /gallery/assets/img/appmap-json-thumb.jpg
image: /gallery/assets/img/appmap-json.jpg
excerpt_separator: <!--more-->
---
When you are working on a particular class, you can use this applet to figure out which SQL (and which tables) are used to implement the behavior of that class.

Start by selecting a scenario name from the dropdown list below. Next, choose a class name from among the classes which are used by the scenario. When you choose a class, you'll see a list of all the SQL queries that class depends on. (The SQL dependencies of a class are all the SQL queries which occur as a child node of the class in the functional flow graph).
<!--more-->

[Read more](https://observablehq.com/@kgilpin/sql-dependencies-for-discourse-postscontroller-create-wh)
{: .btn.btn-primary}