---
title: Blog
permalink: /blog/
---

<style>
  :root{
    --text: #111;
    --muted: #6b7280;
    --border: #ececec;
    --card: #ffffff;
    --shadow: 0 10px 24px rgba(0,0,0,0.06);
    --accent: #2563eb; /* 포인트 컬러 (원하면 바꿔도 됨) */
  }

  .blog-wrap{
    max-width: 920px;
    margin: 0 auto;
    padding: 72px 18px;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    color: var(--text);
  }

  .blog-head{
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
    gap: 18px;
    margin-bottom: 26px;
  }

  .blog-title{
    font-size: clamp(30px, 3.2vw, 44px);
    font-weight: 850;
    letter-spacing: -0.03em;
    margin: 0;
  }

  .blog-desc{
    margin-top: 10px;
    color: var(--muted);
    font-size: 15px;
    line-height: 1.6;
    max-width: 52ch;
  }

  .pill{
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 8px 12px;
    border: 1px solid var(--border);
    border-radius: 999px;
    color: var(--muted);
    font-size: 13px;
    user-select: none;
    white-space: nowrap;
  }
  .dot{
    width: 8px; height: 8px;
    border-radius: 99px;
    background: var(--accent);
    display: inline-block;
  }

  .post-grid{
    display: grid;
    grid-template-columns: 1fr;
    gap: 12px;
    margin-top: 18px;
  }

  .post-card{
    position: relative;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 18px 18px 16px 18px;
    text-decoration: none;
    color: inherit;
    transition: transform .12s ease, box-shadow .12s ease, border-color .12s ease;
  }

  /* 좌측 얇은 포인트 라인 */
  .post-card::before{
    content: "";
    position: absolute;
    left: 0; top: 14px; bottom: 14px;
    width: 3px;
    border-radius: 999px;
    background: rgba(37,99,235,0.35);
  }

  .post-card:hover{
    transform: translateY(-1px);
    box-shadow: var(--shadow);
    border-color: rgba(0,0,0,0.10);
  }
  .post-card:hover::before{
    background: rgba(37,99,235,0.75);
  }

  .post-title{
    font-weight: 800;
    letter-spacing: -0.01em;
    line-height: 1.35;
    margin: 0 0 8px;
  }

  .post-meta{
    display: flex;
    gap: 10px;
    align-items: center;
    color: var(--muted);
    font-size: 13px;
  }

  .mini{
    border: 1px solid var(--border);
    border-radius: 999px;
    padding: 4px 10px;
    background: #fafafa;
  }

  .footer{
    margin-top: 26px;
    color: var(--muted);
    font-size: 13px;
  }
</style>

<div class="blog-wrap">
  <div class="blog-head">
    <div>
      <h1 class="blog-title">Blog</h1>
      <p class="blog-desc">Technical notes & project documentation.</p>
    </div>

    <div class="pill"><span class="dot"></span> Updated as we build</div>
  </div>

  <div class="post-grid">
    {% for post in site.posts %}
      <a class="post-card" href="{{ post.url | relative_url }}">
        <h2 class="post-title">{{ post.title }}</h2>
        <div class="post-meta">
          <span class="mini">{{ post.date | date: "%Y-%m-%d" }}</span>
          <span>Read →</span>
        </div>
      </a>
    {% endfor %}
  </div>

  <div class="footer">Total posts: {{ site.posts | size }}</div>
</div>
