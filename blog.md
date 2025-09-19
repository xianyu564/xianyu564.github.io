---
layout: default
title: "博客"
permalink: /blog/
---

# 博客

欢迎访问我的个人博客，这里分享我在学术研究、技术开发和日常思考方面的文章。

## 最新文章

{% assign posts = site.posts | sort: 'date' | reverse %}
{% for post in posts limit:5 %}
<div class="post-preview">
  <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
  <p class="post-meta">
    <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y年%m月%d日" }}</time>
    {% if post.tags and post.tags.size > 0 %}
      <span class="tags">
        {% for tag in post.tags %}
          <span class="tag">{{ tag }}</span>
        {% endfor %}
      </span>
    {% endif %}
  </p>
  <p class="post-excerpt">{{ post.excerpt | strip_html | truncatewords: 50 }}</p>
  <p><a href="{{ post.url | relative_url }}">阅读全文 →</a></p>
</div>
<hr>
{% endfor %}

## 按年份归档

{% assign posts_by_year = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}
{% for year in posts_by_year %}
<div class="year-archive">
  <h3>{{ year.name }}年</h3>
  <ul class="post-list">
    {% for post in year.items %}
    <li>
      <span class="post-date">{{ post.date | date: "%m-%d" }}</span>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      {% if post.tags and post.tags.size > 0 %}
        <span class="post-tags">
          {% for tag in post.tags %}
            <span class="tag">{{ tag }}</span>
          {% endfor %}
        </span>
      {% endif %}
    </li>
    {% endfor %}
  </ul>
</div>
{% endfor %}

{% if site.posts.size == 0 %}
<div class="no-posts">
  <p>暂无博客文章，敬请期待！</p>
</div>
{% endif %}

---

## 标签云

{% assign all_tags = site.posts | map: 'tags' | flatten | uniq | sort %}
{% if all_tags.size > 0 %}
<div class="tag-cloud">
  {% for tag in all_tags %}
    {% assign tag_posts = site.posts | where_exp: "post", "post.tags contains tag" %}
    <a href="#" class="tag-link" data-tag="{{ tag }}">{{ tag }} ({{ tag_posts.size }})</a>
  {% endfor %}
</div>
{% endif %}

<style>
.post-preview {
  margin-bottom: 30px;
}

.post-preview h3 {
  margin-bottom: 5px;
}

.post-preview h3 a {
  color: #2c3e50;
  text-decoration: none;
}

.post-preview h3 a:hover {
  color: #0366d6;
}

.post-meta {
  color: #666;
  font-size: 0.9em;
  margin-bottom: 10px;
}

.post-excerpt {
  color: #555;
  line-height: 1.6;
  margin-bottom: 10px;
}

.year-archive {
  margin-bottom: 30px;
}

.year-archive h3 {
  color: #2c3e50;
  border-bottom: 2px solid #e1e5e9;
  padding-bottom: 5px;
}

.post-list {
  list-style: none;
  padding: 0;
}

.post-list li {
  margin-bottom: 8px;
  display: flex;
  align-items: center;
  gap: 10px;
}

.post-date {
  color: #666;
  font-size: 0.9em;
  min-width: 40px;
}

.post-list a {
  color: #2c3e50;
  text-decoration: none;
  flex: 1;
}

.post-list a:hover {
  color: #0366d6;
}

.tags, .post-tags {
  margin-left: 10px;
}

.tag {
  background: #f1f3f4;
  color: #666;
  padding: 2px 6px;
  border-radius: 3px;
  font-size: 0.8em;
  margin-right: 5px;
}

.tag-cloud {
  margin-top: 20px;
}

.tag-link {
  display: inline-block;
  background: #f8f9fa;
  color: #495057;
  padding: 4px 8px;
  margin: 4px;
  border-radius: 4px;
  text-decoration: none;
  font-size: 0.9em;
}

.tag-link:hover {
  background: #e9ecef;
  color: #0366d6;
}

.no-posts {
  text-align: center;
  color: #666;
  font-style: italic;
  margin: 40px 0;
}
</style>