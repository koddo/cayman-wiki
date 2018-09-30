{% feed_meta %}

<ul class="page-list">
    {% for my_page in site.pages %}
        {% if my_page.title %}
            <p><a class="page-link" href="{{ my_page.url | prepend: site.baseurl }}">{{ my_page.title }}</a></p>
        {% endif %}
    {% endfor %}
</ul>
