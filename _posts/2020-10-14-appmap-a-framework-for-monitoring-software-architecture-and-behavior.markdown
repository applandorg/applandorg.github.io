---
layout: post
title:  "AppMap: A framework for monitoring software architecture and behavior"
author: Elizabeth Lawler
permalink: /blog/:year/:month/:day/:title/
thumb: /assets/img/posts/appland-post-thumb-fpo.svg
image: /assets/img/posts/appland-post-feature-fpo.svg
category: blog
excerpt_separator: <!--more-->
---

There has been a tremendous increase in the number of products and metrics for the DevOps toolchain, particularly in the delivery of software to the production environment, and the automation and standardization of the quality control of code. 
 
But one area has lingered as an “unmetriced” area of the SDLC for the last 20 years since the agile development and DevOps movements took flight: analysis of software architecture. 

<!--more-->
 
With this in mind, we designed the AppMap framework to address this gap in software analysis. The framework consists of two core elements. First, a standard data format that captures detailed information of runtime code execution, data snapshots and application metadata. Second, client language libraries that enable automatically capturing this data from your applications. This information can be used to generate insightful visualizations and analytics of the behavior and architecture of your code.

 
Altogether, the AppMap framework can provide you and your team with a clear picture of how your software works and how it changes over time. 
 
AppMap clients are shared under the MIT open source license.


## What is the AppMap client?
The AppMap client is a language-specific library which records code behavior during the execution of an application or library. The recordings are stored in JSON files, which can then be visualized and analyzed with many different graphing and monitoring tools. There are currently clients for [Ruby](https://rubygems.org/gems/appmap/versions/0.22.0) and [Java](https://github.com/applandinc/appmap-java/releases). 

## How does the AppLand client work?
1. It all starts in your own application code. You - the developer - add the AppMap client to your project configuration. To record data, you simply run your app with the AppMap client enabled. As you run your app, the AppMap client captures all the important code behavior events as they occur. Today, these events include HTTP server and client requests, function calls, SQL, and cryptography. The exact set of events which you capture can be configured using an appmap.yml file. The recorded data can be either verbose or concise, depending on how you customize the default behavior. The events captured by the AppMap client are stored in a well-structured JSON format. The AppMap data files are typically stored in the tmp directory of the project.  An example file for an example application is found here. 
2. Once you have recorded your app, you can visualize and analyze the behavior, design and architecture of the code. This analysis can be performed using existing toolchain against the AppMap JSON files.
3. Feeding AppMap data to a monitoring backend will turn your metrics from a stream of numbers on the wire into usable charts and alert you of major changes when needed. AppLand provides a backend for reporting and creating reports, visualizations, and dashboards. 

## What languages does AppMap support?
There are clients for [Ruby](https://rubygems.org/gems/appmap/versions/0.22.0) and [Java](https://github.com/applandinc/appmap-java/releases) currently. We will publish our client library roadmap on this site as well as links to any community developed clients.

## How AppMap is different
While there are alternative methods for analyzing code, including performance tracing and static analysis, here is what sets AppMap apart:
1. **Simple:** The format itself is easy to code against. The output is JSON and you can import it and process it with many visualization, monitoring, and analytic backends.
2. **Correct data level:** AppMap generates the right level of detail to understand code design and architecture. Existing performance tracing tools don’t provide enough detail; debuggers don’t do a good job of showing the high level view. AppMap is the “just right” amount of information for understanding how code works.
3. **Development Centric Workflow:** With AppMaps, you don’t need to wait until your code is in production to find design problems and inefficiencies. By using AppMaps with Test Driven Development (TDD), the data you need to perform an analysis is right there.   The recording can be integrated into the CI/CD workflow via integrations. Recording AppMaps in CI automatically populates correct and up-to-date architecture data for each version. 
4. **Integration-friendly:** We believe that data about code behavior and architecture is essential. Every company should have this data set available for visualizations, analysis, and quality management. There are many UML drawing tools, like Mermaid.js and PlantUML, and analytics backends like (X and Y) which can use AppMap data to build graphical depictions of software. This means no vendor lock-in for seeing and sharing your architecture diagrams. 

## What problem does AppMap solve?
Software engineering teams need clear models of architecture to be available and consumable on multiple levels of detail. Clear understanding of design is essential to everyone and should not be the realm of the few in an organization. Clearly communicated architecture and design is fundamental knowledge for the development process. 

Getting people oriented around software architecture and design is necessary and required for them to make high-quality improvements. And the learning curve is simply too steep for many developers in increasingly large codebases. 

AppMaps allow for a culture where developers and leaders can self-service and self-educate on questions of architecture and design. A culture where architectural analysis and refinement is possible on a continuous basis, and where hard to identify and complex bugs are made evident and avoidable before they hit production.

## AppMaps and AppLand
Our goal at AppLand is to help code “speak for itself” and to help build tools that create data and common artifacts so people who work on software can more deeply understand the code they work on and the implications of their choices in complex systems. 
 
Through the automated creation of accurate and timely pictures of architecture, we can democratize knowledge of and communication about how things work.  We can get the right sized answer to our questions. We can share the knowledge across an organization, and among technical and non-technical stakeholders alike. 
 
Just as we don’t leave home without detailed maps of where we are going and notifications of the road hazards along the way, we shouldn’t be driving blind in our own software. We need detailed maps of where we are heading in the complex systems of our software. AppMaps are here to provide you with the data and tools to make your own maps and identify architectural hazards along the way.
 
We are here to help. Consider [joining our Discord](https://discord.com/invite/N9VUap6) to discuss how to use the AppMap client and discuss all things software architecture.
 
If you would like to discuss our commercial offerings, head over to [https://app.land](https://app.land) to check out what we are building. Or check out the [open library of OSS projects](https://app.land/explore) we’ve scanned. We can also be found on Twitter [@LandOfApps](https://twitter.com/landofapps) sharing ideas, tips and tricks for using the AppMap client. 
 
Happy AppMapping!
 
-Elizabeth Lawler
Founder, [AppLand.org](https://appland.org)
Twitter [@elizabethlawler](https://twitter.com/elizabethlawler)
