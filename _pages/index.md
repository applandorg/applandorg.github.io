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

## How AppMap compares to other software tracing formats

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

---

__Our goal at AppLand is to help code “speak for itself.__
We’re a group of passionate engineers and architects aiming to drive innovation in software architecture and design. Software is oftentimes complex and its nuances can be difficult to communicate efficiently. We'd like to change that.

Sounds interesting? Join the discussion in our [Discord community](https://discord.com/invite/7ZJfWwD).

---
