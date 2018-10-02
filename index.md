{% for my_collection in site.collections %}
<h1 class="page-heading">{{ my_collection.title }}</h1>
{% for my_page in my_collection.docs %}
{% if my_page.title != 'Index' %}
<ul class="collection-page">
    <li><a class="page-link" href="{{ my_page.url | prepend: site.baseurl }}">{{ my_page.title }}</a></li>
</ul>
{% endif %}
{% endfor %}
{% endfor %}
