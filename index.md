---
layout: home
title: Home
projects:
- title: emoji.lgbt
  link: https://emoji.lgbt
  tagline: Pride themed emojis for Discord/Slack
- title: p-noun
  link: https://github.com/Tschrock/p-noun
  tagline: Custom HTML elements for pronouns
- title: MineLittlePony-Bedrock
  link: https://github.com/Tschrock/MineLittlePony-Bedrock
  tagline: "Ponies on Minecraft: Bedrock Edition"
- title: fixDeviantArt
  link: https://github.com/Tschrock/fixdeviantart
  tagline: Deviantart embed proxy for Discord/Slack
---

<div class="page-section">

## Featured Projects
<div class="project-list">
    {%- for project in site.projects -%}
        {%- if project.featured -%}
            <a class="project" href="{{ project.link | escape }}">
                <div class="project-title">{{ project.title }}</div>
                <div class="project-tagline">{{ project.tagline }}</div>
            </a>
        {%- endif -%}
    {%- endfor -%}
</div>
<a href="{% link projects.md %}">View All</a>

</div>
<div class="page-section">

## Recent Blog Posts
<ul class="post-list">
    {%- for post in site.posts limit:8 -%}
        <li>
            <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
            -
            <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
        </li>
    {%- endfor -%}
</ul>
<a href="{% link blog.md %}">View All</a>

</div>
