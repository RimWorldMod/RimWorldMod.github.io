---
layout: page
title: Mods
permalink: /mods/
---
 {% for mod in site.mods %}

### **{{ mod.title }}** 

by *{{ mod.author }}* - 
{% for name in site.modders.name %} 
if {{ site.modders.name }} == {{ mod.author }}
    {{ site.modders.name }}

{% endfor %}

 > {{mod.content}}

 {% endfor %}