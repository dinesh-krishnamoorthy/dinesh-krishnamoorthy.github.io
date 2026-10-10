---
layout: page
title: teaching
permalink: /teaching/
nav: true
nav_order: 4
description: Courses I teach and have taught. Click a course to see its lecture material.
---


{% comment %} All course data lives in _data/teaching.yml {% endcomment %}

<style>
.tc { --tc-accent: var(--global-theme-color, #2f6fa8); --tc-muted: var(--global-text-color-light, #6c757d); --tc-line: var(--global-divider-color, rgba(0,0,0,.12)); --tc-card: var(--global-card-bg-color, transparent); }
.tc h2 { font-size: 1.3rem; font-weight: 600; margin: 2.25rem 0 1rem; padding-bottom: .35rem; border-bottom: 2px solid var(--tc-accent); display: inline-block; }
.tc h2:first-child { margin-top: .5rem; }
.tc-list { display: flex; flex-direction: column; gap: .75rem; }
.tc-course { border: 1px solid var(--tc-line); border-radius: 8px; background: var(--tc-card); transition: border-color .15s; }
.tc-course.tc-current { border-left: 4px solid var(--tc-accent); }
details.tc-course[open], details.tc-course:hover { border-color: var(--tc-accent); }
.tc-head { display: grid; grid-template-columns: 6.2rem 1fr auto 1rem; align-items: center; gap: 1rem; padding: .9rem 1.1rem; list-style: none; }
details > .tc-head { cursor: pointer; user-select: none; }
.tc-head::-webkit-details-marker { display: none; }
.tc-code { font-family: var(--global-code-font, ui-monospace, SFMono-Regular, Menlo, monospace); font-weight: 700; color: var(--tc-accent); font-size: .95rem; }
.tc-title { font-weight: 600; line-height: 1.35; }
.tc-meta { font-size: .85rem; color: var(--tc-muted); margin-top: .1rem; }
.tc-pill { display: inline-block; font-size: .7rem; padding: 0 .45rem; border: 1px solid var(--tc-line); border-radius: 999px; margin-left: .35rem; vertical-align: .1em; }
.tc-right { text-align: right; white-space: nowrap; font-size: .85rem; color: var(--tc-muted); }
.tc-right .tc-count { display: block; font-size: .75rem; color: var(--tc-accent); }
.tc-chev { color: var(--tc-accent); text-align: center; transition: transform .2s; }
details[open] > .tc-head .tc-chev { transform: rotate(180deg); }
.tc-body { padding: 0 1.1rem 1rem calc(1.1rem + 7.2rem); border-top: 1px dashed var(--tc-line); padding-top: .9rem; }
.tc-body p { margin: 0 0 .6rem; }
.tc-note { font-size: .9rem; color: var(--tc-muted); }
.tc-mat { list-style: none; margin: .25rem 0 0; padding: 0; counter-reset: tc; }
.tc-mat li { display: flex; align-items: baseline; gap: .75rem; padding: .4rem 0; border-bottom: 1px solid var(--tc-line); }
.tc-mat li:last-child { border-bottom: none; }
.tc-mat li::before { counter-increment: tc; content: counter(tc, decimal-leading-zero); font-size: .75rem; color: var(--tc-muted); font-variant-numeric: tabular-nums; min-width: 1.4rem; }
.tc-mat .t { flex: 1; }
.tc-btn { font-size: .75rem; padding: .05rem .6rem; border: 1px solid var(--tc-accent); border-radius: 4px; text-decoration: none !important; white-space: nowrap; }
.tc-btn:hover { background: var(--tc-accent); color: #fff !important; }
.tc-courselink { display: inline-block; margin-top: .6rem; font-size: .88rem; }
@media (max-width: 576px) {
.tc-head { grid-template-columns: 1fr auto 1rem; gap: .25rem .75rem; }
.tc-code { grid-column: 1 / -1; }
.tc-body { padding-left: 1.1rem; }
}
</style>
<div class="tc">
{% assign tc_current = site.data.teaching | where: "current", true %}
{% assign tc_past = site.data.teaching | where_exp: "c", "c.current != true" %}
{% for tc_group in (1..2) %}
{% if tc_group == 1 %}
{% assign tc_items = tc_current %}<h2>Currently teaching</h2>
{% else %}
{% assign tc_items = tc_past %}<h2>Previously taught</h2>
{% endif %}
<div class="tc-list">
{% for c in tc_items %}
{% assign tc_n = c.materials | size %}
{% if tc_n > 0 or c.note or c.about or c.link %}{% assign tc_open = true %}{% else %}{% assign tc_open = false %}{% endif %}
{% capture tc_head %}
  <div class="tc-code">{{ c.code }}</div>
  <div>
    <div class="tc-title">{{ c.title }}</div>
    <div class="tc-meta">{{ c.institution }}<span class="tc-pill">{{ c.level }}</span></div>
  </div>
  <div class="tc-right">{{ c.terms }}{% if tc_n > 0 %}<span class="tc-count">{{ tc_n }} file{% if tc_n != 1 %}s{% endif %}</span>{% endif %}</div>
{% endcapture %}

{% if tc_open %}
<details class="tc-course{% if c.current %} tc-current{% endif %}" id="{{ c.code | slugify }}">
  <summary class="tc-head">{{ tc_head }}<span class="tc-chev">▾</span></summary>
  <div class="tc-body">
    {% if c.about %}<p>{{ c.about | markdownify | remove: "<p>" | remove: "</p>" }}</p>{% endif %}
    {% if c.note %}<p class="tc-note">{{ c.note | markdownify | remove: "<p>" | remove: "</p>" }}</p>{% endif %}
    {% if tc_n > 0 %}
    <ol class="tc-mat">
      {% for m in c.materials %}
      <li>
        <span class="t">{{ m.title }}</span>
        <a class="tc-btn" href="{% if m.url contains '://' %}{{ m.url }}{% else %}{{ m.url | relative_url }}{% endif %}" target="_blank" rel="noopener">{{ m.label | default: "slides" }}</a>
      </li>
      {% endfor %}
    </ol>
    {% elsif c.note == nil %}
    <p class="tc-note">Lecture material for this course is not available online.</p>
    {% endif %}
    {% if c.link %}<a class="tc-courselink" href="{{ c.link }}" target="_blank" rel="noopener">Course page →</a>{% endif %}
  </div>
</details>
{% else %}
<div class="tc-course{% if c.current %} tc-current{% endif %}" id="{{ c.code | slugify }}">
  <div class="tc-head">{{ tc_head }}<span></span></div>
</div>
{% endif %}
​
{% endfor %}
</div>
{% endfor %}
</div>
<script>
// Opening /teaching/#ttk4135 expands that course directly.
(function () {
var el = location.hash && document.getElementById(location.hash.slice(1));
if (el && el.tagName === "DETAILS") { el.open = true; el.scrollIntoView(); }
})();
</script>
