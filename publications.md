---
title: Publications
description: Publications
---
{% for paper in site.data.publications %}
<div class="w3-card-4">
    <div class="w3-container pub">
        <strong>{{ forloop.index }}. </strong>
        {{ paper.Author | 
            replace: "Zhu Yan","<strong>Zhu Yan</strong>" }}
        <br>
        {{ paper.Title | 
            replace: "drosophila","Drosophila" | 
            replace: "Melanogaster","melanogaster" | 
            replace: "Drosophila","<i>Drosophila</i>" | 
            replace: "melanogaster","<i>melanogaster</i>" }}
        {% if paper.Journal != null %}
            <ins>{{ paper.Journal }}</ins>
        {% endif %}
        <br>
        {% if paper.Year != null %}
            {{ paper.Year }}
        {% endif %}
        {% if paper.Volume != null %}
            ; {{ paper.Volume }}
        {% endif %}
        {% if paper.Issue != null %}
            ({{ paper.Issue }})
        {% endif %}
        {% if paper.Pages != null %}
            : {{ paper.Pages }}
        {% endif %}
        {% if paper.DOI != null %}
            . doi: <a href="https://doi.org/{{paper.DOI}}">{{ paper.DOI }}</a>
        {% endif %}
    </div>
    <button id ="btn{{ forloop.index }}" onclick="showabs('{{ forloop.index }}')" class="absbtn w3-button w3-block w3-light-grey">Click to show abstract</button>
    <div id="{{ forloop.index }}" class="abs w3-panel w3-light-grey" style="display: none">
        <p class="text">
            {{ paper.Abstract |
            replace: "drosophila","Drosophila" | 
            replace: "Melanogaster","melanogaster" | 
            replace: "Drosophila","<i>Drosophila</i>" | 
            replace: "melanogaster","<i>melanogaster</i>" }}
        </p>
    </div>
</div>
{% endfor %}

<script>
    function showabs(id) {
        $("#"+id).slideToggle(500,function(){btnname(id);});
    }
    function btnname(id) {
        var btn = document.getElementById("btn"+id);
        if (btn.innerHTML == "Click to show abstract") {
            btn.innerHTML = "Click to hide abstract";
        }else {
            btn.innerHTML = "Click to show abstract";
        }
    }
</script>