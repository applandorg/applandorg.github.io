---
layout: post
title:  "AppMap diagram editor"
author: Boris Adimov 
permalink: /code-gallery/:title/
category: gallery
wip: true
thumb: /code-gallery/assets/img/appmap-diagram-editor.jpg
image: /code-gallery/assets/img/diagram-editor.png
excerpt_separator: <!--more-->
---

<!--more-->

![AppMap diagram editor interface](/code-gallery/assets/img/diagram-editor.png "AppMap diagram editor")

{: .btn.btn-primary}
[Check out the AppMap diagram editor &raquo;](https://github.com/flywithmemsl/d3-appmap)

## Overview

Diagram Editor example shows how standart diagram component can be used to build an editor and stay in sync with updated data model. In this example, React ( compiled at runtime right in the browser) is used to display editor form. You can create new packageas and classes, as well as edit existing ones. You can also upload and edit any valid diagram json by passing URL to raw json into the corresponding field.    
### Launch
 ```bash
 git clone git@github.com:flywithmemsl/d3-appmap.git
 cd d3-appmap
 npm install
 npm run serve 
 ```
 App will be served at [http://localhost:10001](http://localhost:10001)
 

## Components used

This example is built upon slightly modified standard component diagram JavaScript component, which is available in the open source [d3-appmap](https://github.com/applandinc/d3-appmap/) project. Full code is avaliavble at [github](https://github.com/flywithmemsl/d3-appmap).

## Customizations

In this example, a `ComponentDiagram` is modifed to expand package nodes on double-click for usability. React app uses exposed graph property of `ComponentDiagram` instance to add listeneres to right click event on nodes(this is used to edit clicked node), `postrender` event to update form optinos, shared `window.ComponentDiagramModel` object to write changes to and finally `render` method to rerender changes.

## Data sources

The examples use AppMap data recorded from the tests for the open source application
[Discourse](https://github.com/discourse/discourse), "A platform for community
discussion". The recordings were created using the
[appmap-ruby](https://github.com/applandinc/appmap-ruby) client. Since the Discourse
application is open source and public on AppLand, the recorded scenario data can be freely
downloaded from scenarios in the application.

To obtain raw scenario data, visit the the [AppLand sandbox](https://app.land/), view the
[public applications](https://app.land/explore), and click on the Discourse application.

From the application page, choose a scenario:

<img style="width: 420px; height: 189px;" src="/code-gallery/assets/img/appmap-query-scenario.png">

Open the properties for the scenario:

<img style="width: 420px; height: 245px;" src="/code-gallery/assets/img/appmap-query-scenario-props.png">

Download the data:

<img style="width: 420px; height: 230px;" src="/code-gallery/assets/img/appmap-query-download.png">

Downloading several sets of data will make the query results more interesting.

## Related work
The scenarios of applications in the [AppLand sandbox](https://app.land) each contain a Timeline view, showing the
call sequence contained in the AppMap data.

[&laquo; Back to the code gallery](/code-gallery)
