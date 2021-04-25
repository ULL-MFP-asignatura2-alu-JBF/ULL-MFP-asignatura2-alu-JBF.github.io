---
layout: page
title: Tareas
permalink: /tareas/
---
    
<div style="border-style: solid; border-radius: 25px;">
<ol>
{%- for col in site.collections %}
{%- unless col.label == "posts" %}
<li> Colección: {{ col.label }} </li>
  <ol>
  {%-  assign firstdocs = col.docs | slice: 0,3 %}
  {%- for elem in firstdocs %}
    <li> <b>path:</b> {{ elem.path }} <a href="{{ site.baseurl }}{{ elem.url }}">Ver</a> </li>
    <p>{{ elem.content | markdownify }}</p>
  {%- endfor %}
  </ol>
{%- endunless %}
{%- endfor %}
</ol>
</div>