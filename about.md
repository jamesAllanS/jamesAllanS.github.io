---
title: About
permalink: /about/
tags: []
summary: 
---

<h1 class="current"> This is what I'm about...</h1>

![random placeholder image featuring technology](http://placeimg.com/650/120/tech)

Lorem ipsum dolor sit amet consectetur adipisicing elit. Fugit ducimus explicabo quia repudiandae necessitatibus nam dicta ea iusto neque? Dolor rem iste, doloremque perspiciatis neque nesciunt saepe veritatis eaque corrupti.

## Skills:

* need to change this file to html

* iter thru sections
  * if index isEven
    * add to row
    * add page.current index to left col
    * add page.current index + 1 to right col

<div class="row">

<!-- TODO for loop needs to start on a given index -->
{% for section in site.about_sections limit:2 %}
  {% assign result = forloop.index | modulo:2 %}
  {% if result == 0 %}
<div class="column about-left">
  <h2>{{ section.title }}</h2>
  <h3>{{ section.description }}</h3>
  <p>{{ section.content | markdownify }}</p>
</div>
  {% else %}
<div class="column about-right">
  <h2>{{ section.title }}</h2>
  <h3>{{ section.description }}</h3>
  <p>{{ section.content | markdownify }}</p>
</div>
  {% endif %}
{% endfor %}

{% for i in (3..5) %}
  {{ i }}
{% endfor %}

</div>

* Version Control:
    * Git / Github

___


___