---
layout: single
title: "PhD Students"
permalink: /team/phd/
classes: wide
sidebar:
        nav: team
feature_row:
   - image_path: assets/images/pau-bosch.jpg
     alt: "Pau Bosch Santos"
     title: "Pau Bosch Santos"
     url: /team/phd/pau-bosch/
   - image_path: assets/images/elisabet-carbo.jpg
     alt: "Elisabet Carbó Catalan"   
     title: "Elisabet Carbó"
     url: /team/phd/elisabet-carbo/
   - image_path: /assets/images/ana-kvirikashvili.jpg
     alt: "Ana Kvirikashvili"
     title: "Ana Kvirikashvili"
     url: /team/phd/ana-kvirikashvili/
   - image_path: /assets/images/aina-vidal.jpg
     alt: "Aina Vidal Pérez"   
     title: "Aina Vidal Pérez"
     url: /team/phd/aina-vidal/
---
<section class="entries-grid">
{% if include.id %}
  {% assign feature_row = page[include.id] %}
{% else %}
  {% assign feature_row = page.feature_row %}
{% endif %}

{% for f in feature_row %}

<div class="grid__item-adjust">

    {% if f.url contains "://" %}
      {% capture f_url %}{{ f.url }}{% endcapture %}
    {% else %}
      {% capture f_url %}{{ f.url | relative_url }}{% endcapture %}
    {% endif %}

      <div class="archive__item">
       <a href="{{ f_url }}">

       <img src=
              {% if f.image_path contains "://" %}
                "{{ f.image_path }}"
              {% else %}
                "{{ f.image_path | relative_url }}"
              {% endif %}
            alt="{% if f.alt %}{{ f.alt }}{% endif %}">

         <h2 class="archive__item-title" style="clear: both">{{ f.title }}</h2>

     </a>

        {% if f.excerpt %}
         <div class="archive__item-excerpt">
         {{ f.excerpt | markdownify }}
         </div>
        {% endif %}



      </div>
</div>
{% endfor %}
</section>
