## Twig snippets
#### List childpages

    {% for page in pages(current_page.id) if not page.hidden %}
      <p><a href="{{ page.title }}">{{ page.title }}</a></p>
    {% endfor %}

#### List pages in /child-dir/child-dir/ (Offset=2)

    {% for page in pages(Offset=2) if not page.hidden %}
      <p><a href="{{ page.url }}">{{ page.title }}</a></p>
    {% endfor %}

#### List pages from a specific template

    {% for page in pages %}
      {% if page.meta["template"] == 'your-template-name' %}
        <p><a href="{{ page.url }}">{{ page.title }}</a></p>
      {% endif %}
    {% endfor %}
