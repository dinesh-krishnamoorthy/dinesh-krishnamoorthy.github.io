---
layout: page
title: publications
permalink: /publications/
nav: true
nav_order: 3

# All entries live in _data/publications.yml
me: "Krishnamoorthy, D."
scholar: "https://scholar.google.com/citations?user=AHUrS0EAAAAJ&hl=en"
sections:
  - { key: journal,    title: "Journal Articles",  prefix: J, by_year: true }
  - { key: conference, title: "Conference Papers", prefix: C, by_year: true }
  - { key: patents,    title: "Patents",           prefix: P }
  - { key: theses,     title: "Theses" }
  - { key: media,      title: "Press, Media and Other" }
---

<style>
  .pb-wrap { --pb-accent: var(--global-theme-color, #2f6fa8); --pb-muted: var(--global-text-color-light, #6c757d); --pb-line: var(--global-divider-color, rgba(0,0,0,.12)); }
  .pb-bar { display: flex; flex-wrap: wrap; gap: .5rem; align-items: center; margin: .25rem 0 1.5rem; }
  .pb-chip { font-size: .85rem; padding: .2rem .75rem; border: 1px solid var(--pb-line); border-radius: 999px; text-decoration: none !important; color: inherit !important; }
  .pb-chip b { color: var(--pb-accent); margin-right: .2rem; }
  .pb-chip:hover { border-color: var(--pb-accent); }
  .pb-chip.pb-scholar { border-color: var(--pb-accent); color: var(--pb-accent) !important; }
  .pb-search { flex: 1 1 220px; max-width: 320px; margin-left: auto; padding: .3rem .8rem; font-size: .9rem; border: 1px solid var(--pb-line); border-radius: 999px; background: transparent; color: inherit; }
  .pb-search:focus { outline: none; border-color: var(--pb-accent); }
  .pb-empty { display: none; color: var(--pb-muted); font-style: italic; }

  .pb-wrap h2 { font-size: 1.3rem; font-weight: 600; margin: 2.25rem 0 1rem; padding-bottom: .35rem; border-bottom: 2px solid var(--pb-accent); display: inline-block; scroll-margin-top: 70px; }
  .pb-year { display: grid; grid-template-columns: 3.5rem 1fr; gap: 1.25rem; border-top: 1px solid var(--pb-line); padding-top: .6rem; margin-top: .4rem; }
  .pb-year:first-of-type { border-top: none; }
  .pb-yr { font-weight: 700; color: var(--pb-accent); font-size: 1.05rem; position: sticky; top: 64px; align-self: start; padding-top: .45rem; }
  .pb-list { list-style: none; margin: 0; padding: 0; }
  .pb { position: relative; padding: .5rem 0 .6rem 2.9rem; }
  .pb-n { position: absolute; left: 0; top: .6rem; font-size: .72rem; color: var(--pb-muted); font-variant-numeric: tabular-nums; }
  .pb-title { font-weight: 600; line-height: 1.4; }
  .pb-authors { font-size: .92rem; margin-top: .1rem; }
  .pb-authors b { font-weight: 700; text-decoration: underline; text-decoration-color: var(--pb-accent); text-underline-offset: 2px; }
  .pb-venue { font-size: .9rem; color: var(--pb-muted); }
  .pb-venue i { color: var(--global-text-color, inherit); opacity: .85; }
  .pb-meta { margin-top: .3rem; display: flex; flex-wrap: wrap; gap: .3rem; align-items: center; }
  .pb-tag { font-size: .68rem; font-weight: 600; letter-spacing: .03em; padding: .05rem .5rem; border-radius: 999px; }
  .pb-award  { color: #a86f00; background: color-mix(in srgb, #c48a00 15%, transparent); }
  .pb-note   { color: #7c4dcc; background: color-mix(in srgb, #7c4dcc 13%, transparent); }
  .pb-status { color: var(--pb-muted); border: 1px dashed var(--pb-muted); }
  .pb-meta a { font-size: .72rem; padding: 0 .5rem; border: 1px solid var(--pb-line); border-radius: 4px; text-decoration: none !important; line-height: 1.7; }
  .pb-meta a:hover { border-color: var(--pb-accent); }
  .pb-flat .pb { padding-left: 0; }

  @media (max-width: 576px) {
    .pb-year { grid-template-columns: 1fr; gap: 0; }
    .pb-yr { position: static; }
    .pb { padding-left: 2.3rem; }
    .pb-search { max-width: none; margin-left: 0; }
  }
</style>

<div class="pb-wrap">

  <div class="pb-bar">
    {% for s in page.sections %}{% assign n = site.data.publications[s.key] | size %}{% if n > 0 and s.prefix %}
    <a class="pb-chip" href="#{{ s.key }}"><b>{{ n }}</b>{{ s.title | downcase }}</a>
    {% endif %}{% endfor %}
    <a class="pb-chip pb-scholar" href="{{ page.scholar }}" target="_blank" rel="noopener">Google Scholar ↗</a>
    <input class="pb-search" type="search" placeholder="Search title, author, venue…" aria-label="Search publications">
  </div>
  <p class="pb-empty">No publications match your search.</p>

{% assign me_bold = "<b>" | append: page.me | append: "</b>" %}
{% for s in page.sections %}
  {% assign items = site.data.publications[s.key] %}
  {% assign total = items | size %}
  {% if total == 0 %}{% continue %}{% endif %}
  <section class="pb-section" id="{{ s.key }}">
  <h2>{{ s.title }}</h2>

  {% if s.by_year %}{% assign groups = items | group_by: "year" %}{% else %}{% assign groups = "" | split: "" %}{% endif %}
  {% assign k = total | plus: 1 %}

  {% if s.by_year %}
    {% for g in groups %}
    <div class="pb-year">
      <div class="pb-yr">{{ g.name }}</div>
      <ol class="pb-list">
      {% for p in g.items %}{% assign k = k | minus: 1 %}
        <li class="pb">
          <span class="pb-n">[{{ s.prefix }}{{ k }}]</span>
          <div class="pb-title">{{ p.title }}</div>
          <div class="pb-authors">{{ p.authors | replace: page.me, me_bold }}</div>
          <div class="pb-venue"><i>{{ p.venue }}</i>{% if p.details %}, {{ p.details }}{% endif %}</div>
          {% if p.award or p.note or p.status or p.links %}<div class="pb-meta">
            {% if p.award %}<span class="pb-tag pb-award">★ {{ p.award }}</span>{% endif %}
            {% if p.note %}<span class="pb-tag pb-note">{{ p.note }}</span>{% endif %}
            {% if p.status %}<span class="pb-tag pb-status">{{ p.status }}</span>{% endif %}
            {% for l in p.links %}<a href="{{ l[1] }}" target="_blank" rel="noopener">{{ l[0] }}</a>{% endfor %}
          </div>{% endif %}
        </li>
      {% endfor %}
      </ol>
    </div>
    {% endfor %}

  {% else %}
    <ol class="pb-list{% unless s.prefix %} pb-flat{% endunless %}">
    {% for p in items %}{% assign k = k | minus: 1 %}
      <li class="pb">
        {% if s.prefix %}<span class="pb-n">[{{ s.prefix }}{{ k }}]</span>{% endif %}
        {% if p.text %}
          <div>{{ p.text | markdownify | remove: "<p>" | remove: "</p>" }}</div>
        {% else %}
          <div class="pb-title">{{ p.title }}</div>
          <div class="pb-authors">{{ p.authors | replace: page.me, me_bold }}</div>
          <div class="pb-venue"><i>{{ p.venue }}</i>{% if p.year %} ({{ p.year }}){% endif %}</div>
        {% endif %}
        {% if p.award or p.note or p.status or p.links %}<div class="pb-meta">
          {% if p.award %}<span class="pb-tag pb-award">★ {{ p.award }}</span>{% endif %}
          {% if p.note %}<span class="pb-tag pb-note">{{ p.note }}</span>{% endif %}
          {% if p.status %}<span class="pb-tag pb-status">{{ p.status }}</span>{% endif %}
          {% for l in p.links %}<a href="{{ l[1] }}" target="_blank" rel="noopener">{{ l[0] }}</a>{% endfor %}
        </div>{% endif %}
      </li>
    {% endfor %}
    </ol>
  {% endif %}
  </section>
{% endfor %}
</div>

<script>
  (function () {
    var box = document.querySelector(".pb-search"); if (!box) return;
    box.addEventListener("input", function () {
      var q = box.value.trim().toLowerCase(), any = false;
      document.querySelectorAll(".pb-section").forEach(function (sec) {
        var secHit = false;
        sec.querySelectorAll(".pb").forEach(function (li) {
          var hit = !q || li.textContent.toLowerCase().indexOf(q) !== -1;
          li.style.display = hit ? "" : "none"; if (hit) secHit = true;
        });
        sec.querySelectorAll(".pb-year").forEach(function (y) {
          y.style.display = y.querySelector('.pb:not([style*="none"])') ? "" : "none";
        });
        sec.style.display = secHit ? "" : "none"; if (secHit) any = true;
      });
      document.querySelector(".pb-empty").style.display = any ? "none" : "block";
    });
  })();
</script>
