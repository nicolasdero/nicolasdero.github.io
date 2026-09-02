<!-- Function to scroll text when the button is pressed -->
<script>
    function toggle_summary(id) {
        var e = document.getElementById(id);
        e.classList.toggle('open');
    }
    </script>

<div class="software-page">
  <p class="software-intro">
  La physique théorique nous confronte très souvent à des modèles complexes et à des équations difficiles à résoudre. Les simulations numériques deviennent alors un outil nécessaire pour tester nos prédictions analytiques. L'ordinateur occupe en ce sens une place centrale et se transforme ainsi en laboratoire. Au fil du temps, j'ai pris plaisir à développer un cadre numérique autour de mes recherches. Ma philosophie est de développer des softwares open source et reproductibles, susceptibles de profiter à la communauté scientifique comme aux esprits les plus curieux. Vous trouverez ci-dessous une liste des softwares que j’ai publiés, accompagnée d’un bref aperçu de l’utilité de ces outils. Consultez les pages GitHub correspondantes pour une documentation détaillée.

  </p>

  <div class="software-list"> 

  {% for software in site.data.softwares_fr.main %} 
    <div class="software-item"> 
      <div class="software-image"> 
        <img src="{{ software.image }}" alt="{{ software.title }}"> 
      </div> 
      <div class="software-content"> 
        <div class="software-title"> {{ software.title }} </div> 
        <div class="software-description">{{ software.description }} </div> 
        <div class="software-links">
          {% if software.useful %}
          <button class="btn btn-sm z-depth-0 summary-btn"
                  type="button"
                  onclick="toggle_summary('software-summary-{{ forloop.index }}')">
              Utile ?
          </button>
          {% endif %}
          {% if software.github %}
          <a href="{{ software.github }}" class="btn btn-sm z-depth-0"
            role="button" target="_blank" rel="noopener">
              GitHub
          </a>
          {% endif %}
          {% if software.zenodo %}
          <a href="{{ software.zenodo }}" class="btn btn-sm z-depth-0"
            role="button" target="_blank" rel="noopener">
              Zenodo
          </a>
          {% endif %}
        </div>
      {% if software.useful %}
      <div id="software-summary-{{ forloop.index }}" class="publication-summary">
          <p>{{ software.useful }}</p>
      </div>
      {% endif %}
    </div> 
  </div> 
{% endfor %} 