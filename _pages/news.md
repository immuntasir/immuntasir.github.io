---
layout: new-publications
title: "News"
permalink: /news/
author_profile: false
---

<div class="news-page">
  <div class="page-header">
    <h1>News & Updates</h1>
    <p class="subtitle">Latest updates about my research and activities</p>
  </div>
  
  <div class="news-timeline">
    {% for item in site.data.news %}
    <div class="news-item-full">
      <div class="news-date-full">
        <span class="month">{{ item.date | date: "%b" }}</span>
        <span class="year">{{ item.date | date: "%Y" }}</span>
      </div>
      <div class="news-content-full">
        {{ item.text | markdownify }}
      </div>
    </div>
    {% endfor %}
  </div>
</div>

<style>
.news-page {
  max-width: 900px;
  margin: 0 auto;
  padding: 2rem 1rem;
}

.news-timeline {
  position: relative;
  padding-left: 2rem;
}

.news-timeline::before {
  content: '';
  position: absolute;
  left: 0;
  top: 0;
  bottom: 0;
  width: 2px;
  background: var(--border-color);
}

.news-item-full {
  display: flex;
  gap: 2rem;
  margin-bottom: 2rem;
  position: relative;
}

.news-item-full::before {
  content: '';
  position: absolute;
  left: -2.5rem;
  top: 0.5rem;
  width: 12px;
  height: 12px;
  background: var(--primary-color);
  border-radius: 50%;
  border: 3px solid var(--bg-white);
  box-shadow: 0 0 0 2px var(--primary-color);
}

.news-date-full {
  flex-shrink: 0;
  text-align: center;
  min-width: 80px;
}

.news-date-full .month {
  display: block;
  font-size: 1.2rem;
  font-weight: 700;
  color: var(--primary-color);
}

.news-date-full .year {
  display: block;
  font-size: 0.9rem;
  color: var(--text-light);
  font-weight: 600;
}

.news-content-full {
  flex: 1;
  background: var(--bg-white);
  padding: 1.5rem;
  border-radius: 8px;
  box-shadow: var(--shadow);
  transition: var(--transition);
}

.news-content-full:hover {
  box-shadow: var(--shadow-hover);
  transform: translateY(-2px);
}

.news-content-full p {
  margin: 0;
  color: var(--text-dark);
  line-height: 1.7;
}

.news-content-full a {
  color: var(--primary-color);
  text-decoration: none;
  font-weight: 600;
}

.news-content-full a:hover {
  color: var(--secondary-color);
  text-decoration: underline;
}

@media (max-width: 768px) {
  .news-timeline {
    padding-left: 1rem;
  }
  
  .news-item-full {
    flex-direction: column;
    gap: 1rem;
  }
  
  .news-item-full::before {
    left: -1.5rem;
  }
  
  .news-date-full {
    display: flex;
    gap: 0.5rem;
    align-items: baseline;
  }
  
  .news-date-full .month {
    font-size: 1rem;
  }
}
</style>
