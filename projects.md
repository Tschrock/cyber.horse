---
layout: page
title: Projects
permalink: /projects/
show_in_header: true
---

# Projects
<div>
    <div class="project-list">
        {%- for project in site.projects -%}
            <a class="project" href="{{ project.link | default:project.url | escape }}">
                <div class="project-title">{{ project.title }}</div>
                <div class="project-tagline">{{ project.tagline }}</div>
            </a>
        {%- endfor -%}
    </div>
</div>
