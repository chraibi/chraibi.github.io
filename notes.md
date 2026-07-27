---
layout: page
title: "Field Notes"
permalink: /notes/
description: "Short notes from the road — workshops, meetings, and things worth writing down."
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Newsreader:ital,opsz,wght@0,6..72,400..700;1,6..72,400..700&display=swap" rel="stylesheet">

<style>
  .post-header { display: none; }
  .page-content { background: #fdfcf9; }
  .notes-index { font-family: "Newsreader", Georgia, serif; color: #26313b; padding: 2rem 0 3rem; }
  .notes-kicker {
    font-family: Roboto, "Helvetica Neue", sans-serif;
    font-size: 1.15rem; letter-spacing: .22em; text-transform: uppercase;
    color: #477dca; display: flex; align-items: center; gap: 1rem; margin: 0;
  }
  .notes-kicker::after { content: ""; flex: 1; height: 1px; background: #e3ddd2; }
  .notes-index h1 {
    font-family: "Newsreader", Georgia, serif; font-weight: 500;
    font-size: 4.4rem; letter-spacing: -0.015em; color: #1c252e;
    margin: 1rem 0 0; line-height: 1.1;
  }
  .notes-intro { font-style: italic; font-size: 1.9rem; color: #55606b; margin: 1.2rem 0 0; line-height: 1.5; }
  .notes-list { list-style: none; margin: 3.5rem 0 0; padding: 0; }
  .notes-list li { border-top: 1px solid #e3ddd2; padding: 2.2rem 0; margin: 0; }
  .notes-list li:last-child { border-bottom: 1px solid #e3ddd2; }
  .note-item-date {
    font-family: Roboto, "Helvetica Neue", sans-serif;
    font-size: 1.2rem; color: #8b8577; letter-spacing: .08em; text-transform: uppercase;
  }
  .note-item-title { margin: .4rem 0 0; font-size: 2.7rem; line-height: 1.2; font-weight: 500; }
  .note-item-title a { color: #1c252e; text-decoration: none; }
  .note-item-title a:hover { color: #477dca; }
  .note-item-lead { font-style: italic; font-size: 1.75rem; color: #55606b; margin: .5rem 0 0; }
  .notes-back { font-family: Roboto, "Helvetica Neue", sans-serif; font-size: 1.3rem; margin-top: 3rem; }
  .notes-back a { color: #477dca; text-decoration: none; }
  .notes-back a:hover { text-decoration: underline; }
</style>

<div class="notes-index">
  <p class="notes-kicker">Field Notes</p>
  <h1>Field Notes</h1>
  <p class="notes-intro">Short notes from the road — workshops, meetings, and things worth writing down.</p>

  <ul class="notes-list">
    {% for post in site.posts %}
    <li>
      <span class="note-item-date">{{ post.date | date: "%B %-d, %Y" }}</span>
      <h2 class="note-item-title"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      {% if post.lead %}<p class="note-item-lead">{{ post.lead }}</p>{% endif %}
    </li>
    {% endfor %}
  </ul>

  <p class="notes-back"><a href="/">&larr; Back to home</a></p>
</div>
