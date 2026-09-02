<!-- Function to scroll text when the button is pressed -->
<script>
    function toggle_summary(id) {
        var e = document.getElementById(id);
        e.classList.toggle('open');
    }
    </script>

<div class="software-page">
  <p class="software-intro">
  Theoretical physics often presents us with complex models and difficult equations, making numerical simulations essential for testing our analytical predictions. In this light, the computer becomes a true laboratory. Over time, I have grown to love this numerical environment and scientific programming in general. My philosophy is to build reproducible, open-source software that can benefit the research community and curious minds alike. Below, you will find a list of my published software along with brief overviews of how these tools can be useful to you. Visit the corresponding GitHub pages for detailed documentation.
  </p>

  <div class="software-list"> 

  {% for software in site.data.softwares.main %} 
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
              Useful for you?
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