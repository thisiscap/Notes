# Craft (Twig) snippets

**Twig filters**

- Url encode
  ```twig
  {{ "apples and carrots"|url_encode }}
  {# outputs "apples%20and%20carrots" #}
  ```
- Active state to nav item
  ```twig
  {% if craft.request.firstSegment == 'news' %}class="active"{% endif %}
  ```
- Do something based on device (cache example)
  ```twig
  {% cache if craft.request.isMobileBrowser() %}
  ```
