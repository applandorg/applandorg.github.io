---
layout: default
title: AppMap
permalink: /
---

## Get New Data About Your Software’s Architecture

Traditional products such as application profilers, APMs, and loggers all provide information about characteristics of code and software applications.  AppMap provides a comprehensive inspection of your software architecture, aggregated in one simple file obtained simply easily from test case execution and other behavioral traces, and is entirely open source.

<div class="index-section">
  <table>
     <thead>
        <tr>
           <th class="no-border"></th>
           <th colspan="4">Application tracing methods</th>
        </tr>
     </thead>
     <tbody>
        <tr>
           <td class="no-border"></td>
           <td>Performance profiler</td>
           <td>APM</td>
           <td>Logging</td>
           <td>AppMap</td>
        </tr>
        <tr>
           <td>Level of detail</td>
           <td>Fine</td>
           <td>Coarse</td>
           <td>Very coarse</td>
           <td>Medium</td>
        </tr>
        <tr>
           <td class="green-cell">Commands received</td>
           <td class="green-cell">Yes</td>
           <td class="green-cell">Yes</td>
           <td class="green-cell">Yes</td>
           <td class="green-cell">Yes</td>
        </tr>
        <tr>
           <td>Commands sent</td>
           <td class="green-cell">Yes</td>
           <td class="yellow-cell">Maybe</td>
           <td class="yellow-cell">Maybe</td>
           <td class="green-cell">Yes</td>
        </tr>
        <tr>
           <td>Data model</td>
           <td>No</td>
           <td>No</td>
           <td>No</td>
           <td class="green-cell">Yes</td>
        </tr>
        <tr>
           <td>SQL queries</td>
           <td class="yellow-cell">Maybe</td>
           <td class="green-cell">Yes</td>
           <td class="yellow-cell">Maybe</td>
           <td class="green-cell">Yes</td>
        </tr>
        <tr>
           <td>Parameters</td>
           <td>No</td>
           <td class="yellow-cell">Maybe</td>
           <td class="yellow-cell">Maybe</td>
           <td class="green-cell">Yes</td>
        </tr>
        <tr>
           <td>Internal APIs</td>
           <td>Maybe</td>
           <td>No</td>
           <td>No</td>
           <td class="green-cell">Yes</td>
        </tr>
        <tr>
           <td>Code flow visualization</td>
           <td class="green-cell">Yes</td>
           <td>No</td>
           <td>No</td>
           <td class="green-cell">Yes</td>
        </tr>
        <tr>
           <td>Crypto</td>
           <td>No</td>
           <td>No</td>
           <td>No</td>
           <td class="green-cell">Yes</td>
        </tr>
        <tr>
           <td>Available in dev</td>
           <td class="green-cell">Yes</td>
           <td>No</td>
           <td class="green-cell">Yes</td>
           <td class="green-cell">Yes</td>
        </tr>
        <tr>
           <td>Links to source</td>
           <td class="green-cell">Yes</td>
           <td>No</td>
           <td>No</td>
           <td class="green-cell">Yes</td>
        </tr>
        <tr>
           <td>Aggregate by command</td>
           <td>No</td>
           <td>No</td>
           <td>No</td>
           <td class="green-cell">Yes</td>
        </tr>
     </tbody>
  </table>
</div>

### AppMap framework

The AppMap framework provides a means of gathering detailed information of your application’s inner workings. Use this information to generate insightful visualizations and analytics to share with your team.

![Appmap diagram](/assets/img/pages/appmap-diagram.svg)


### AppMap data specification

The AppMap data specification aims to capture detailed information of runtime code execution, data snapshots and application metadata. This specification is being developed by AppLand and its contributors to create a standard around data used in analyzing and visualizing application architecture, behavior and design. The working specification is available [here on GitHub](https://github.com/applandinc/appmap).

### Recording client

The recording client enables an application to dynamically record and emit app map files. Use the app map files you’ve captured to generate insightful visualizations and analytics of the behavior and architecture of your code. Clients are currently available for [Java](https://github.com/applandinc/appmap-java) or [Ruby](https://github.com/applandinc/appmap-ruby).

---

__Our goal at AppLand is to help code “speak for itself.__
We’re a group of passionate engineers and architects aiming to drive innovation in software architecture and design. Software is oftentimes complex and its nuances can be difficult to communicate efficiently. We'd like to change that.

Sounds interesting? Join the discussion in our [Discord community](https://discord.com/invite/7ZJfWwD).

---
