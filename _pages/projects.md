---
layout: page
title: projects
permalink: /projects/
nav: true
nav_order: 4
display_categories: [work, fun]
horizontal: false
---

<style>
.projects-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 1rem 0;
}

.projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
    gap: 2rem;
    margin-top: 1rem;
    max-width: 1200px;
    margin-left: auto;
    margin-right: auto;
}

.project-card {
    max-width: 500px;
    justify-self: center;
}

.project-card {
    background: var(--global-bg-color);
    border: 1px solid var(--global-divider-color);
    border-radius: 12px;
    overflow: hidden;
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    position: relative;
    height: 100%;
    display: flex;
    flex-direction: column;
    text-decoration: none;
}

.project-card:hover {
    transform: translateY(-8px);
    box-shadow: 0 12px 24px rgba(181, 9, 172, 0.15);
    border-color: var(--global-theme-color);
    text-decoration: none;
}

.project-image {
    position: relative;
    overflow: hidden;
    height: 200px;
    background: linear-gradient(135deg, var(--global-theme-color), #d946ef);
}

.project-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.3s ease;
}

.project-card:hover .project-image img {
    transform: scale(1.05);
}

.project-content {
    padding: 1.5rem;
    flex: 1;
    display: flex;
    flex-direction: column;
}

.project-title {
    font-size: 1.25rem;
    font-weight: 600;
    color: var(--global-text-color);
    margin-bottom: 0.75rem;
    line-height: 1.3;
}

.project-subtitle {
    font-size: 0.9rem;
    color: var(--global-theme-color);
    font-weight: 500;
    margin-bottom: 0.75rem;
    text-transform: uppercase;
    letter-spacing: 0.5px;
}

.project-description {
    color: var(--global-text-color-light);
    font-size: 0.95rem;
    line-height: 1.6;
    margin-bottom: 1rem;
    flex: 1;
}

.project-meta {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-top: auto;
    padding-top: 1rem;
    border-top: 1px solid var(--global-divider-color);
}

.project-date {
    font-size: 0.85rem;
    color: var(--global-text-color-light);
    font-weight: 500;
}

.category-badge {
    display: inline-block;
    padding: 0.25rem 0.75rem;
    background: var(--global-theme-color);
    color: white;
    border-radius: 20px;
    font-size: 0.75rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    margin-bottom: 1rem;
}

@media (max-width: 768px) {
    .projects-grid {
        grid-template-columns: 1fr;
        gap: 1.5rem;
    }
    
    .project-card {
        margin-bottom: 1rem;
    }
    
    .project-content {
        padding: 1.25rem;
    }
}

@media (min-width: 769px) and (max-width: 1024px) {
    .projects-grid {
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        gap: 1.5rem;
    }
}
</style>

<div class="projects-container">
    <div class="projects-grid">
        {% assign sorted_projects = site.projects | where_exp: "project", "project.hidden != true" | sort: "importance" | reverse %}
        {% for project in sorted_projects %}
        <a href="{% if project.redirect %}{{ project.redirect }}{% else %}{{ project.url | relative_url }}{% endif %}" class="project-card">
            <div class="project-image">
                {% if project.img %}
                    <img src="{{ project.img | relative_url }}" alt="{{ project.title }}">
                {% endif %}
            </div>
            <div class="project-content">
                <div class="category-badge">{{ project.category }}</div>
                <h2 class="project-title">{{ project.title }}</h2>
                {% if project.subtitle %}
                    <div class="project-subtitle">{{ project.subtitle }}</div>
                {% endif %}
                <p class="project-description">{{ project.description }}</p>
                <div class="project-meta">
                    {% if project.date %}
                        <div class="project-date">{{ project.date | date: "%B %Y" }}</div>
                    {% endif %}
                </div>
            </div>
        </a>
        {% endfor %}
    </div>
</div>
