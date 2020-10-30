---
layout: post
title:  "Querying data in AppMaps"
author: Alan Potter
permalink: /code-gallery/:title/
category: gallery
thumb_url: https://asciinema.org/a/368789.svg
image_url: https://asciinema.org/a/368789.svg
excerpt_separator: <!--more-->
---

The recording clients (for [Ruby](https://github.com/applandinc/appmap-ruby) and
[Java](https://github.com/applandinc/appmap-java)) generate a rich set of data about the
internal structure of an application. Loading the data into a database makes it easier to
ask questions about the relationships between the appplication's components.

This example reads events from an [AppMap](https://github.com/applandinc/appmap) into a
[`CallTree`](https://github.com/applandinc/appmap-models/blob/master/src/callTree/callTree.js),
then loads the data into [neo4j](https://neo4j.com). A graph database makes it easy to find
all the classes that contain only "leaf" methods, i.e. those methods that don't call other
methods. These classes are good candidates for
[exclusion](https://github.com/applandinc/appmap-ruby#configuration), to reduce the noise
in an AppMap.

<!--more-->

<script id="asciicast-368789" src="https://asciinema.org/a/368789.js" async></script>

{: .btn.btn-primary}
[Check out the code &raquo;](https://gist.github.com/apotterri/5d4014f47e3dbd4c000ec4920835280a)

[&laquo; Back to the code gallery](/code-gallery)
