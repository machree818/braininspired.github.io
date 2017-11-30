---
---
<br>
{% for file in site.static_files %}
    {% if file.path contains "/images/slides/" %}
        {{ file.path }}
    {% endif %}
{% endfor %}