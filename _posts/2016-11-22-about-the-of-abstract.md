---
title: "About the uses of Abstracts"
date:   2016-11-22 10:54:58 +0100
categories: Coding
tags: [xml, inheritance, good practise]
---

## To all modders

Apparently there is bad information regarding xml inheritance.  Specifically regarding abstract definitions.

The prevailing thought pattern is that abstracts are inheritable across mods. **This is not true**. An abstract can only be inherited across files within the mod that defines it. This is known as [scope](https://en.wikipedia.org/wiki/Scope_(computer_science)) and trying to inherit from another mods abstract will result in it being "*out of scope*".  

> This is similar to the "using" statement in assembly sources which defines a namespace as "in scope" allowing referencing to classes in the namespace defined without explicitly referencing the namespace.

The big offender is "**BuildingBase**" which many modders are not defining thinking that they can inherit.  While *none of the abstracts are inheritable*, "**BuildingBase**" is used most often.

Please check your `output_log.txt/Player.log` and resolve any errors before releasing your mods.  

> Don't rely on the debug window popping up!

The issue with abstracts and errors, however, is that they do not show an error or even a warning directly.  Trying to inherit from an abstract which doesn't exist will result in the fields in the def which are not set by the def to be set to the default for the class (eg, ThingDef).  This can cause subtle errors which may not show as a direct link to the missing abstract.

While the game may "work," these errors can cause problems with *other* mods.  The [Community Core Library](https://ludeon.com/forums/index.php?topic=16599.0) is especially sensitive to `xml` errors and many users are experiencing problems and reporting bogus/junk bugs due to this.

Thank-you for reading this,
**1000101**

*Edited 12/08/2016*:  Fixed some typographical errors and added information regarding the lack of errors when trying to use undefined abstracts.

*Edit 15/11/2016*:

## TL;DR

If you don't define an abstract, don't use it.  No errors will be thrown by the game about missing abstracts but they *can* and *will* cause subtle errors which may not detectable at first or without other mods installed.

Bogus error reports and disgruntled users can be avoided by simply defining abstracts.

Guarantee the success of your own mods and others by defining every abstract you use.


**Skullywag** also posted this boiled-down information as PSAs:
[[Mods Subforum]](https://ludeon.com/forums/index.php?topic=27432.0)
[[Help Subforum]](https://ludeon.com/forums/index.php?topic=27433.0)
[[Releases Subforum]](https://ludeon.com/forums/index.php?topic=27431.0)