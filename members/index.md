---
title: Members
description: People of the Smart Production Systems Lab at Soongsil University.
nav:
  order: 2
  tooltip: Members
footer: images/banner_ssu.jpg
header: images/banner_ssu.jpg
footer-dark: true
---

<h1><i class="fas fa-users section-icon"></i> Members</h1>

{% include section.html %}

<div class="sec-head">
  <h2>Professor</h2>
</div>

{%
  include list.html
  data="members"
  component="portrait"
  filters="role: prof"
%}

{% include section.html %}

<div class="sec-head">
  <h2>Graduate Students</h2>
</div>

{%
  include list.html
  data="members"
  component="portrait"
  filters="role: grad"
%}

{% include section.html %}

<div class="sec-head">
  <h2>Undergraduate Researchers</h2>
</div>

{%
  include list.html
  data="members"
  component="portrait"
  filters="role: ug"
%}

{% include section.html %}

<div class="sec-head">
  <h2>Past Members</h2>
</div>

<div class="alumni">
  <div class="alumni-cohort">
    <span class="alumni-period">2023.07 – 2024.12</span>
    <span class="alumni-names">강민규 · 이보성 · 민동욱</span>
  </div>
  <div class="alumni-cohort">
    <span class="alumni-period">2025.01 – 2025.12</span>
    <span class="alumni-names">이혁진 · 최민영 · 조정운 · 손성은</span>
  </div>
</div>
