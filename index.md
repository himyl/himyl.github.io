---
layout: page
title: "Home"
class: home
---

<h1> Hi, I'm Mengyao Li </h1>

<div class="columns" markdown="1">

<div class="intro" markdown="1">
I'm a Senior Applied Scientist at the [Microsoft Office of Applied Research](https://www.microsoft.com/en-us/research/group/office-of-applied-research/). My research focuses on <b>developing human-AI collaboration systems</b>. My work explores ways to model and understand the behaviors and skills of both humans and AI systems, combining techniques from natural language processing, reinforcement learning, data science, psychology, and mental health. 

I received my PhD in Computer Science from the University of Washington, advised by [Prof. Tim Althoff](https://homes.cs.washington.edu/~althoff/). My work has been recognized with an outstanding paper award from [ACL](https://2023.aclweb.org/program/best_papers/), the best paper award from [The Web Conference](https://www.youtube.com/watch?v=4my9W24oifs&t=763s), and the [JP Morgan Chase AI Research PhD Fellowship](https://www.jpmorgan.com/technology/artificial-intelligence/research-awards/phd-fellowship-2023/ashish-sharma). Also, my work has been deployed in the real-world by [Mental Health America](https://screening.mhanational.org/changing-thoughts-with-an-ai-assistant/).


<!-- I'm a fifth-year PhD candidate in the Paul G. Allen School of Computer Science & Engineering at the University of Washington, where I am advised by [Tim Althoff](http://timalthoff.com/).  -->

<!-- <b>I'm on the job market!</b> If you think we would be a good match, please [reach out](mailto:ashshar@cs.washington.edu). -->

<!-- I study <b>how AI can support human well-being</b>. My long-term research goal is to develop human-centered AI systems that can empower people in real-world tasks. Broadly, I'm interested in Natural Language Processing, Human-AI Collaboration, Computational Social Science, and Mental Health. I'm supported by the [JP Morgan Chase AI Research PhD Fellowship](https://www.jpmorgan.com/technology/artificial-intelligence/research-awards/phd-fellowship-2023/ashish-sharma). -->

<!-- My research has been recognized with an <b>outstanding paper award</b> from <a href="https://2023.aclweb.org/program/best_papers/">ACL</a>, a <b>best paper award</b> from <a href="https://www.youtube.com/watch?v=4my9W24oifs&t=763s">The Web Conference</a> and has been <b>deployed in the real-world</b> by <a href="https://screening.mhanational.org/changing-thoughts-with-an-ai-assistant/">Mental Health America</a>. -->


</div>

<div class="me" markdown="1">
<picture>
  <!-- <source srcset='/images/dominik_berlin.webp' type='image/webp' /> -->
  <img
    src='/images/portrait.jpg'
    alt='Mengyao Li'>
</picture>

{:.no-list}
* <a href="mailto:{{ site.email }}">{{ site.email }}</a>
</div>

</div>

<!-- Previously, I was a Research Fellow at Microsoft Research. I have a Bachelor's and Master's degree in computer science from the Indian Institute of Technology, Kharagpur. I have also done research internships at Microsoft Research, University of Illinois at Urbana-Champaign and Adobe Research Lab. Details in my <a href="{{ "/cv/" | relative_url }}">CV</a>. -->

## Featured Projects

<div class="featured-projects">
  {% assign sorted_projects = site.data.projects | sort: 'highlight' %}
  {% for project in sorted_projects %}
    {% if project.highlight %}
      {% include project.html project=project %}
    {% endif %}
  {% endfor %}
</div>

<!-- ## Featured <a href="{{ "/publications/" | relative_url }}">Publications</a> -->

<!-- <div class="featured-publications">
  {% assign sorted_publications = site.publications | sort: 'year' | reverse %}
  {% for pub in sorted_publications %}
    {% if pub.highlight %}
      <a href="{{ pub.pdf }}" class="publication">
        <strong>{{ pub.title }}</strong>
        <span class="authors">{% for author in pub.authors %}{{ author }}{% unless forloop.last %}, {% endunless %}{% endfor %}</span>.
        <i>{% if pub.venue %}{{ pub.venue }}, {% endif %}{{ pub.year }}</i>.
        {% for award in pub.awards %}<br/><span class="award"><i class="fas fa-{% if award == "Best Paper Award" %}trophy{% else %}award{% endif %}" aria-hidden="true"></i> {{ award }}</span>{% endfor %}
      </a>
    {% endif %}
  {% endfor %}
</div> -->

<a href="{{ "/publications/" | relative_url }}" class="button">
  <i class="fas fa-chevron-circle-right"></i>
  Show All Publications
</a>

<div class="news-travel" markdown="1">

<div class="news" markdown="1">
## News

<ul>
{% for news in site.data.news limit:10 %}
  {% include news.html news=news %}
{% endfor %}
</ul>

</div>

<div class="travel" markdown="1">
## Travel

<table>
<tbody>
{% assign future_travel = site.data.travel | where_exp:'item','item.start == null' %}
{% for travel in future_travel %}
  {% include travel.html travel=travel %}
{% endfor %}
{% assign sorted_travel = site.data.travel | where_exp:'item','item.start' | sort: 'start' | reverse %}
{% for travel in sorted_travel limit:10 %}
  {% include travel.html travel=travel %}
{% endfor %}
</tbody>
</table>

</div>

</div>
