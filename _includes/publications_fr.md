<!-- Function to scroll text when the button is pressed -->
<script>
  function toggle_summary(id) {
      var e = document.getElementById(id);
      e.classList.toggle('open');
  }
</script>

<div class="publications">
  <ol class="bibliography">

  {% for link in site.data.publications_fr.main %}
  <li>
  <div class="pub-row">
    <div class="col-sm-3 abbr" style="position: relative;padding-right: 50px;padding-left: 15px;">
      <img src="{{ link.image }}" class="teaser img-fluid z-depth-1">
      <abbr class="badge" data-venue="{{ link.conference_short }}">{{ link.conference_short }}</abbr>
    </div>
    <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: -10px;">
        <div class="title"><a href="{{ link.page }}">{{ link.title }}</a></div>
        <div class="author">{{ link.authors }}</div>
        <div class="periodical">{{ link.conference }}</div>
        <div class="links">
          {% if link.pdf %} 
          <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0"
            role="button" target="_blank" style="font-size:12px;">PDF</a>
          {% endif %}
          {% if link.summary %}
          <button class="btn btn-sm z-depth-0 summary-btn"
                  type="button"
                  onclick="toggle_summary('summary-{{ forloop.index }}')">
              Vulgarisation
          </button>
          {% endif %}
        </div>
        {% if link.summary %}
        <div id="summary-{{ forloop.index }}" class="publication-summary">
            <p>{{ link.summary }}</p>
        </div>
        {% endif %}
    </div>
  </div>
  </li>
  {% endfor %}

  </ol>
</div>

<div style="margin-top: 2em;"></div>
Vous pouvez également retrouver certains de mes travaux de master ainsi que d’autres travaux académiques sur ma <a href="https://www.researchgate.net/profile/Nicolas-De-Ro">page ResearchGate</a>, notamment des travaux qui ne sont pas, à proprement parler, des publications scientifiques.


