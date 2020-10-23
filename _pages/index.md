---
layout: default
title: AppMap
permalink: /
---

Software tools such as performance profilers, APMs, and log aggregators all provide some information about the behavior of code; but none are
dedicated to helping developers inspect and optimize their application architecture. The AppMap framework provides comprehensive information about
your software architecture, recorded into simple JSON files. These AppMap files can be easily obtained by executing test cases or by
interactively recording a live, running application. You can use AppMap recordings to generate insightful visualizations and analytics, share
with your team, and optimize your software architecture.

![Appmap diagram](/assets/img/pages/appmap-diagram.svg)

### Data format specification

The AppMap data specification aims to capture detailed information of runtime code execution, data snapshots and application metadata. This specification is being developed by AppLand and its contributors to create a standard data format for analyzing, visualizing, and optimizing application architecture. The working specification is available at [https://github.com/applandinc/appmap](https://github.com/applandinc/appmap).

### Recording clients

The AppMap recording client enables an application to dynamically record and emit AppMap files. Use the AppMap files you’ve captured to generate insightful visualizations and analytics of the behavior and architecture of your code. Clients are currently available for [Java](https://github.com/applandinc/appmap-java) and [Ruby](https://github.com/applandinc/appmap-ruby).

### Analysis and visualization

AppMap data is easy to program, so you can quickly build custom analytics
and visualizations of your architecture.

Here are a few examples. [View the gallery](/gallery) for more!

<ul class="gallery-project-list">
  {% assign featured_posts = site.posts | where: "featured", true %}
  {% for post in featured_posts limit:4 %}
  {% if post.category=="gallery" %}
    <a class="gallery-project" href="{{ post.url }}">
        {% if post.thumb %}
          <img src="{{ site.baseurl }}{{ post.thumb }}" alt="{{ post.title }}" class="post-image post-thumb">
        {% endif %}
        <div class="post-content">
          <h2>{{ post.title }}</h2>
        </div>
    </a>
  {% endif %}
  {% endfor %}
</ul>


