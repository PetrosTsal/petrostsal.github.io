---
layout: home
title: Agenda
permalink: /agenda/
nav: true
nav_order: 2
---

{% assign cards = site.agenda_cards | sort: "order" %}

<section class="card-grid">
  {% for card in cards %}
    {% case card.type %}
      {% when "event" %}
        {% include cards/card_event.liquid
          title=card.title
          location=card.location
          when=card.when
          tag=card.tag
          text=card.text %}
      {% when "basic" %}
        {% include cards/card_basic.liquid
          title=card.title
          text=card.text
          sec_text=card.sec_text %}
      {% when "organizers" %}
        {% include cards/card_organizers.liquid
          title=card.title
          subtitle=card.subtitle
          organizers=card.organizers %}
      {% when "keyvalue" %}
        {% include cards/card_keyvalue.liquid
          title=card.title
          subtitle=card.subtitle
          keyvalue_type=card.keyvalue_type
          items=card.items %}
      {% else %}
        <div class="card">Unknown card type: {{ card.type }}</div>
    {% endcase %}
  {% endfor %}
</section>