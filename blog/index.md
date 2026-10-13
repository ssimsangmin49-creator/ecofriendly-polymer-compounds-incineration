---
title: Blog
permalink: /blog/
---

<style>
  .blog-wrap {
    --blog-text: #111;
    --blog-muted: #6b7280;
    --blog-border: #ececec;
    --blog-accent: #2563eb;
    --blog-card: #fff;

    max-width: 1160px;
    margin: 0 auto;
    padding: 72px 18px;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    color: var(--blog-text);
  }

  .blog-head {
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
    gap: 18px;
    margin-bottom: 32px;
  }

  .blog-title {
    font-size: clamp(30px, 3.2vw, 44px);
    font-weight: 850;
    letter-spacing: -0.03em;
    margin: 0;
  }

  .blog-desc {
    margin-top: 10px;
    color: var(--blog-muted);
    font-size: 15px;
    line-height: 1.6;
  }

  .blog-pill {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 8px 12px;
    border: 1px solid var(--blog-border);
    border-radius: 999px;
    color: var(--blog-muted);
    font-size: 13px;
    white-space: nowrap;
  }

  .blog-dot {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: var(--blog-accent);
  }

  /* Main layout */
  .blog-layout {
    display: grid;
    grid-template-columns: 240px minmax(0, 1fr);
    gap: 32px;
    align-items: start;
  }

  /* Sidebar */
  .blog-sidebar {
    background: #fafafa;
    border: 1px solid var(--blog-border);
    border-radius: 16px;
    padding: 22px 16px;
    position: sticky;
    top: 24px;
  }

  .blog-sidebar h3 {
    font-size: 12px;
    font-weight: 800;
    letter-spacing: .1em;
    color: var(--blog-muted);
    margin: 0 0 18px 10px;
  }

  .blog-category {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    gap: 8px;
    padding: 11px 10px;
    border: 0;
    border-radius: 9px;
    background: transparent;
    color: #374151;
    font: inherit;
    font-size: 14px;
    text-align: left;
    cursor: pointer;
    transition: background .15s ease;
  }

  .blog-category:hover {
    background: #eef2ff;
  }

  .blog-category.active {
    background: #e8efff;
    color: #1d4ed8;
    font-weight: 750;
  }

  .blog-count {
    flex-shrink: 0;
    font-size: 12px;
    color: #6b7280;
    background: #fff;
    border: 1px solid #e5e7eb;
    border-radius: 999px;
    padding: 2px 8px;
  }

  /* Post area */
  .blog-content {
    min-width: 0;
  }

  .blog-content-head {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 12px;
    margin-bottom: 18px;
    padding-bottom: 14px;
    border-bottom: 1px solid var(--blog-border);
  }

  .blog-current {
    font-size: 19px;
    font-weight: 800;
    margin: 0;
  }

  .blog-result {
    color: var(--blog-muted);
    font-size: 13px;
  }

  .post-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 12px;
  }

  .post-card {
    position: relative;
    display: block;
    background: var(--blog-card);
    border: 1px solid var(--blog-border);
    border-radius: 16px;
    padding: 18px 18px 16px;
    text-decoration: none;
    color: inherit;
    transition: transform .12s ease,
                box-shadow .12s ease,
                border-color .12s ease;
  }

  .post-card::before {
    content: "";
    position: absolute;
    left: 0;
    top: 14px;
    bottom: 14px;
    width: 3px;
    border-radius: 999px;
    background: rgba(37,99,235,.35);
  }

  .post-card:hover {
    transform: translateY(-1px);
    box-shadow: 0 10px 24px rgba(0,0,0,.06);
    border-color: rgba(0,0,0,.10);
  }

  .post-card:hover::before {
    background: rgba(37,99,235,.75);
  }

  .post-title {
    font-weight: 800;
    font-size: 18px;
    letter-spacing: -.01em;
    line-height: 1.35;
    margin: 0 0 10px;
  }

  .post-meta {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    align-items: center;
    color: var(--blog-muted);
    font-size: 13px;
  }

  .blog-mini {
    border: 1px solid var(--blog-border);
    border-radius: 999px;
    padding: 4px 10px;
    background: #fafafa;
  }

  .blog-post-category {
    color: #2563eb;
    font-size: 12px;
  }

  .blog-empty {
    padding: 32px 12px;
    color: var(--blog-muted);
    text-align: center;
  }

  .blog-footer {
    margin-top: 26px;
    color: var(--blog-muted);
    font-size: 13px;
  }

  [hidden] {
    display: none !important;
  }

  @media (max-width: 760px) {
    .blog-wrap {
      padding: 40px 16px;
    }

    .blog-layout {
      grid-template-columns: 1fr;
      gap: 22px;
    }

    .blog-sidebar {
      position: static;
    }

    .blog-head {
      align-items: flex-start;
      flex-direction: column;
    }
  }
