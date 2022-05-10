## Twig snippets
#### List childpages

    {% for page in pages(current_page.id) if not page.hidden %}
      <p><a href="{{ page.title }}">{{ page.title }}</a></p>
    {% endfor %}


#### List pages in /dir/dir/

    {% for page in pages(Offset=2) if not page.hidden %}
      <p><a href="{{ page.url }}">{{ page.title }}</a></p>
    {% endfor %}
