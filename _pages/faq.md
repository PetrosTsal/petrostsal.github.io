---
layout: home
title: FAQ
permalink: /faq/
nav: true
nav_order: 3
---

<h1>Frequently Asked Questions (FAQ)</h1>

{% assign faqs = site.faq_cards | sort: "order" %}

<div class="faq-list">
  {% for faq in faqs %}
    {% include cards/card_faq.liquid
      title=faq.title
      answer=faq.answer
      index=forloop.index %}
  {% endfor %}
</div>