---
---
<div class="w3-content w3-display-container">
    {% for file in site.static_files %}
        {% if file.path contains "/images/slides/" %}
            <img class="mySlides w3-animate-opacity" src="{{ file.path }}" style="width:100%"/>
        {% endif %}
    {% endfor %}
    <div class="w3-center w3-container w3-section w3-large w3-text-white w3-display-bottommiddle" style="width:100%">
        <div class="w3-left w3-hover-text-khaki cursor" onclick="plusDivs(-1)">&#10094;</div>
        <div class="w3-right w3-hover-text-khaki cursor" onclick="plusDivs(1)">&#10095;</div>
        {% for file in site.static_files %}
            {% if file.path contains "/images/slides/" %}
                <span class="w3-badge dotnavi w3-border w3-transparent w3-hover-white" onclick="currentDiv({% increment index %})"></span>
            {% endif %}
        {% endfor %}
    </div>
</div>

<script>
var slideIndex = 1;
showDivs(1);
var auto;
iniautoshow();

function iniautoshow() {
    auto = setInterval(autoshow, 2000);
}

function autoshow() {
    plusDivs(1);
}

function plusDivs(n) {
  showDivs(slideIndex += n);
}

function currentDiv(n) {
  showDivs(slideIndex = n+1);
  clearInterval(auto);
  setTimeout(iniautoshow, 5000);
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