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
        <p class="tagline">Ph.D. Candidate</p>
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
          
          <a href="{{ site.baseurl }}/cv/" class="social-link" title="CV">
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
        <p>I am a <strong>Ph.D. candidate</strong> in Computer Science at the <strong>University of Illinois Urbana-Champaign</strong> (Siebel School of Computing and Data Science), advised by Dr. Ismini Lourentzou. My research focuses on <strong>trustworthy and multi-modal machine learning</strong>, specifically aiming to advance the robustness and real-world reliability of foundation models. I specialize in addressing fundamental weaknesses in AI systems, such as failures under long-tail distributions, adversarial interactions, and missing inputs, to build models that are safe, grounded, and technically rigorous. My research has been published in premier venues, including <strong>CVPR</strong>, <strong>NeurIPS</strong>, <strong>EMNLP</strong>, <strong>WACV</strong>, and <strong>CIKM</strong>.</p>
        
        <p>I have significant industry research experience, most recently as a Intern at <strong>Google DeepMind</strong> on the <strong>Gemini App</strong> team. Previously, I spent three summers at <strong>IBM Research (Almaden Lab)</strong>, where my work resulted in two U.S. patents and multiple publications. I co-led the winning team for the <strong>Amazon NOVA AI Challenge</strong>, developing methodologies for LLM safety and code security that led to publications at <strong>NeurIPS 2025</strong> and <strong>EMNLP 2025</strong>. Earlier, I was part of a finalist team in the <strong>Amazon Alexa Prize TaskBot Challenge 2</strong>, contributing to the design of a multimodal conversational agent deployed to thousands of users.</p>
        
        <p>Previously, I earned my <strong>M.S. in Computer Science</strong> from <strong>Virginia Tech</strong> and my <strong>B.Sc. in Computer Science & Engineering</strong> from the <strong>University of Dhaka</strong>. My technical expertise spans large language models, vision-language models, and robust ML, backed by strong technical skills in Python, C, and full-stack development.</p>
        
        <div class="research-interests">
          <h3>Research Interests</h3>
          <ul>
            <li>Trustworthy ML</li>
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