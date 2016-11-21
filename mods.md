---
layout: page
title: Mods
permalink: /mods/
---
 {% for mod in site.mods %}

### **{{ mod.title }}** 

by *{{ mod.author }}* - 
{% if site.modders.name == "{{ mod.author }}" %} Github page of {{ site.modders.name }}
{% endif %}

 > {{mod.content}}

 {% endfor %}