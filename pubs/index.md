---
title: Publications
description: Journal articles, conference papers, and works in progress from the SPS Lab.
nav:
  order: 3
  tooltip: 논문
---

{%- comment -%}
이 페이지의 내용은 \_data/publications.yaml 에서 자동으로 만들어집니다.
논문을 추가/수정/삭제하려면 \_data/publications.yaml 만 고치면 되고,
상단의 개수(숫자)도 자동으로 다시 계산됩니다. 이 파일은 보통 건드릴 필요가 없습니다.
{%- endcomment -%}

<h1><i class="fas fa-book-open section-icon"></i> Publications</h1>

<nav class="jump-nav">
  <a class="jump" href="#wip">Works in Progress <span class="jump_count">{{ site.data.publications.wip | size }}</span></a>
  <a class="jump" href="#intl">International <span class="jump_count">{{ site.data.publications.journal_intl | size }}</span></a>
  <a class="jump" href="#domestic">Domestic <span class="jump_count">{{ site.data.publications.journal_dom | size }}</span></a>
  <a class="jump" href="#intl-conf">Int'l Conferences <span class="jump_count">{{ site.data.publications.conf_intl | size }}</span></a>
  <a class="jump" href="#dom-conf">Domestic Conferences <span class="jump_count">{{ site.data.publications.conf_dom | size }}</span></a>
</nav>

{% include section.html %}

<div class="sec-head">
  <h2 id="wip">Works in Progress</h2>
</div>

<ol class="pubs">
{%- for pub in site.data.publications.wip %}
  <li><div>
    <div class="pub_title">{{ pub.title }}</div>
    {%- if pub.status == "accepted" %}
    <div class="pub_meta"><span class="pub_tag">accepted</span></div>
    {%- elsif pub.status == "review" %}
    <div class="pub_meta"><span class="pub_tag is-review">under review</span></div>
    {%- endif %}
  </div></li>
{%- endfor %}
</ol>

{% include section.html %}

<div class="sec-head">
  <h2 id="intl">International Publications</h2>
</div>

<ol class="pubs">
{%- for pub in site.data.publications.journal_intl %}
  <li><div>
    <div class="pub_title">{{ pub.title }}</div>
    <div class="pub_meta">{% include pub-authors.html list=pub.authors %} · <span class="venue">{{ pub.venue }}</span> {{ pub.detail }}</div>
    {%- if pub.doi %}
    <a class="pub_link" href="https://doi.org/{{ pub.doi }}">on-line link <i class="fas fa-up-right-from-square"></i></a>
    {%- endif %}
  </div></li>
{%- endfor %}
</ol>

{% include section.html %}

<div class="sec-head">
  <h2 id="domestic">Domestic Publications</h2>
</div>

<ol class="pubs">
{%- for pub in site.data.publications.journal_dom %}
  <li><div>
    <div class="pub_title">{{ pub.title }}</div>
    <div class="pub_meta">{% include pub-authors.html list=pub.authors %} · <span class="venue">{{ pub.venue }}</span> {{ pub.detail }}</div>
    {%- if pub.doi %}
    <a class="pub_link" href="https://doi.org/{{ pub.doi }}">on-line link <i class="fas fa-up-right-from-square"></i></a>
    {%- endif %}
  </div></li>
{%- endfor %}
</ol>

{% include section.html %}

<div class="sec-head">
  <h2 id="intl-conf">International Conferences</h2>
</div>

<ol class="pubs">
{%- for pub in site.data.publications.conf_intl %}
  <li><div class="pub_conf"><span class="ptitle">{{ pub.title }}</span> · {% include pub-authors.html list=pub.authors %} · <span class="venue">{{ pub.venue }}</span>, {{ pub.detail }}</div></li>
{%- endfor %}
</ol>

{% include section.html %}

<div class="sec-head">
  <h2 id="dom-conf">Domestic Conferences</h2>
</div>

<ol class="pubs">
{%- for pub in site.data.publications.conf_dom %}
  <li><div class="pub_conf"><span class="ptitle">{{ pub.title }}</span> · {% include pub-authors.html list=pub.authors %} · <span class="venue">{{ pub.venue }}</span>, {{ pub.detail }}</div></li>
{%- endfor %}
</ol>
