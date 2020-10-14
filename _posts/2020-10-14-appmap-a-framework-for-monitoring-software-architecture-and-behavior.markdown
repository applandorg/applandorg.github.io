---
layout: post
title:  "AppMap : A framework for monitoring software architecture and behavior"
author: Kevin Gilpin
permalink: /blog/:year/:month/:day/:title/
thumb: /assets/img/posts/unblock-yourself-thumb.jpg
image: /assets/img/posts/unblock-yourself-illo.svg
excerpt_separator: <!--more-->
---

There has been a tremendous increase in the number of products and metrics for the DevOps toolchain, particularly in the delivery of software to the production environment, the automation and standardization of the quality control of code. But one area has lingered as an “unmetriced” area of the SDLC for the last 20 years since the agile development and DevOps movements took flight : analysis of software architecture. 
<!--more-->
 
The AppMap framework is designed to address this gap in software analysis. It consists of three core elements. First, a standard data format captures detailed information of runtime code execution, data snapshots and application metadata. Client libraries enable live applications to record and emit this data, while visualization and analysis tools provide insights into application behavior and architecture. 
 
Altogether, the AppMap framework can provide you and your team with a clear picture of how your software works and how it changes over time. 
 
AppMap clients are shared under the MIT open source license.

## What is the AppMap client?
The AppMap client is a language-specific library which records code behavior during the execution of an application or library. The recordings are stored in JSON files, which can then be visualized and analyzed with many different graphing and monitoring tools.

## How does the AppLand client work?
1. It all starts in your own application code. You - the developer - add the AppMap client to your project configuration. To record data, you simply run your app with the appmap client enabled. As you run your app, the AppMap client captures all the important code behavior events as they occur. Today, these events include HTTP server and client requests, function calls, SQL, and cryptography. The exact set of events which you capture can be configured using an `appmap.yml` file. The recorded data can be either verbose or concise, depending on how you customize the default behavior. The events captured by the AppMap client are stored in a well-structured JSON format. The AppMap data files are typically stored in the tmp directory of the project.
2. Once you have recorded your app, you can visualize and analyze the behavior, design and architecture of the code. This analysis can be performed using a local toolchain directly against the appmap JSON files, or the files can be uploaded to a server and processed there.
3. The monitoring backend will turn your metrics from a stream of numbers on the wire into usable charts and alert you when needed. AppLand has a backend for reporting and creating reports, visualizations, and dashboards. 

## What languages does AppMap support?
There are clients for Ruby and Java currently.  We will publish our client library roadmap on this site as well as links to any community developed clients.

## How AppMap is different
There are alternative methods for analyzing code, including performance tracing and static analysis. Here’s what sets AppMap apart:
1. **Simplicity:** Not only is it very easy to instrument your app, the format is easy to code against. The output is JSON and you can import it and process it with many visualization, monitoring, and analytic backends.
2. **Level of detail:** AppMap is the right level of detail to understand code design and architecture. Performance tracing data doesn’t provide enough detail; debuggers don’t do a good job of showing the high level view. AppMap is the “just right” amount of information for understanding how code works.
3. **“Shifted-left”:** With AppMaps, you don’t need to wait until your code is in production to find out where the design problems and inefficiencies lie. When code is processed through a CI pipeline before releasing to production, all the AppMap recording and analytics can be performed as part of the CI/CD workflow. And recording appmaps in CI will ensure that you always have correct and up-to-date data for each version. 
4. **Visualization-friendly and integration-friendly:** We believe that data about code behavior and architecture is essential. Every company should have this data set available for visualizations, analysis, and quality management. There are many UML drawing tools, like Mermaid.js and PlantUML which can use AppMap data to build graphical depictions of software. This means no vendor lock-in for seeing and sharing your architecture diagrams. 

## What problem does AppMap solve?
Beyond the technical problems, appmaps provide greater transparency around application architecture. Clear models of the architecture of modern enterprise software need to be available and consumable on multiple levels of detail. Clear understanding of design should not be the realm of the few in an organization, or localized to commercial or proprietary products. Our very lives and safety rely on the quality of software and improving that quality is a public good. Clearly communicated architecture and design is fundamental knowledge for the development process. 

Getting people oriented around software architecture and design is necessary and required for them to make high-quality improvements. And the learning curve is simply too steep for many developers in increasingly large codebases. AppMaps allow for a culture where developers and leaders can self-service and self-educate on questions of architecture and design. Where architectural analysis and refinement is possible on a continuous basis, and where hard to identify and complex bugs are made evident and avoidable before they hit production.

## AppMaps and AppLand
Our goal at [AppLand](https://appland.com) is to help code “speak for itself” and to help build common artifacts so developers can more deeply understand the code they work on and the larger design implications of their choices. 
 
Through pictures and graphics we can democratize knowledge of how things work, across an organization of technical and non-technical stakeholders. Grady Booch once said that UML was a *competitive differentiator*, during the period when waterfall design still ruled and people routinely made blueprints and design documents before they built software, and may or may not have reconciled them afterward. Agile has moved away from that, but that does not mean that everyone has their bearings straight in the codebase from the design perspective. 
 
Just as we don’t leave home without detailed maps of where we are going and notifications of the road hazards along the way, we shouldn’t be driving blind in our own software. We need detailed maps of where we are heading in the complex systems of our software. AppMaps are here to provide you with the data and tools to make your own maps and identify architectural hazards along the way.
 
We are here to help. Consider [joining our Discord](https://discord.com/invite/N9VUap6) to discuss how to use the AppMap client and discuss all things software architecture.
 
If you would like to discuss our commercial offerings, head over to [https://app.land](https://app.land) to check out what we are building.  We have a [FREE LIBRARY of OSS projects](https://app.land/explore) we’ve scanned to share project architecture information with the world of developers it could help.  
 
We can also be found on Twitter [@LandOfApps](https://twitter.com/landofapps) sharing ideas, tips and tricks for using the AppMap client. 
 
Happy AppMapping!
 
-Elizabeth Lawler
Founder, [AppLand.org](https://appland.org)
Twitter [@elizabethlawler](https://twitter.com/elizabethlawler)
 
 
