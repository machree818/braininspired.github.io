---
title: People
layout: default
---
{% for member in site.data.members %}
<div class="w3-card-4">
    <div class="w3-row">
        <div class="w3-quarter w3-container w3-center" style="padding: 0">
            {% if member.img != null %}
            <div class="feather"><img src="{{ member.img | prepend:'/images/' | append:'.webp' }}"/></div>
            {% else %}
            <i class="fa fa-user fa-4x" aria-hidden="true" style="margin:1rem"></i>
            {% endif %}
        </div>
        <div class="w3-rest w3-container">
            <p class="name">{{ member.name }}</p>
            <div class="w3-row">
                {% if member.title != null %}
                <div class="w3-left w3-container"><p class="title">{{ member.title }}</p></div>
                {% endif %}
                {% if member.email != null %}
                <div class="w3-left w3-container"><a class="email" href="{{ member.email | prepend:'mailto:' }}"><i class="fa fa-envelope"></i></a></div>
                {% endif %}
            </div>
            {% if member.txt != null %}
            <p>{{ member.txt }}</p>
            {% endif %}
        </div>
    </div>
</div>
{% endfor %}