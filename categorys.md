---
layout: etc
title: "Categories"
permalink: /categorys/
---
{% assign categorys_str = "travelling,watching,reading,thinking,diving,sundries,tech" %}
{% assign categorys = categorys_str | split:',' %}
{% for category in categorys %}
<div cass="post">
	<h3 class="page-title">
		<a href="./{{ category }}">{{ category }}</a> ({{ site.categories[category].size }})
	</h3>
	<ul>
		{% assign loopSize = site.categories[category].size %}
		{% if loopSize >= 3 %}{% assign loopSize = 3 %}{% endif %}
		{% for idx in (0..loopSize) %}{% unless forloop.last %}
			<li>
				<a href="{{ site.categories[category][idx].url }}">{{ site.categories[category][idx].title }}</a>
				, <span class="entry-date"><time datetime="{{ site.categories[category][idx].date | date_to_xmlschema }}" itemprop="datePublished">{{ site.categories[category][idx].date | date_to_string }}</time></span>
			</li>
		{% endunless %}{% endfor %}
	</ul>
</div>
{% endfor %}