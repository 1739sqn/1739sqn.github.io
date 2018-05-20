<div class="hero">
  <div class="container" markdown="1">

![logo](/logo.svg)
{: .float-right}

1739 Squadron
===================
{: .display-4 .font-weight-normal}

Air Training Corps
------------------
{: .display-5 .font-weight-normal}

  </div>
</div>

{% comment %}
-----------------------------------------------------------------------------------

Unless you know what you're doing, you probably don't want to edit below this line.

Content for sections can be found in _sections/
The border photos can be found in assets/border_photos

The following joins the sections together with their border photos

-----------------------------------------------------------------------------------
{% endcomment %}

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
