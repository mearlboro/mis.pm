---
layout: page
---

<article>
{{ content }}


<h1>projects</h1>

{% for cat in site.categories %}
{% capture category_name %}{{ cat | first }}{% endcapture %}
{% if category_name != 'blog' %}
<a href="/projects/{{category_name}}">
<div class="col-1-of-3 square">
<h4>{{ category_name }}</h4>
</div>
</a>
{% endif %}
{% endfor %}

<br/>

<h1>miscellanea</h1>

{% for p in site.posts %}
    {% if p.categories contains 'blog' %}
        <h3><a href="{{ p.url }}" target="_blank" style="{{ p.hidetitle }}"><br/>{{ p.title }}</a></h3>
        <p><a href="{{ p.url }}" target="_blank">{{ p.subtitle }}</a><br/></p>
        <p>{{ p.description }}</p>
    {% endif %}
{% endfor %}

</article>
