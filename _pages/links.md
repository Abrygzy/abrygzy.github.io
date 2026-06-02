---
layout: page
title: links
permalink: /links/
description: A curated collection of useful links, grouped by topic.
nav: true
nav_order: 4
_styles: |
  .link-section + .link-section {
    margin-top: 2.5rem;
  }

  .link-section h2 {
    margin-bottom: 0.35rem;
  }

  .link-grid .card {
    height: 100%;
    border: 1px solid rgba(0, 0, 0, 0.08);
    transition:
      transform 0.18s ease,
      box-shadow 0.18s ease,
      border-color 0.18s ease;
  }

  .link-grid .card:hover {
    transform: translateY(-3px);
    box-shadow: 0 0.75rem 1.5rem rgba(0, 0, 0, 0.08);
    border-color: var(--global-theme-color);
  }

  .link-grid .card-title {
    margin-bottom: 0.6rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 0.75rem;
  }

  .link-grid .external-mark {
    font-size: 0.9rem;
    opacity: 0.7;
  }

  .link-grid .card-text {
    margin-bottom: 0;
    color: var(--global-text-color-light);
  }
---

This page gathers websites and tools that are useful in my daily work. The entries are grouped by topic so they are easier to browse and expand over time.

{% for group in site.data.useful_links %}
  <section class="link-section">
    <h2>{{ group.category }}</h2>
    <p class="post-description">{{ group.description }}</p>
    <div class="row link-grid">
      {% for link in group.links %}
        <div class="col-sm-12 col-md-6 mb-4">
          <a href="{{ link.url }}" target="_blank" rel="noopener noreferrer" class="text-decoration-none">
            <div class="card hoverable">
              <div class="card-body">
                <h3 class="card-title h5">
                  <span>{{ link.title }}</span>
                  <span class="external-mark" aria-hidden="true">↗</span>
                </h3>
                <p class="card-text">{{ link.description }}</p>
              </div>
            </div>
          </a>
        </div>
      {% endfor %}
    </div>
  </section>
{% endfor %}
