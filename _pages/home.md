---
layout: home
title: Home
hero: Collaborate and innovate for 2 days, and unleash AI's potential for education!
permalink: /
subtitle: Team up with mentors and industry leaders to transform your AI-powered vision for education into reality.

profile:
  align: right
  image: prof_pic.jpg
  image_circular: false # crops the image to make it circular
  more_info: >
    <p>555 your office number</p>
    <p>123 your address street</p>
    <p>Your City, State 12345</p>

selected_papers: true # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page

announcements:
  enabled: true # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: true
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

{% assign cards = site.home_cards | sort: "order" %}

<section class="card-grid">
  {% for card in cards %}
    {% case card.type %}
      {% when "event" %}
        {% include cards/card_event.liquid
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
      {% when "timeline" %}
        {% include cards/card_timeline.liquid
          title=card.title
          subtitle=card.subtitle
          timeline=card.timeline %}
      {% when "whyapply" %}
        {% include cards/card_whyapply.liquid
            title=card.title
            subtitle=card.subtitle
            items=card.items %}
      {% when "prizes" %}
        {% include cards/card_prizes.liquid
            title=card.title
            subtitle=card.subtitle
            prizes=card.prizes 
            buttons=card.buttons %}
      {% else %}
        <div class="card">Unknown card type: {{ card.type }}</div>
    {% endcase %}
  {% endfor %}
  <div class="page-buttons">
    <a href="https://forms.gle/3fAafWCyVxya5jf6A" class="btn primary">Register</a>
    <a href="https://forms.gle/hJ5BtdgpaFLxFvap6" class="btn secondary">Contact Us</a>
  </div>
</section>