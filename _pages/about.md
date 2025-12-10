---
layout: new-home
title: "Muntasir Wahed"
permalink: /
author_profile: false
redirect_from:
  - /about/
  - /about.html
  - /new/
---

<!-- This is the modern homepage -->
<div class="modern-home">
  <div class="hero-section">
    <div class="profile-container">
      <div class="profile-image">
        <img src="{{ site.baseurl }}/images/{{ site.author.avatar }}" alt="{{ site.author.name }}">
      </div>
      <div class="profile-info">
        <h1>{{ site.author.name }}</h1>
        <p class="tagline">Ph.D. Candidate, UIUC</p>
        <p class="affiliation">{{ site.author.current_dept }}<br>{{ site.author.current_org }}</p>
        
        <div class="social-links">
          {% if site.author.email %}
          <a href="mailto:{{ site.author.email }}" class="social-link" title="Email">
            <i class="fas fa-envelope"></i>
          </a>
          {% endif %}
          
          {% if site.author.googlescholar %}
          <a href="{{ site.author.googlescholar }}" class="social-link" title="Google Scholar" target="_blank">
            <i class="ai ai-google-scholar"></i>
          </a>
          {% endif %}
          
          {% if site.author.linkedin %}
          <a href="https://linkedin.com/in/{{ site.author.linkedin }}" class="social-link" title="LinkedIn" target="_blank">
            <i class="fab fa-linkedin"></i>
          </a>
          {% endif %}
          
          {% if site.author.github %}
          <a href="https://github.com/{{ site.author.github }}" class="social-link" title="GitHub" target="_blank">
            <i class="fab fa-github"></i>
          </a>
          {% endif %}
          
          {% if site.author.twitter %}
          <a href="https://twitter.com/{{ site.author.twitter }}" class="social-link" title="Twitter" target="_blank">
            <i class="fab fa-twitter"></i>
          </a>
          {% endif %}
          
          <a href="{{ site.baseurl }}/files/cv.pdf" class="social-link" title="CV">
            <i class="fas fa-file-pdf"></i>
          </a>
        </div>
      </div>
    </div>
  </div>
  
  <div class="content-grid">
    <section class="about-section">
      <h2>About Me</h2>
      <div class="about-content">
        <p>I am a <strong>Ph.D. candidate</strong> in Computer Science at the <strong>University of Illinois Urbana-Champaign</strong>, advised by Dr. Ismini Lourentzou, with an expected graduation in May 2026. My research focuses on <strong>trustworthy and multi-modal machine learning</strong>, with interests in vision-language models, grounded response generation, and conversational AI.</p>
        
        <p>I specialize in building robust AI models that can handle missing information, mitigate adversarial attacks, and defend against harmful or malicious content. My experience includes internships at <strong>Google DeepMind</strong> on the Gemini App team and three summers at <strong>IBM Research (Almaden Lab)</strong>.</p>
        
        <p>I am the co-lead of the winning team for the <strong>2025 Amazon Nova AI Challenge</strong>, where we developed models that are robust against malicious prompts and reliably generate code secure against Common Weakness Enumerations (CWEs). Additionally, I was part of a finalist team in the <strong>Amazon Alexa Prize TaskBot Challenge 2</strong>.</p>
        
        <div class="research-interests">
          <h3>Research Interests</h3>
          <ul>
            <li>Trustworthy Machine Learning</li>
            <li>Vision-Language Models</li>
            <li>Adversarial Robustness</li>
            <li>Conversational AI</li>
            <li>Multi-modal Learning</li>
          </ul>
        </div>
      </div>
    </section>
    
    <section class="news-section">
      <h2>News</h2>
      <div class="news-list">
        {% for item in site.data.news limit:6 %}
        <div class="news-item">
          <span class="news-date">{{ item.date | date: "%B %Y" }}</span>
          <p class="news-text">{{ item.text | markdownify }}</p>
        </div>
        {% endfor %}
      </div>
      <a href="{{ site.baseurl }}/news/" class="view-more">View all news →</a>
    </section>
  </div>
  
  <section class="highlights-section">
    <h2>Featured Publications</h2>
    <div class="publications-grid">
      {% assign featured_pubs = site.data.publications.publications | where: "featured", true | sort: "featured_order" %}
      {% for pub in featured_pubs %}
      <div class="publication-card">
        {% if pub.image %}
        <div class="pub-image">
          <img src="{{ site.baseurl }}/{{ pub.image }}" alt="{{ pub.title }}">
        </div>
        {% endif %}
        <div class="pub-content">
          <h3>{{ pub.title }}</h3>
          <p class="pub-venue">{{ pub.publisher }} • {{ pub.date | date: "%Y" }}</p>
          <div class="pub-links">
            {% if pub.link %}
            <a href="{{ pub.link }}" target="_blank">Paper</a>
            {% endif %}
            {% if pub.pdf %}
            <a href="{{ pub.pdf }}" target="_blank">PDF</a>
            {% endif %}
            {% if pub.code %}
            <a href="{{ pub.code }}" target="_blank">Code</a>
            {% endif %}
          </div>
        </div>
      </div>
      {% endfor %}
    </div>
    <a href="{{ site.baseurl }}/publications/" class="view-more">View all publications →</a>
  </section>
</div>