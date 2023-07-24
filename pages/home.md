---
layout: home-greetings
author_profile: true
browser-title: "Welcome"
permalink: /
---
# Bonjour! こんにちは！

I'm Mark (Junchen) Jin, a Machine Learning Scientist at PayPal. Currently I'm working on projects related to personalization, knowledge graph, and GenAI.

I graduated from the Master of Science in Machine Learning and Data Science (formerly MSiA) program at the Northwestern University. Prior to this, I obtained my dual bachelor's degrees in Computer Science from the University of Michigan, Ann Arbor, and in Electrical and Computer Engineering from Shanghai Jiao Tong University.

I've been conducting research in graph mining, data mining, and applied machine learning, especially on graph representation learning and graph neural networks.

<!-- {% capture notice-text %}
**I am looking for an internship opportunity for 2023** - please [email me](mailto:jiongzhu@umich.edu) if you have any interesting opportunities to share!
{% endcapture %}

<div class="notice--warning">
  {{ notice-text | markdownify }}
</div> -->


{% include news.html %}

{% if site.data.publication.size > 0 %}
## Publications

<div class="notice">
{% for pubyear in site.data.publication %}
    <h4> {{ pubyear.year }} </h4>
    <ul>
    {% for pubitem in pubyear.publications %}
        <li> 
            {% if pubitem.reference %}
                {% capture pubitem-citation-text %}
                    {% reference pubitem.reference %}
                {% endcapture %}
                {% capture pubitem-citation-title %}
                    <b>{{ pubitem.title | strip }}</b>
                {% endcapture %}
                {{ pubitem-citation-text | replace: "Junchen Jin", "<u>Junchen Jin</u>" | replace: pubitem.title, pubitem-citation-title }}<br>
            {% else %}
                {{ pubitem.authors_year | markdownify | remove: '<p>' | remove: '</p>' | strip }}.
                <b>{{ pubitem.title | markdownify | remove: '<p>' | remove: '</p>' | strip }}</b>.
                {{ pubitem.venue | markdownify | remove: '<p>' | remove: '</p>' | strip }}.<br>
            {% endif %}
            {% if pubitem.paper %} <a href="{{ pubitem.paper }}" style="text-decoration:none" target="_blank" rel="noopener noreferrer">[
                <i class="fas fa-file-alt" aria-hidden="true"></i> Paper
                ]</a>{% endif %}
            {% if pubitem.poster %} <a href="{{ pubitem.poster }}" style="text-decoration:none" target="_blank" rel="noopener noreferrer">[
                <i class="fas fa-file-image" aria-hidden="true"></i> Poster
                ]</a>{% endif %}
            {% if pubitem.slides %} <a href="{{ pubitem.slides }}" style="text-decoration:none" target="_blank" rel="noopener noreferrer">[
                <i class="fas fa-file-powerpoint" aria-hidden="true"></i> Slides
                ]</a>{% endif %}
            {% if pubitem.code %} <a href="{{ pubitem.code }}" style="text-decoration:none" target="_blank" rel="noopener noreferrer">[
                <i class="fas fa-code" aria-hidden="true"></i> Code
                ]</a>{% endif %}
        </li>
    {% endfor %}
    </ul>
{% endfor %}
</div>
{% endif %}

{% if site.data.preprints.size > 0 %}
## Preprints

<div class="notice">
{% for pubyear in site.data.preprints %}
    <h4> {{ pubyear.year }} </h4>
    <ul>
    {% for pubitem in pubyear.publications %}
        <li> 
            {{ pubitem.citation | markdownify | remove: '<p>' | remove: '</p>' }}<br>
            {% if pubitem.slides %} <a href="{{ pubitem.slides }}" style="text-decoration:none" target="_blank">[
                <i class="fas fa-file-powerpoint" aria-hidden="true"></i> Slides
                ]</a>{% endif %}
            {% if pubitem.paper %} <a href="{{ pubitem.paper }}" style="text-decoration:none" target="_blank">[
                <i class="fas fa-file-alt" aria-hidden="true"></i> Paper
                ]</a>{% endif %}
            {% if pubitem.code %} <a href="{{ pubitem.code }}" style="text-decoration:none" target="_blank">[
                <i class="fas fa-code" aria-hidden="true"></i> Code
                ]</a>{% endif %}
        </li>
    {% endfor %}
    </ul>
{% endfor %}
</div>
{% endif %}