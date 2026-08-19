---
layout: page
permalink: /publications/
title: Publications
description: publications by categories in reversed chronological order.
nav: true
nav_order: 2
---

<!-- _pages/publications.md -->

<div class="publications">

<h2 class="year">Journal Articles</h2>

{% bibliography --query @article %}

<h2 class="year">Conference Papers</h2>

{% bibliography --query @inproceedings %}

</div>
