---
layout: article
title: Docs admin
permalink: /docs-admin/
---

{%- assign thisCollection = site.collections
  | where: "label", page.collection
  | first -%}

This build's environment: {{jekyll.environment}}

##### Admin TOC

{% for doc in thisCollection.docs %}
  {%- assign filename = doc.path | split: "/" | last | split: "." | first -%}
  {%- unless filename == "index" %}
  * [{{doc.title}}]({{doc.url}})
  {%- endunless -%}
{%- endfor %}