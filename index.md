---
title: Home
description: Smart Production Systems Lab at Soongsil University
nav:
  order: 0
  tooltip: Home
---

{% include section.html full=true %}

<div class="hero">
  <div class="hero_inner">
    <div class="hero_eyebrow">Smart Production Systems Lab · Soongsil University</div>
    <h1 class="hero_title">We Optimize.</h1>
    <div class="hero_subtitle">최적화와 애널리틱스로 산업 시스템의 의사결정 문제를 풉니다</div>
    <p class="hero_text">
      숭실대학교 산업·정보시스템공학과 <strong>스마트 생산시스템(SPS) 연구실</strong>은
      제조, 물류, 에너지, 서비스 등 다양한 산업 시스템에서 발생하는 의사결정 문제를
      <strong>정수최적화</strong>와 <strong>불확실성 하에서의 순차적 의사결정</strong> 방법론으로
      해결하고 가치를 창출하기 위한 연구를 수행합니다.
    </p>
    <div class="hero_actions">
      <a class="btn btn--solid" href="{{ '/research/' | relative_url }}"><i class="fas fa-lightbulb"></i> 연구 분야 보기</a>
      <a class="btn btn--ghost" href="{{ '/pubs/' | relative_url }}"><i class="fas fa-book-open"></i> Publications</a>
      <a class="btn btn--ghost" href="{{ '/members/' | relative_url }}"><i class="fas fa-users"></i> Members</a>
    </div>
  </div>
</div>

{% include section.html %}

<div class="eyebrow">Research</div>
## 연구 분야

<div class="highlight-grid">
  <a class="highlight-card" href="{{ '/research/' | relative_url }}">
    <div class="hc_icon"><i class="fas fa-project-diagram"></i></div>
    <div class="hc_sub">Methodology</div>
    <div class="hc_title">정수 최적화 이론 및 알고리즘</div>
  </a>
  <a class="highlight-card" href="{{ '/research/' | relative_url }}">
    <div class="hc_icon"><i class="fas fa-dice"></i></div>
    <div class="hc_sub">Methodology</div>
    <div class="hc_title">불확실성 하 순차적 의사결정</div>
  </a>
  <a class="highlight-card" href="{{ '/research/' | relative_url }}">
    <div class="hc_icon"><i class="fas fa-industry"></i></div>
    <div class="hc_sub">Application</div>
    <div class="hc_title">스마트 생산 시스템 운영</div>
  </a>
  <a class="highlight-card" href="{{ '/research/' | relative_url }}">
    <div class="hc_icon"><i class="fas fa-bolt"></i></div>
    <div class="hc_sub">Application</div>
    <div class="hc_title">에너지 시스템 최적화</div>
  </a>
  <a class="highlight-card" href="{{ '/research/' | relative_url }}">
    <div class="hc_icon"><i class="fas fa-truck"></i></div>
    <div class="hc_sub">Application</div>
    <div class="hc_title">공급망 관리</div>
  </a>
</div>

{% include section.html %}

<div class="eyebrow">Latest</div>
## 최근 소식

<div class="news-list">
{% for post in site.posts limit:4 %}
  <div class="news-item">
    <span class="news-date">{{ post.date | date: "%Y.%m" }}</span>
    <a class="news-title" href="{{ post.url | relative_url }}">{{ post.title }}</a>
  </div>
{% endfor %}
</div>

<p class="center" style="margin-top:24px;">
{% include link.html type="link" icon="fas fa-arrow-right" text="모든 소식 보기" link="/news/" flip=true %}
</p>

{% include section.html %}

<div class="cta-band">
  <div class="cta_title"><i class="fas fa-user-graduate"></i> 함께 연구할 학생을 찾습니다</div>
  <p class="cta_text">
    스마트 생산시스템 연구실에서 <strong>학부연구생 및 대학원생</strong>을 모집하고 있습니다.
    수리 최적화와 실제 운영 문제의 접점에서 연구에 관심 있는 분은 편하게 이메일로 문의해 주세요.
  </p>
  <a class="cta_email" href="mailto:younsoo.lee@ssu.ac.kr"><i class="fas fa-envelope"></i> younsoo.lee@ssu.ac.kr</a>
</div>
