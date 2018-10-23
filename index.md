---
layout: main
---

<main class="home" id="post" role="main" itemprop="mainContentOfPage" itemscope="itemscope" itemtype="http://schema.org/Blog">
    <div id="grid" class="row flex-grid">
    {% for post in site.demonstrations%}
            <article class="box-item" itemscope="itemscope" itemtype="http://schema.org/BlogPosting" itemprop="blogPost">
                <div class="box-body">
                <div>
                    <a class="post-link post-title" href="{{ post.url | prepend: site.baseurl }}">
                        <h2 class="post-title" itemprop="name">
                        {{ post.title }}
                        </h2>
                    </a>
                    <div class="tags">
                        <a class="demo" href="{{ post.demo_url }}">Demonstration</a>
                    </div>
                </div>
                    {% if post.image %}
                        <div class="cover">
                            {% include new-post-tag.html date=post.date %}
                            <a href="{{ post.url | prepend: site.baseurl }}" {%if isnewpost %}class="new-post"{% endif %}>
                                <img src="assets/img/placeholder.png" data-url="{{ post.image }}" class="preload">
                            </a>
                        </div>
                    {% endif %}
                    <div class="box-info">
                        <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">
                            <p class="description">{{ post.introduction }}</p>
                        </a>
                        <div class="tags">
                            {% for tag in post.tags %}
                                <a href="{{ site.baseurl}}/tags/#{{tag | slugify }}">{{ tag }}</a>
                            {% endfor %}
                        </div>
                    </div>
                </div>
            </article>
        {% endfor %}
    </div>
</main>
