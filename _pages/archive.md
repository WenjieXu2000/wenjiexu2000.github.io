---
layout: page
permalink: /archive/
title: Archive
description: A chronological archive of all my blog posts.
nav: true
nav_order: 2
---

<div class="archive-container">
  <div class="archive-sidebar">
    <div class="archive-toc">
      <h3>Years</h3>
      <ul>
        {%- assign date_format = "%Y" -%}
        {%- assign sorted_posts = site.posts | sort: 'date' | reverse -%}
        {% assign grouped_posts = sorted_posts | group_by_exp: "post", "post.date | date: date_format" %}
        {% for year in grouped_posts %}
          <li><a href="#{{ year.name }}">{{ year.name }}</a></li>
        {% endfor %}
      </ul>
    </div>

    <div class="archive-tags">
      <h3>Tags</h3>
      <div class="tag-cloud">
        {% for tag in site.tags %}
          <a href="{{ tag[0] | slugify | prepend: '/blog/tag/' | relative_url }}">
            {{ tag[0] }} <span class="tag-count">({{ tag[1].size }})</span>
          </a>
        {% endfor %}
      </div>
    </div>

    <div class="archive-categories">
      <h3>Categories</h3>
      <div class="category-cloud">
        {% for category in site.categories %}
          <a href="{{ category[0] | slugify | prepend: '/blog/category/' | relative_url }}">
            {{ category[0] }} <span class="category-count">({{ category[1].size }})</span>
          </a>
        {% endfor %}
      </div>
    </div>

  </div>

  <div class="archive">
    {% for year in grouped_posts %}
      <h2 id="{{ year.name }}" class="archive-year-header">{{ year.name }}</h2>
      <ul class="post-list">
        {% for post in year.items %}
          {% assign post_date = post.date %}
          <li class="post-item" id="{{ post_date | date: '%Y-%m-%d' }}">
            <span class="post-date">{{ post_date | date: "%b %-d" }}</span>
            <a class="post-title" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
          </li>
        {% endfor %}
      </ul>
    {% endfor %}
  </div>
</div>

<script>
document.addEventListener('DOMContentLoaded', function() {
  const tocLinks = document.querySelectorAll('.archive-toc a');
  tocLinks.forEach(link => {
    link.addEventListener('click', function(e) {
      e.preventDefault();
      const targetId = this.getAttribute('href').slice(1);
      const targetElement = document.getElementById(targetId);
      if (targetElement) {
        targetElement.scrollIntoView({ behavior: 'smooth' });
      }
    });
  });
});
</script>
