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
  .post { max-width: 1100px !important; }
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
  .notes-list li { border-top: 1px solid #e3ddd2; margin: 0; }
  .notes-list li:last-child { border-bottom: 1px solid #e3ddd2; }
  .note-row {
    display: grid; grid-template-columns: 1fr 300px; gap: 3rem; align-items: center;
    padding: 2.4rem 0; text-decoration: none; color: inherit; text-align: left;
  }
  .note-item-date {
    font-family: Roboto, "Helvetica Neue", sans-serif;
    font-size: 1.2rem; color: #8b8577; letter-spacing: .08em; text-transform: uppercase;
  }
  .note-item-title {
    font-family: "Newsreader", Georgia, serif;
    margin: .5rem 0 0; font-size: 2.9rem; line-height: 1.15; font-weight: 500;
    color: #1c252e; transition: color .15s ease;
  }
  .note-row:hover .note-item-title { color: #477dca; }
  .note-item-lead { font-style: italic; font-size: 1.75rem; color: #55606b; margin: .6rem 0 0; line-height: 1.45; }
  .note-thumb {
    width: 300px; aspect-ratio: 3 / 2; border-radius: 6px; overflow: hidden;
    background: #f0ece3; border: 1px solid #e3ddd2;
  }
  .note-thumb img {
    width: 100%; height: 100%; object-fit: cover; display: block;
    transition: transform .3s ease;
  }
  .note-row:hover .note-thumb img { transform: scale(1.04); }
  @media (max-width: 720px) {
    .note-row { grid-template-columns: 1fr; gap: 1.4rem; }
    .note-thumb { width: 100%; }
  }
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
      <a class="note-row" href="{{ post.url | relative_url }}">
        <div>
          <span class="note-item-date">{{ post.date | date: "%B %-d, %Y" }}</span>
          <h2 class="note-item-title">{{ post.title }}</h2>
          {% if post.lead %}<p class="note-item-lead">{{ post.lead }}</p>{% endif %}
        </div>
        {% if post.thumb %}
        <div class="note-thumb"><img src="{{ post.thumb | relative_url }}" alt="" loading="lazy"></div>
        {% endif %}
      </a>
    </li>
    {% endfor %}
  </ul>

  <p class="notes-back"><a href="/">&larr; Back to home</a></p>
</div>
