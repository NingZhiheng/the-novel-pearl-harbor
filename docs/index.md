---
layout: home
---

{% include 00_about.md %}

------

离线下载：

* 适用于在电脑等大屏设备上阅读的 [`main.a4paper.pdf`](/uploads/main.a4paper.pdf) ；
* 适用于在手机等小屏设备上阅读的 [`main.a6paper.pdf`](/uploads/main.a6paper.pdf)。

------

{% if site.posts.size == 0 %}
  <h2>章节不存在</h2>
{% else %}
  <h2>最近章节</h2>
{% endif %}

<div class="posts">
  {% for post in paginator.posts %}
    <div class="post">
      <h3>
        <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
      </h3>

      <div clsss="meta">
        <span class="date">
          {{ post.date | date: "%Y-%m-%d" }}
        </span>

        <!-- <ul class="tag">
          {% for tag in post.tags %}
          <li>
            <a href="{{ site.url }}{{ site.baseurl }}/tags#{{ tag }}">
              {{ tag }}
            </a>
          </li>
          {% endfor %}
        </ul> -->
      </div>

      <!-- <div class="entry">
        {{ post.excerpt | truncate: 200 }}
      </div> -->

      <!-- <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Read More</a> -->
    </div>
  {% endfor %}
</div>

<div class="pagination">
  {% if paginator.previous_page %}
    <span class="prev">
      <a href="{{ site.baseurl }}{{ paginator.previous_page_path }}" class="prev">
        ← 上一页
      </a>
    </span>
  {% endif %}
  {% if paginator.next_page %}
    <span class="next">
      <a href="{{ site.baseurl}}{{ paginator.next_page_path }}" class="next">
        下一页 →
      </a>
    </span>
  {% endif %}
</div>
