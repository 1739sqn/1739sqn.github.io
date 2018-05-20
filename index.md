---
title: 1739 Squadron
---

{% comment %}
-----------------------------------------------------------------------------------

Unless you know what you're doing, you probably don't want to edit this file.

Content for sections can be found in _sections/
The border photos can be found in assets/border_photos

The following adds a title, and joins the sections together with their border photos

-----------------------------------------------------------------------------------
{% endcomment %}

<div class="hero">
  <div class="container">
    <div class="row">
      <div class="col-md-9">
        <h1 class="display-4 font-weight-normal">1739 Squadron</h1>
        <h2 class="display-5 font-weight-normal">Air Training Corps</h2>
      </div>

      <div class="col-md-3 text-right" style="margin-top: 10px">
        <img src="/logo.svg" alt="RAFAC Logo" />
      </div>
    </div>
  </div>
</div>

{% for section in site.sections %}
  {% assign title_slug = section.title | slugify %}

  <section id="{{ title_slug }}" class="section {{ section.classes }}">
    <div class="container">
      <div class="row">
        <div class="col-md-12">
          <h2 class="text-center">
            {{ section.title }}
          </h2>

          {{ section.content }}
        </div>
      </div>
    </div>
  </section>

  <div class="border-photos">
    <div class="container">
      {% assign border_photos = 'border_photos/' | append: title_slug %}

      <div class="row">
        {% for image in site.static_files %}
          {% if image.path contains border_photos %}
            <div class="col-md-4">
              <div class="border-photo" style="background-image: url('{{ image.path }}')"></div>
            </div>
          {% endif %}
        {% endfor %}
      </div>
    </div>
  </div>
{% endfor %}
