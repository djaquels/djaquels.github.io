---
title: About
layout: page
---
<div class="toleft">
        <img
            class="selfie"
            src="{% if site.authors[page.author].external-image == true %}{{ site.authors[page.author].me }}{% else %}{{ site.url }}/{{ site.authors[page.author].me }}{% endif %}"
            alt="{{ site.authors[page.author].name }}"
        />
</div>

<p>

</p>

<h2>Skills</h2>

<ul class="skill-list">
    Backend
	<li>
	 <img class="skills-image" alt="{{ site.name }}" src="{% if site.external-image %}{{ site.skills.backend.laravel }}{% else %}{{ site.url }}/{{ site.skills.backend.laravel }}{% endif %}" />
	</li>
	<li>
	 <img class="skills-image" alt="{{ site.name }}" src="{% if site.external-image %}{{ site.skills.backend.node }}{% else %}{{ site.url }}/{{ site.skills.backend.node }}{% endif %}" />
	</li>
	<li>
	 <img class="skills-image" alt="{{ site.name }}" src="{% if site.external-image %}{{ site.skills.backend.spring }}{% else %}{{ site.url }}/{{ site.skills.backend.spring }}{% endif %}" />
	</li>
	<li>
	 <img class="skills-image" alt="{{ site.name }}" src="{% if site.external-image %}{{ site.skills.backend.rails }}{% else %}{{ site.url }}/{{ site.skills.backend.rails }}{% endif %}" />
	</li>
</ul>

<ul class="skill-list">
    Systems & Tools
	<li>
	 <img class="skills-image" alt="{{ site.name }}" src="{% if site.external-image %}{{ site.skills.tools.git }}{% else %}{{ site.url }}/{{ site.skills.tools.git }}{% endif %}" />
	</li>
	<li>
	 <img class="skills-image" alt="{{ site.name }}" src="{% if site.external-image %}{{ site.skills.tools.docker }}{% else %}{{ site.url }}/{{ site.skills.tools.docker }}{% endif %}" />
	</li>
	<li>
	 <img class="skills-image" alt="{{ site.name }}" src="{% if site.external-image %}{{ site.skills.tools.linux }}{% else %}{{ site.url }}/{{ site.skills.tools.linux }}{% endif %}" />
	</li>
	<li>
	 <img class="skills-image" alt="{{ site.name }}" src="{% if site.external-image %}{{ site.skills.tools.cisco }}{% else %}{{ site.url }}/{{ site.skills.tools.cisco }}{% endif %}" />
	</li>
</ul>
<h2>Projects</h2>

<ul>
	<li><a href="https://github.com/">Lorem Lorem</a></li>
</ul>
