<div class="software-page">

<p class="software-intro">
I develop open-source software to support my research in theoretical physics, with a particular focus on quantum dynamics, classical and quantum Krylov methods, and many-body systems. The codes below are available on GitHub.
</p>

<div class="software-list"> 
{% for software in site.data.softwares.main %} 
  <div class="software-item"> 

    <div class="software-image"> 
      <img src="{{ software.image }}" alt="{{ software.title }}"> 
    </div> 

    <div class="software-content"> 
      <div class="software-title">
        {{ software.title }} 
      </div> 

      <div class="software-description">
        {{ software.description }} 
      </div> 

      <div class="software-links"> 
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

    </div> 
  </div> 
{% endfor %} 
</div>

</div>