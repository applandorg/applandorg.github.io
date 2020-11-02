---
layout: post
title:  "Auto-generated component diagram"
author: Kevin Gilpin
permalink: /code-gallery/:title/
category: gallery
featured: true
thumb: /code-gallery/assets/img/component-diagram-observable-thumb.jpg
image: /code-gallery/assets/img/component-diagram-observable.png
excerpt_separator: <!--more-->
---

The AppMap framework includes JavaScript code which can automatically render 
visual depictions of AppMap data. This example shows how AppMap data can be
displayed as a [C4 component diagram](https://c4model.com/#ComponentDiagram).

<!--more-->

<iframe width="100%" height="474" frameborder="0"
  src="https://observablehq.com/embed/@kgilpin/appmap-component-diagram?cell=diagramContainer&cell=stylesheet"></iframe>

{: .btn.btn-primary}
[Check out the Component Diagram &raquo;](https://observablehq.com/@kgilpin/appmap-component-diagram)

## Components used

This example uses the standard component diagram JavaScript component, which is available in the open source [d3-appmap](https://github.com/applandinc/d3-appmap/) project.

## Customizations

This example shows how to initialize and display a component diagram, providing scenario JSON data and a container DOM element. By following this example, you can display an AppLand component diagram in any web site or application which supports JavaScript. You can use a custom coding environment, or leverage a tool like Observable, CodePen, or JSFiddle.

## Data sources

The example uses AppMap data recorded from the open source application [if-me](https://github.com/ifmeorg/ifme), which is a "Free, open source mental health communication web app to share experiences with loved ones." The data used in this example was recorded from an If-Me test case using the [appmap-ruby](https://github.com/applandinc/appmap-ruby/) client, and uploaded to the [AppLand sandbox](https://app.land). Since the If-Me application is open source and public on AppLand, the recorded scenario data is freely downloadable. 

To obtain the download URL for any scenario, click Properties and then find the 
Raw data link:

<img style="width: 420px; height: 291px;" src="/code-gallery/assets/img/raw-data-link.png">

## Related work

A component diagram view available in the [AppLand sandbox](https://app.land) for every application. To see the component diagram for if-me, go to [https://app.land/explore](https://app.land/explore) and click on the If-Me application. The Component tab will be selected by default, showing an interactive component diagram of the application.

[&laquo; Back to the code gallery](/code-gallery)
