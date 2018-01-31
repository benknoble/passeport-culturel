---
layout: default
permalink: index.html
title: Passeport culturel
description: "Qu'est-ce qu'il y a ?"
---
<h1><a href="{{ site.url }}/featured/"><i>Importants</i></a></h1>
<div class="posts">
  {% for post in site.categories.featured limit:2 %}
  <div class="post">
    <h3 class="post-title">
      <a href="{{ site.url }}{{ post.url }}">
        {{ post.title }}
      </a>
    </h3>

  {% if post.modified.size > 2 %}<span class="post-date indexpg" itemprop="dateModified" content="{{ post.modified | date: "%Y-%m-%d" }}"><i class="fa fa-edit" title="Mise à jour"> {{ post.modified | date_to_string }}</i> <a href="{{ site.url }}/featured" title="Ecrits importants"><i class="fa fa-paperclip" title="Important" class="social-icons"></i></a></span>{% else %}<span class="post-date indexpg" itemprop="datePublished" content="{{ post.date | date: "%Y-%m-%d" }}"><i class="fa fa-calendar" title="Date publié"> {{ post.date | date_to_string }}</i> <a href="{{ site.url }}/featured" title="Ecrits importants"><i class="fa fa-paperclip" title="Important" class="social-icons"></i></a></span>{% endif %}

 {% if post.description.size > 140 %}{{ post.description | markdownify | remove: '<p>' | remove: '</p>' }}{% else %}{{ post.excerpt | markdownify | remove: '<p>' | remove: '</p>' }}{% endif %} <a href="{{ site.url }}{{ post.url }}" title="De plus"><strong>De plus...</strong></a>
  </div>
  <hr class="transp">
  {% endfor %}
</div>

<h1><a href="{{ site.url }}/blog/"><i>Récents</i></a></h1>
<div class="posts">
  {% for post in site.posts limit:3 %}
  {% unless post.category contains "featured" %}
  <div class="post">
    <h3 class="post-title">
      <a href="{{ site.url }}{{ post.url }}">
        {{ post.title }}
      </a>
    </h3>

  {% if post.modified.size > 2 %}<span class="post-date indexpg" itemprop="dateModified" content="{{ post.modified | date: "%Y-%m-%d" }}"><i class="fa fa-edit" title="Last updated"> {{ post.modified | date_to_string }}</i></span>{% else %}<span class="post-date indexpg" itemprop="datePublished" content="{{ post.date | date: "%Y-%m-%d" }}"><i class="fa fa-calendar" title="Date publié"> {{ post.date | date_to_string }}</i></span>{% endif %}

 {% if post.description.size > 140 %}{{ post.description | markdownify | remove: '<p>' | remove: '</p>' }}{% else %}{{ post.excerpt | markdownify | remove: '<p>' | remove: '</p>' }}{% endif %} <a href="{{ site.url }}{{ post.url }}" title="De plus"><strong>De plus...</strong></a>
  </div>
  {% unless forloop.last %}<hr class="transp">{% endunless %}
  {% endunless %}
  {% endfor %}
</div>
<h3 class="post-title">
<div class="pagination" style="margin: 0.5rem;">
    <a class="pagination-item older" href="{{ site.url }}/blog"><i class="fa fa-edit"> Blog</i></a>
    <a class="pagination-item newer" href="{{ site.url }}/tags"><i class="fa fa-tags"> Mots clés</i></a>
</div>
</h3>
