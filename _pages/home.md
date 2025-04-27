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
          title=card.title
          location=card.location
          when=card.when
          tag=card.tag
          text=card.text %}
      {% when "basic" %}
        {% include cards/card_basic.liquid
          title=card.title
          text=card.text %}
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

<section>
<form action="https://formsubmit.co/YOUR_EMAIL_HERE" method="POST" class="contact-form">
  <h2><strong>Contact Us</strong></h2>
  <p>Have questions or need more information? Reach out to us!</p>
  
  <label for="name">Name</label>
  <input type="text" name="name" id="name" placeholder="Your Name" required>

  <label for="email">Email</label>
  <input type="email" name="email" id="email" placeholder="Your Email" required>

  <label for="message">Message</label>
  <textarea name="message" id="message" rows="3" placeholder="Your Message" required></textarea>

  <!-- Optional fields -->
  <input type="hidden" name="_next" value="{{ site.url }}{{ site.baseurl }}/thanks/">
  <input type="hidden" name="_captcha" value="false">
  <input type="text" name="_honey" style="display:none">

  <button type="submit">Send Message</button>
</form>
</section>