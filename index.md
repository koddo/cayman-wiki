<ul class="page-list">
    {% for my_page in site.pages %}
        {% if my_page.title %}
            <p><a class="page-link" href="{{ my_page.url | prepend: site.baseurl }}">{{ my_page.title }}</a></p>
        {% endif %}
    {% endfor %}
</ul>


{% for my_collection in site.collections %}
  {% if my_collection.label != 'posts' %}
  <h1 class="page-heading">{{ my_collection.title }}</h1>
  <ul class="collection-list">
      <li>
          <!-- <p>collection: <a href="{{ site.baseurl }}/{{ my_collection.label }}">{{ my_collection.title }}</a></p> -->
          {% for my_page in my_collection.docs %}
          {% if my_page.title != 'Index' %}
          <ul class="collection-page">
              <li><a class="page-link" href="{{ my_page.url | prepend: site.baseurl }}">{{ my_page.title }}</a></li>
          </ul>
          {% endif %}
          {% endfor %}
      </li>
  </ul>
  {% endif %}
{% endfor %}
