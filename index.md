---
layout: default
title: Home
---

<div class="mx-auto max-w-5xl">
  <section class="rounded-2xl border border-white/10 bg-white/5 p-6 shadow-[0_0_0_1px_rgba(255,255,255,0.06)] sm:p-10">
    <p class="text-sm text-white/60">Static Site Generator</p>

    <h1 class="mt-3 text-3xl font-semibold tracking-tight sm:text-5xl">
      {{ site.title }}
    </h1>

    <p class="mt-4 max-w-2xl text-base text-white/70 sm:text-lg">
      A modern, fast static website built with <span class="text-white">Jekyll</span> and styled using
      <span class="text-white">Tailwind CSS</span>. Includes a <span class="text-white">Blog</span> and
      <span class="text-white">Jekyll Admin</span> for editing content in the browser.
    </p>

    <div class="mt-6 flex flex-wrap gap-2">
      <span class="rounded-full bg-white/10 px-3 py-1 text-xs text-white/80 ring-1 ring-white/10">Jekyll</span>
      <span class="rounded-full bg-white/10 px-3 py-1 text-xs text-white/80 ring-1 ring-white/10">Tailwind CSS</span>
      <span class="rounded-full bg-white/10 px-3 py-1 text-xs text-white/80 ring-1 ring-white/10">Blog</span>
      <span class="rounded-full bg-white/10 px-3 py-1 text-xs text-white/80 ring-1 ring-white/10">Jekyll Admin</span>
      <span class="rounded-full bg-white/10 px-3 py-1 text-xs text-white/80 ring-1 ring-white/10">Static Hosting Ready</span>
    </div>

    <div class="mt-8 grid gap-4 sm:grid-cols-2">
      <a href="{{ '/blog/' | relative_url }}"
         class="group rounded-xl border border-white/10 bg-white/5 p-5 transition hover:bg-white/10 hover:-translate-y-0.5">
        <div class="flex items-center justify-between">
          <h2 class="text-base font-semibold">Read the Blog</h2>
          <span class="text-white/60 transition group-hover:text-white group-hover:translate-x-0.5">→</span>
        </div>
        <p class="mt-2 text-sm text-white/70">Browse posts, updates, and notes.</p>
      </a>

      <a href="{{ '/admin/' | relative_url }}"
         class="group rounded-xl border border-white/10 bg-white/5 p-5 transition hover:bg-white/10 hover:-translate-y-0.5">
        <div class="flex items-center justify-between">
          <div>
            <h2 class="text-base font-semibold">Open Admin</h2>
            <p class="mt-1 text-xs text-white/50">Starts at Posts</p>
          </div>
          <span class="text-white/60 transition group-hover:text-white group-hover:translate-x-0.5">→</span>
        </div>
        <p class="mt-2 text-sm text-white/70">Create and edit posts using Jekyll Admin.</p>
      </a>
    </div>
  </section>

  <section class="mt-10">
    <div class="mb-4 flex items-end justify-between">
      <h2 class="text-xl font-semibold tracking-tight">Latest posts</h2>
      <a class="text-sm text-white/60 hover:text-white" href="{{ '/blog/' | relative_url }}">View all</a>
    </div>

    <div class="grid gap-4 sm:grid-cols-2">
      {% for post in site.posts limit:4 %}
      <a href="{{ post.url | relative_url }}"
         class="rounded-2xl border border-white/10 bg-white/5 p-5 transition hover:bg-white/10 hover:-translate-y-0.5">
        <p class="text-xs text-white/60">{{ post.date | date: "%b %d, %Y" }}</p>
        <h3 class="mt-2 text-base font-semibold">{{ post.title }}</h3>
        <p class="mt-2 text-sm text-white/70">{{ post.excerpt | strip_html | truncate: 140 }}</p>
      </a>
      {% endfor %}
    </div>
  </section>
</div>
