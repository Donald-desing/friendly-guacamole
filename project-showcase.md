---
layout: page
title: "Project Showcase"
permalink: /project-showcase/
---
# Project Showcase
Here installers can share their completed projects, and customers can leave their feedback.
{% for project in site.projects %}
## {{ project.title }}
Installer: {{ project.installer }}
Date: {{ project.date | date: "%B %d, %Y" }}
{{ project.content }}
{% endfor %}
