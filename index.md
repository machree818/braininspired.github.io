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

---

My group is interested in understanding: 
1. the formation of neural circuitry, by investigating the molecular mechanisms that direct the development of complex and previously inaccessible higher-order regions of the *Drosophila* visual system;
2. the molecular and cellular basis of how neural circuits mediate complex animal behavior, by systematically mapping neural circuits underlying vision and other sensory perceptions; 
3. how diseases and genetic mutations affect the development and function of the nervous system.

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