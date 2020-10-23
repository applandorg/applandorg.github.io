---
layout: post
title:  "Diff of a program execution trace"
author: Rafal Rzepecki
permalink: /gallery/:title/
category: gallery
featured: true
thumb: /gallery/assets/img/simple-execution-trace.png
image: /gallery/assets/img/simple-execution-trace.png
excerpt_separator: <!--more-->
---

Let's look at a core capability of the AppMap framewmork: execution traces. What if we could tell how a specific patch affects the execution before even reading and understanding the change?

In this example, we first use appmap-ruby to record the execution of a simple program. Then we modify the program with an optimization, and record it again.
AppMap recordings are processed and fed into the Unix `diff` program 
to obtain a simple but illuminating 
analysis of how the program execution has changed.

<!--more-->

<a href="https://gist.github.com/dividedmind/172920e9bd9a19dfbb84856eb64f2524">
  <img alt="Check out the gist" style="width: 447px" src="/gallery/assets/img/simple-execution-trace.png">
</a>

{: .btn.btn-primary}
[Check out the Gist &raquo;](https://gist.github.com/dividedmind/172920e9bd9a19dfbb84856eb64f2524)

[&laquo; Back to the gallery](/gallery)
