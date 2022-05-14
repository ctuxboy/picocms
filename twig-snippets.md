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

#### Loop trought a YAML-array (metadata)

Yaml:

    links:
      - name: website-1
        url: https://website-1.com
      - name: website-2
        url: https://website-2.com
    
Twig:

    {% for item in meta.links %}
      <p><a href="{{ item.url }}">{{ item.name }}</a></p>
    {% endfor %}
    
    
#### Total pages from a specific template

    {% set counter = '' %}
      {% for page in pages %}
      {%- if page.meta["template"] == 'YOUR_TEMPLATE' %}
        {% set counter = counter +1 %}
      {% endif -%}
    {% endfor %}
    
    Total pages: {{ counter }}
    
#### Total pages from a specific offset (dirtree)

    {% set counter = '' %}
    {% for page in pages("",offset=3) %} {# offset=3 => /subdir/subdir/page.md #}
      {% set counter = counter + 1 %}
    {% endfor %}

    Total pages: {{ counter }}
