---
---
<style>.main-content {padding: 0}</style>
<div class="w3-display-container">
    {% for file in site.static_files %}
        {% if file.path contains "/images/slides/" %}
            <img class="mySlides w3-animate-opacity" src="{{ file.path }}" alt="{{ file.basename }}">
        {% endif %}
    {% endfor %}
    <div class="w3-center w3-container w3-section w3-text-white w3-display-bottommiddle" id="slidectrl">
        <div class="w3-left w3-hover-text-khaki cursor" onclick="plusDivs(-1)">&#10094;</div>
        <div class="w3-right w3-hover-text-khaki cursor" onclick="plusDivs(1)">&#10095;</div>
        {% for file in site.static_files %}
            {% if file.path contains "/images/slides/" %}
                <span class="w3-badge dotnavi w3-border w3-transparent w3-hover-white" onclick="currentDiv({% increment index %})"></span>
            {% endif %}
        {% endfor %}
    </div>
</div>
<hr>
<div class="w3-row">
    <div class="w3-col m6 l7 w3-container w3-justify">
        <p>My group is interested in mapping neural circuits mediating behaviors, particularly those related to the higher brain functions, in the fruit flies. Our topics cover behaviors of both individuals and groups, ranging from drinking, feeding, learning and memory to courtship, aggression and sociality. We routinely utilize interdisciplinary approaches including neurogenetics, optogenetics, brain imaging, electrophysiology, quantitative behavioral analysis, and machine vision. Additionally, we are interested in applying what we learned from the tiny flies to solve problems in other organisms (such as human and robots). </p>
        <p>Although it would be a long way to go, we designed our research specifically to accelerate the accomplishments of the following goals: </p>
        <ul>
            <li>to eat without getting fat</li>
            <li>to be smart without studying</li>
            <li>to love without being hurt</li>
            <li>to compete without being defeated</li>
            <li>to be alone without feeling lonely</li>
        </ul>
    </div>
    <div class="w3-col m6 l5 w3-container w3-justify">
        <div class="w3-center">
            <h1>Prof. Yan Zhu</h1>
            <img src="images/members/zy.jpg" alt="Prof. Yan Zhu">
        </div>
        <hr>
        <ul>
            <li>PhD in Molecular Cell Biology, Washington University in St. Louis, 2003</li>
            <li>Postdoctoral Scholar, HHMI and UCLA, 2003-2009</li>
            <li>Principal Investigator, State Key Lab of Brain and Cognitive Science, Institute of Biophysics, Chinese Academy of Sciences, 2009-</li>
            <li>Professor, University of Chinese Academy of Sciences, 2015-</li>
        </ul>
    </div>
</div>

<script>
    var slideIndex = 1;
    var autoInterval,autoTimeout;
    showDivs(1);
    iniautoshow();

    function iniautoshow() {
        autoInterval = setInterval(autoshow, 3000);
    }

    function autoshow() {
        showDivs(slideIndex += 1);
    }

    function plusDivs(n) {
        showDivs(slideIndex += n);
        clearInterval(autoInterval);
        clearTimeout(autoTimeout);
        iniautoshow();
    }

    function currentDiv(n) {
        showDivs(slideIndex = n+1);
        clearInterval(autoInterval);
        clearTimeout(autoTimeout);
        autoTimeout = setTimeout(iniautoshow, 8000);
    }

    function showDivs(n) {
        var i;
        var x = document.getElementsByClassName("mySlides");
        var dots = document.getElementsByClassName("dotnavi");
        if (n > x.length) {slideIndex = 1}    
        if (n < 1) {slideIndex = x.length}
        for (i = 0; i < x.length; i++) {
            if (x[i].style.display = "block"){
                x[i].style.display = "none";
            }
        }
        for (i = 0; i < dots.length; i++) {
            dots[i].className = dots[i].className.replace(" w3-white", "");
        }
        x[slideIndex-1].style.display = "block";
        dots[slideIndex-1].className += " w3-white";
    }
</script>