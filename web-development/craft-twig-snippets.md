# Craft (Twig) snippets

**Twig filters**

- Url encode
  ```
  {{ "apples and carrots"|url_encode }}
  {# outputs "apples%20and%20carrots" #}
  ```
- Active state to nav item
  ```
  {% if craft.request.firstSegment == 'news' %}class="active"{% endif %}
  ```
