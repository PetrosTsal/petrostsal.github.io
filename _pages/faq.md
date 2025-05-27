---
layout: home
title: FAQ
permalink: /faq/
nav: true
nav_order: 3
---
<div class="container card">
  <h1>FAQ</h1>

  {% assign faqs = site.faq_cards | sort: "order" %}

  <div class="faq-list">
    {% for faq in faqs %}
      {% include cards/card_faq.liquid
        title=faq.title
        answer=faq.answer
        index=forloop.index %}
    {% endfor %}
  </div>
  <div class="page-buttons">
      <a href="" class="btn primary">Register</a>
      <a href="" class="btn secondary">Contact Us</a>
  </div>
</div>