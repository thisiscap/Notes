# Craft (Twig) snippets

**Twig filters**

- Url encode
  ```twig
  {{ "apples and carrots"|url_encode }}
  {# Outputs "apples%20and%20carrots" #}
  ```
- Active state to nav item
  ```twig
  {% if craft.request.firstSegment == 'news' %}class="active"{% endif %}
  ```
  or
  ```twig
  {% if craft.request.getPath() ==  entry.uri %}subNavigation-link--active{% endif %}
  ```
- Do something based on device
  ```twig
  {% if craft.request.isMobileBrowser() %}
    {# Do something #}
  {% endif %}
  ```
- Stagger CSS animations using a twig loop
  ```twig
  {% for entry in craft.entries.all() %}
  	{% set seconds = loop.index/2 %}
  	<div style="animation-delay: {{seconds}}s;">{{entry.title}}</div>
  {% endfor %}
  ```
- Add a conditional to a loop
  ```twig
  {% for entry in craft.entries.all() if entry.fieldName.exists() %}
    {# Do something #}
  {% endfor %}
  ```

**Sources**

http://craftsnippets.com/articles/twig-templating-tips-and-tricks-for-craft-cms?utm_campaign=Craft%2BLink%2BList&utm_medium=web&utm_source=Craft_Link_List_98
