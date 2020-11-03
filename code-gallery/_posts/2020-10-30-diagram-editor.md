---
layout: post
title:  "AppMap diagram editor"
author: Boris Adimov 
permalink: /code-gallery/:title/
category: gallery
wip: false
thumb: /code-gallery/assets/img/appmap-diagram-editor.jpg
image: /code-gallery/assets/img/diagram-editor.png
excerpt_separator: <!--more-->
---

The AppMap framework includes various indepented components to visualise your code data.This example shows how standart diagram component can be used to build an editor and stay in sync with updated data model.


<!--more-->

![AppMap diagram editor interface](/code-gallery/assets/img/diagram-editor.png "AppMap diagram editor")

{: .btn.btn-primary}
[Check out the AppMap diagram editor &raquo;](https://github.com/flywithmemsl/d3-appmap)

## Overview

Diagram Editor example shows how standart diagram component can be used to build an editor and stay in sync with updated data model. In this example, React ( compiled at runtime right in the browser ) is used to display an editor form. You can create new packageas and classes, as well as edit existing ones. You can also upload and edit any valid diagram json by passing URL to raw json into the corresponding field.    

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

### React integration

While there is not yet a React Component that implements a wrapper around AppMap componets, this example shows a way, albeit not the best or most performant, to work with AppMap components out of your existing React App. 

## Customizations

In this example, a `ComponentDiagram` is modifed to expand package nodes on double-click for usability. React app uses exposed graph property of `ComponentDiagram` instance to add listeneres to right click event on nodes(this is used to edit clicked node), `postrender` event to update form optinos, shared `window.ComponentDiagramModel` object to write changes to and finally a `render` method to paint changes to diagram.

## Data sources

The examples use AppMap data recorded from the tests for AppLand Web Service application. The data is already placed in the HTML code of the page and is also avaliable at [this gist](https://gist.githubusercontent.com/flywithmemsl/82242a372bbc7c462c8907c1e0c6245c/raw/031be7271dfbe5ba67c6bd998a08fa26a692db80/data.json). You can export edited model data by serialising object located at `window.componentDiagramModel` to JSON.


[&laquo; Back to the code gallery](/code-gallery)
