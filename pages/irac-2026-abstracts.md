---
title: Abstracts
description: Abstracts for [IRAC 2026](/irac-2026/).
background: https://images.unsplash.com/photo-1468436385273-8abca6dfd8d3?q=80&w=2810&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D
permalink: /irac-2026/abstracts/
toc: true
---

{% assign abstr = site.data.abstractsirac2026 | group_by: 'contributiontype' %}
{% for type in abstr %}
## {{ type.name }}s
{% for abstract in type.items %}
{:id="{{ abstract.key }}"}
#### {{ abstract.title }}

{% if abstract.authorsbefore %}{{ abstract.authorsbefore }};{% endif %}{% if abstract.orcid == NULL %} **{{ abstract.firstname }} {{ abstract.lastname }}**{% else %} [**{{ abstract.firstname }} {{ abstract.lastname }}**](https://orcid.org/{{ abstract.orcid }}){% endif %}{% if abstract.authors %}; {{ abstract.authors }}{% endif %}

{% for kw in abstract.keywords %} **{{ kw }}**{:.badge .bg-primary } {% endfor %}

{{ abstract.abstract }}
{% endfor %}
{% endfor %}

