---
title: People
description: People
---
{% for member in site.data.members %}
<div class="w3-card-4">
    <div class="w3-row">
        <div class="imgdiv w3-col w3-container w3-center">
            {% if member.img != null %}
            <div class="feather"><img src="{{ member.img | prepend:'/images/members/' | append:'.webp' }}" alt="{{ member.name }}"></div>
            {% else %}
            <i class="fa fa-user fa-4x" aria-hidden="true" style="margin-top:2rem"></i>
            {% endif %}
        </div>
        <div class="w3-rest w3-container">
            <strong class="name">{{ member.name }}</strong>
            <br>
            <em class="title">
                {{ member.title }}
                <span class="email" href="{{ member.email | prepend:'mailto:' }}">
                    <i class="fa fa-envelope"></i>
                </span>
            </em>
            {% if member.txt != null %}
            <p class="text">
                {{ member.txt |
                replace: "drosophila","Drosophila" | 
                replace: "Melanogaster","melanogaster" | 
                replace: "Drosophila","<i>Drosophila</i>" | 
                replace: "melanogaster","<i>melanogaster</i>" }}
            </p>
            {% endif %}
        </div>
    </div>
</div>
{% endfor %}