</style>

<div class="blog-wrap">

  <div class="blog-head">
    <div>
      <h1 class="blog-title">Blog</h1>
      <p class="blog-desc">
        Technical notes & project documentation.
      </p>
    </div>

    <div class="blog-pill">
      <span class="blog-dot"></span>
      Updated as we build
    </div>
  </div>

  <div class="blog-layout">

    <!-- SIDEBAR -->
    <aside class="blog-sidebar" aria-label="Blog categories">

      <h3>CATEGORIES</h3>

      <button class="blog-category active"
              type="button"
              data-category="all"
              aria-pressed="true">
        <span>All Posts</span>
        <span class="blog-count">{{ site.posts | size }}</span>
      </button>

      {% assign sorted_categories = site.categories | sort %}

      {% for category in sorted_categories %}
        {% assign category_name = category[0] %}
        {% assign category_posts = category[1] %}

        <button class="blog-category"
                type="button"
                data-category="{{ category_name | escape }}"
                aria-pressed="false">
          <span>{{ category_name | replace: "-", " " | escape }}</span>
          <span class="blog-count">{{ category_posts | size }}</span>
        </button>
      {% endfor %}

    </aside>

    <!-- POSTS -->
    <main class="blog-content">

      <div class="blog-content-head">
        <h2 class="blog-current" id="blog-current">
          All Posts
        </h2>
        <span class="blog-result" id="blog-result">
          {{ site.posts | size }} posts
        </span>
      </div>

      <div class="post-grid" id="blog-posts">

        {% for post in site.posts %}

          <a class="post-card"
             href="{{ post.url | relative_url }}"
             data-categories="{{ post.categories | join: '|' | escape }}">

            <h2 class="post-title">{{ post.title }}</h2>

            <div class="post-meta">
              <span class="blog-mini">
                {{ post.date | date: "%Y-%m-%d" }}
              </span>

              {% for category in post.categories %}
                <span class="blog-post-category">
                  {{ category | replace: "-", " " }}
                </span>
              {% endfor %}

              <span>Read →</span>
            </div>

          </a>

        {% endfor %}

      </div>

      <div class="blog-empty" id="blog-empty" hidden>
        No posts found in this category.
      </div>

      <div class="blog-footer">
        Total posts: {{ site.posts | size }}
      </div>

    </main>

  </div>
</div>

<script>
(function () {
  const buttons = document.querySelectorAll(".blog-category");
  const posts = document.querySelectorAll(".post-card");
  const current = document.getElementById("blog-current");
  const result = document.getElementById("blog-result");
  const empty = document.getElementById("blog-empty");

  if (!buttons.length || !current || !result || !empty) return;

  function selectCategory(category, label) {
    let visible = 0;

    posts.forEach(function (post) {
      const categories = (post.dataset.categories || "")
        .split("|")
        .filter(Boolean);

      const show = category === "all" ||
                   categories.includes(category);

      post.hidden = !show;
      if (show) visible++;
    });

    buttons.forEach(function (button) {
      const active = button.dataset.category === category;
      button.classList.toggle("active", active);
      button.setAttribute("aria-pressed", String(active));
    });

    current.textContent = label;
    result.textContent = visible + (visible === 1 ? " post" : " posts");
    empty.hidden = visible !== 0;
  }

  buttons.forEach(function (button) {
    button.addEventListener("click", function () {
      const label = button.querySelector("span").textContent.trim();
      selectCategory(button.dataset.category, label);
    });
  });
})();
</script>
