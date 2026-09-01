<!-- <h2 id="publications" class="pub-section-title" >Publications <span class="pub-ext-links"><a href="https://scholar.google.com/citations?user=Qi2PSmEAAAAJ" target="_blank">Google Scholar</a><a href="https://dblp.org/pid/12/10033-1.html" target="_blank">DBLP</a></span></h2> -->

<!-- <h3 class="pub-subsection" style="margin: 30px 0px -30px;">Preprints</h3> -->

<script>
    function toggle_summary(id) {
        var e = document.getElementById(id);
        e.classList.toggle('open');
    }
    </script>

<div class="publications">
<ol class="bibliography">

{% for link in site.data.preprints.main %}

<li>
<div class="pub-row">
  <div class="col-sm-3 abbr" style="position: relative;padding-right: 50px;padding-left: 15px;">
    <img src="{{ link.image }}" class="teaser img-fluid z-depth-1">
            <abbr class="badge" data-venue="{{ link.conference_short }}">{{ link.conference_short }}</abbr>
  </div>
  <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: -10px;">
      <div class="title"><a href="{{ link.page }}">{{ link.title }}</a></div>
      <div class="author">{{ link.authors }}</div>
      <div class="periodical">{{ link.conference }}
      </div>
    <div class="links">

  {% if link.pdf %} 
  <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0"
     role="button" target="_blank" style="font-size:12px;">PDF</a>
  {% endif %}

  {% if link.summary %}
  <button class="btn btn-sm z-depth-0 summary-btn"
          type="button"
          onclick="toggle_summary('summary-{{ forloop.index }}')">
      Lay summary
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

You can also find some of my master's research and other academic work on my <a href="https://www.researchgate.net/profile/Nicolas-De-Ro">ResearchGate page</a>, including material that is not strictly classified as a scientific publication.




<!-- <h3 class="pub-subsection" style="margin: 35px 0px -30px;">Publications</h3>


<div class="publications">
<ol class="bibliography">

{% for link in site.data.publications.main %}

<li>
<div class="pub-row">
  <div class="col-sm-3 abbr" style="position: relative;padding-right: 15px;padding-left: 15px;">
    <img src="{{ link.image }}" class="teaser img-fluid z-depth-1">
            <abbr class="badge">{{ link.conference_short }}</abbr>
  </div>
  <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: 20px;">
      <div class="title"><a href="{{ link.pdf }}">{{ link.title }}</a></div>
      <div class="author">{{ link.authors }}</div>
      <div class="periodical"><em>{{ link.conference }}</em>
      </div>
    <div class="links">
      {% if link.pdf %} 
      <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">PDF</a>
      {% endif %}
      {% if link.code %} 
      <a href="{{ link.code }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Code</a>
      {% endif %}
      {% if link.page %} 
      <a href="{{ link.page }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Project Page</a>
      {% endif %}
      {% if link.data %} 
      <a href="{{ link.data }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Dataset</a>
      {% endif %}
      {% if link.bibtex %} 
      <a href="{{ link.bibtex }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">BibTex</a>
      {% endif %}
      {% if link.notes %} 
      <strong> <i style="color:#e74d3c; font-weight:600">{{ link.notes }}</i></strong>
      {% endif %}
      {% if link.others %} 
      {{ link.others }}
      {% endif %}
    </div>
  </div>
</div>
</li>

{% endfor %}

</ol>
</div> -->
