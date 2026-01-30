---
layout: new-publications
title: "Publications"
permalink: /publications/
author_profile: false
---

<div class="publications-page">
  <div class="page-header">
    <h1>Publications</h1>
    <p class="subtitle">You can also find my publications on <a href="{{ site.author.googlescholar }}" target="_blank">Google Scholar</a>.</p>
  </div>
  
  <div class="publications-container">
    {% assign sorted_pubs = site.data.publications.publications | sort: 'date' | reverse %}
    
    {% for pub in sorted_pubs %}
    <article class="publication-item">
      {% if pub.image %}
      <div class="pub-image-large">
        <img src="{{ site.baseurl }}/{{ pub.image }}" alt="{{ pub.title }}">
      </div>
      {% endif %}
      
      <div class="pub-content-main">
        <div class="pub-header">
          <h2 class="pub-title">{{ pub.title }}</h2>
        </div>
        
        <div class="pub-meta">
          <p class="pub-authors">
            {% for author in pub.authors %}
              {% if author == site.author.name %}
                <strong>{{ author }}</strong>{% unless forloop.last %}, {% endunless %}
              {% else %}
                {{ author }}{% unless forloop.last %}, {% endunless %}
              {% endif %}
            {% endfor %}
          </p>
          
          <p class="pub-venue-date">
            {% if pub.publisher %}
              {% if pub.publisher == "arXiv" %}
              <span class="venue">Preprint</span>
              {% else %}
              <span class="venue">{{ pub.publisher }}</span>
              {% endif %}
            {% elsif pub.venue %}
            <span class="venue">{{ pub.venue }}</span>
            {% endif %}
            <span class="date">{{ pub.date | date: "%Y" }}</span>
          </p>
        </div>
      
      {% if pub.abstract %}
      <div class="pub-abstract">
        <p>{{ pub.abstract }}</p>
      </div>
      {% endif %}
      
      <div class="pub-actions">
        {% if pub.link %}
        <a href="{{ pub.link }}" class="btn btn-primary" target="_blank">
          <i class="fas fa-link"></i> Paper
        </a>
        {% endif %}
        
        {% if pub.project_page %}
        <a href="{{ pub.project_page }}" class="btn btn-primary" target="_blank">
          <i class="fas fa-globe"></i> Project
        </a>
        {% endif %}
        
        {% if pub.pdf %}
        <a href="{{ pub.pdf }}" class="btn btn-secondary" target="_blank">
          <i class="fas fa-file-pdf"></i> PDF
        </a>
        {% endif %}
        
        {% if pub.code %}
        <a href="{{ pub.code }}" class="btn btn-secondary" target="_blank">
          <i class="fab fa-github"></i> Code
        </a>
        {% endif %}
        
        {% if pub.slides %}
        <a href="{{ pub.slides }}" class="btn btn-secondary" target="_blank">
          <i class="fas fa-presentation"></i> Slides
        </a>
        {% endif %}
        
        {% if pub.video %}
        <a href="{{ pub.video }}" class="btn btn-secondary" target="_blank">
          <i class="fas fa-video"></i> Video
        </a>
        {% endif %}
        
        {% if pub.bibtex %}
        <button class="btn btn-secondary bibtex-toggle" data-target="bibtex-{{ forloop.index }}">
          <i class="fas fa-quote-right"></i> BibTeX
        </button>
        {% endif %}
      </div>
      
        {% if pub.bibtex %}
        <div class="bibtex-container" id="bibtex-{{ forloop.index }}" style="display: none;">
          <pre><code>{{ pub.bibtex }}</code></pre>
        </div>
        {% endif %}
      </div>
    </article>
    {% endfor %}
  </div>
</div>

<script>
// Toggle BibTeX display
document.querySelectorAll('.bibtex-toggle').forEach(button => {
  button.addEventListener('click', function() {
    const targetId = this.getAttribute('data-target');
    const container = document.getElementById(targetId);
    if (container.style.display === 'none') {
      container.style.display = 'block';
      this.classList.add('active');
    } else {
      container.style.display = 'none';
      this.classList.remove('active');
    }
  });
});
</script>
