---
layout: page
title: Mods
permalink: /modsabout/
---
{% for mod in site.mods %}
 <div class="mod">
 <h2>{{ mod.title }} by **{{ mod.author }}**</h2>
 {{ mod.content }}
 </div> 
 {% endfor %}
