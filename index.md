<div class="hero">
  <div class="container" markdown="1">

1739 Squadron
===================
{: .display-4 .font-weight-normal}

Air Training Corps
------------------
{: .display-5 .font-weight-normal}

  </div>
</div>

{% for section in site.sections %}
  <section id="{{ section.title | slugify }}" class="section {{ section.classes }}">
    <div class="container">
      <div class="row">
        <div class="col-md-12">
          <h2 class="text-center">{{ section.title }}</h2>
          {{ section.content }}
        </div>
      </div>
    </div>
  </section>
{% endfor %}
