---
title: Blog
permalink: /blog/
---

<style>
  .blog-wrap {
    max-width: 860px;
    margin: 0 auto;
    padding: 64px 18px;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, sans-serif;
  }

  .blog-title {
    font-size: 38px;
    font-weight: 800;
    margin-bottom: 8px;
  }

  .blog-desc {
    color: #666;
    font-size: 15px;
    margin-bottom: 32px;
  }

  .post-list {
    list-style: none;
    padding: 0;
    margin: 0;
  }

  .post-item {
    padding: 14px 0;
    border-bottom: 1px solid #eaeaea;
  }

  .post-link {
    text-decoration: none;
    color: #111;
    font-weight: 600;
  }

  .post-link:hover {
    text-decoration: underline;
  }

  .post-date {
    font-size: 13px;
    color: #888;
    margin-top: 4px;
  }
</style>

<div class="blog-wrap">
  <div class="blog-title">Blog</div>
  <div class="blog-desc">
    Technical notes & project documentation
  </div>

  <ul class="post-list">
    {% for post in site.posts %}
      <li class="post-item">
        <a class="post-link" href="{{ post.url | relative_url }}">
          {{ post.title }}
        </a>
        <div class="post-date">
          {{ post.date | date: "%Y-%m-%d" }}
        </div>
      </li>
    {% endfor %}
  </ul>
</div>

