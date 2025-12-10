---
layout: new-publications
title: "Curriculum Vitae"
permalink: /cv/
author_profile: false
---

<div class="cv-page">
  <div class="page-header">
    <h1>Curriculum Vitae</h1>
    <p class="subtitle">Muntasir Wahed - Ph.D. Candidate, UIUC</p>
    <div class="cv-actions">
      <a href="{{ site.baseurl }}/files/MuntasirWahed_2025.pdf" target="_blank" class="btn-download">
        <i class="fas fa-download"></i> Download PDF
      </a>
    </div>
  </div>
  
  <div class="cv-viewer">
    <iframe src="{{ site.baseurl }}/files/MuntasirWahed_2025.pdf" 
            width="100%" 
            height="800px" 
            style="border: 1px solid var(--border-color); border-radius: 8px;">
      <p>Your browser does not support PDFs. 
         <a href="{{ site.baseurl }}/files/MuntasirWahed_2025.pdf" target="_blank">Download the CV instead</a>.
      </p>
    </iframe>
  </div>
</div>

<style>
.cv-page {
  max-width: 100%;
  margin: 0 auto;
  padding: 2rem 1rem;
}

.page-header {
  text-align: center;
  margin-bottom: 2rem;
}

.page-header h1 {
  font-size: 2.5rem;
  color: var(--text-dark);
  margin: 0 0 0.5rem 0;
}

.page-header .subtitle {
  font-size: 1.1rem;
  color: var(--text-light);
  margin: 0 0 1.5rem 0;
}

.cv-actions {
  margin-bottom: 1rem;
}

.btn-download {
  display: inline-block;
  background: var(--primary-color);
  color: white;
  padding: 0.75rem 1.5rem;
  text-decoration: none;
  border-radius: 6px;
  font-weight: 600;
  transition: var(--transition);
  box-shadow: var(--shadow);
}

.btn-download:hover {
  background: var(--secondary-color);
  transform: translateY(-2px);
  box-shadow: var(--shadow-hover);
  color: white;
  text-decoration: none;
}

.btn-download i {
  margin-right: 0.5rem;
}

.cv-viewer {
  background: var(--bg-white);
  border-radius: 12px;
  padding: 2rem;
  box-shadow: var(--shadow);
}

.cv-viewer iframe {
  border: 1px solid var(--border-color);
  border-radius: 8px;
  box-shadow: var(--shadow);
  transition: var(--transition);
}

.cv-viewer iframe:hover {
  box-shadow: var(--shadow-hover);
}

@media (max-width: 768px) {
  .cv-page {
    padding: 1rem 0.5rem;
  }
  
  .page-header h1 {
    font-size: 2rem;
  }
  
  .cv-viewer {
    padding: 1rem;
  }
  
  .cv-viewer iframe {
    height: 600px;
  }
}
</style>