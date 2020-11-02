---
layout: post
title:  "View SQL dependencies of a class"
author: Kevin Gilpin
permalink: /code-gallery/:title/
category: gallery
featured: true
thumb: /code-gallery/assets/img/view-sql-dependencies-thumb.jpg
image: /code-gallery/assets/img/view-sql-dependencies.jpg
excerpt_separator: <!--more-->
---

When you are working on a particular class, you can use this applet to figure out which SQL (and which tables) are used to implement the behavior of that class.

<!--more-->

AppMap data files contain all the SQL queries that are performed by a program. These queries are stored in the [sql_query](https://github.com/applandinc/appmap#sql-query-attributes) field of relevant events. Because AppMap events include the caller/callee context, we can use an AppMap data file to find out which SQL queries a class “depends” on. When we say a class depends on a SQL query, we mean that the query is made by the class, or by some descendent function call of the class.

Start by selecting a scenario name from the dropdown list below. Next, choose a class name from among the classes which are used by the scenario. When you choose a class, you'll see a list of all the SQL queries that class depends on. (The SQL dependencies of a class are all the SQL queries which occur as a child node of the class in the functional flow graph).

[![Check it out](/code-gallery/assets/img/view-sql-dependencies.jpg)](https://observablehq.com/@kgilpin/sql-dependencies-for-discourse-postscontroller-create-wh)

{: .btn.btn-primary}
[Check out the Observable notebook &raquo;](https://observablehq.com/@kgilpin/sql-dependencies-for-discourse-postscontroller-create-wh)

## Components used

This example uses the [AppMap data format](https://github.com/applandinc/appmap/) directly.

## Customizations

The AppMap `events` are parsed into a tree. Then the classes are detected, and a filter is applied 
which selects only those classes which have a `sql_query` child node.

## Data sources

The user can select AppMap data from three different open source applications. 
Each of these applications is mapped and available in the [App.Land sandbox](https://app.land/explore):

* [Discourse](https://app.land/applications/283)
* [If-Me](https://app.land/applications/165)
* [Rails Sample App 6th Edition](https://app.land/applications/219?mapset=1970)

## Related work

If you view a Scenario in the App.Land sandbox, open the scenario filter dialog.

![Activate scenario filters](/code-gallery/assets/img/activate-scenario-filters.png)

Then, deselect the "stack depth" checkbox and leave the SQL filters enabled. 

![Remove stack depth filter](/code-gallery/assets/img/remove-stack-depth-filter.png)

Now you will see only the code flows that lead to a SQL query. In this way, you can do a visual inspection of how the code and queries are related.

[&laquo; Back to the code gallery](/code-gallery)
