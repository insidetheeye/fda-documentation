---
title: Content reuse
tags: 
  - "single-sourcing"
keywords: "includes, conref, dita, transclusion, transclude, inclusion, reference"
last_updated: "August 12, 2015"
summary: "You can reuse chunks of content by storing these files in the includes folder. You then choose to include the file where you need it. This works similar to conref in DITA, except that you can include the file in any content type."
published: true
---



## About content reuse
You can embed content from one file inside another using includes. Put the file containing content you want to reuse (e.g., mypage.html) inside the \_includes folder, and then use a tag like this:

{% raw %}![ade2.jpg]({{site.baseurl}}/ade2.jpg)

```
{% include mypage.html %}
```
{% endraw %}

With content in your \_includes folder, you don't add any frontmatter to these pages because they will be included on other pages already containing frontmatter.

Also, when you include a file, all of the file's contents get included. You can't specify that you only want a specific part of the file included. However, you can use parameters with includes. See [Jekyll's documentation](http://stackoverflow.com/questions/21976330/passing-parameters-to-inclusion-in-liquid-templates) for more information on that.

## Page-level variables

You can also create custom variables in your frontmatter like this: 

```
---
title: Page-level variables
permalink: /page_level_variables/
thing1: Joe
thing2: Dave
---
```

You can then access the values in those custom variables using the `page` namespace, like this:


{% raw %}
```
thing1: {{page.thing1}}
thing2: {{page.thing2}}
```
{% endraw %}

Honestly, I haven't found a tremendous use case for page-level variables, but it's nice to know they're available. 

I use includes all the time. Most of the includes in the \_includes directory are pulled into the theme layouts. For those includes that change, I put them inside custom and then inside a specific project folder.
