{% if page.lang == "fr" %}
  <a class="normal language-switch" href="{{ page.en_url | relative_url }}">EN</a>
{% else %}
  <a class="normal language-switch" href="{{ page.fr_url | relative_url }}">FR</a>
{% endif %}

{% for link in site.data.navigation.main %}
  {% if link.right %}
    <a class="normal right" href="{% if link.url == nil or link.url == '' %}{% if page.lang == 'fr' %}/fr/{% else %}/{% endif %}{% else %}{% if page.lang == 'fr' %}/fr/{{ link.url }}{% else %}/{{ link.url }}{% endif %}{% endif %}">
      {% if page.lang == "fr" %}
        {{ link.title_fr }}
      {% else %}
        {{ link.title }}
      {% endif %}
    </a>
  {% else %}
    <a class="normal" href="{% if link.url == nil or link.url == '' %}{% if page.lang == 'fr' %}/fr/{% else %}/{% endif %}{% else %}{% if page.lang == 'fr' %}/fr/{{ link.url }}{% else %}/{{ link.url }}{% endif %}{% endif %}">
      {% if page.lang == "fr" %}
        {{ link.title_fr }}
      {% else %}
        {{ link.title }}
      {% endif %}
    </a>
  {% endif %}
{% endfor %}