---
layout: single
title: "Mods"
permalink: /mods/
---
 {% for mod in site.mods %}
### **[{{ mod.title }}]({{mod.title | slugify }})** 
 > >{{mod.excerpt}}

{% assign modauthor = site.modders | where:"name" , mod.author | first %} by **[{{ mod.author }}](https://github.com/{{modauthor.github_id}})**

___
 {% endfor %}