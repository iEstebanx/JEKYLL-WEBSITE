---
layout: default
title: Blog
permalink: /blog/
---

<div class="mx-auto max-w-5xl">
  <header class="mb-8">
    <h1 class="text-3xl font-semibold tracking-tight sm:text-4xl">Blog</h1>
    <p class="mt-2 text-white/70">Posts and updates powered by Jekyll.</p>
  </header>

  <div class="grid gap-4 sm:grid-cols-2">
    {% for post in site.posts %}
      <a href="{{ post.url | relative_url }}"
         class="rounded-2xl border border-white/10 bg-white/5 p-6 hover:bg-white/10">
        <p class="text-xs text-white/60">{{ post.date | date: "%b %d, %Y" }}</p>
        <h2 class="mt-2 text-lg font-semibold">{{ post.title }}</h2>
        <p class="mt-2 text-sm text-white/70">{{ post.excerpt | strip_html | truncate: 160 }}</p>
      </a>
    {% endfor %}
  </div>
</div>