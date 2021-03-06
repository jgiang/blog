---
layout: page
permalink: /about/index.html
title: Jasmine Giang
tags: [Jasmine, Giang, jmoney]
chart: true
---


{% assign total_words = 0 %}
{% assign total_readtime = 0 %}
{% assign featuredcount = 0 %}
{% assign statuscount = 0 %}

{% for post in site.posts %}
    {% assign post_words = post.content | strip_html | number_of_words %}
    {% assign readtime = post_words | append: '.0' | divided_by:200 %}
    {% assign total_words = total_words | plus: post_words %}
    {% assign total_readtime = total_readtime | plus: readtime %}
    {% if post.featured %}
    {% assign featuredcount = featuredcount | plus: 1 %}
    {% endif %}
{% endfor %}

<figure >
	<img src="{{ site.url }}/images/about/sonoma.jpg">
</figure>

<br>
My name is **Jasmine Giang**, and this is my personal blog. It currently has {{ site.posts | size }} posts in {{ site.categories | size }} categories which combinedly have {{ total_words }} words. {% if featuredcount != 0 %}There are <a href="{{ site.url }}/featured">{{ featuredcount }} featured posts</a>, you should definitely check those out.{% endif %} The most recent post is {% for post in site.posts limit:1 %}{% if post.description %}<a href="{{ site.url }}{{ post.url }}" title="{{ post.description }}">"{{ post.title }}"</a>{% else %}<a href="{{ site.url }}{{ post.url }}" title="{{ post.description }}" title="Read more about {{ post.title }}">"{{ post.title }}"</a>{% endif %}{% endfor %} which was published on {% for post in site.posts limit:1 %}{% assign modifiedtime = post.modified | date: "%Y%m%d" %}{% assign posttime = post.date | date: "%Y%m%d" %}<time datetime="{{ post.date | date_to_xmlschema }}" class="post-time">{{ post.date | date: "%d %b %Y" }}</time>{% if post.modified %}{% if modifiedtime != posttime %} and last modified on <time datetime="{{ post.modified | date: "%Y-%m-%d" }}" itemprop="dateModified">{{ post.modified | date: "%d %b %Y" }}</time>{% endif %}{% endif %}{% endfor %}. The last commit was on {{ site.time | date: "%A, %d %b %Y" }} at {{ site.time | date: "%I:%M %p" }} UTC.

I was born and raised in Los Angeles, CA. I am a fourth-year Computer Science major at the [**University of California, Berkeley**](http://www.berkeley.edu/). I am currently an engineering intern at [Codesmith](http://codesmith.io) in Playa Vista, CA. I love eating, and as a result, I am an obsessive yelper. Other hobbies include: taking selfie-stick selfies, watching Food Network, jigsaw puzzling, taking panorama photos, and exploring new places.

<figure>
  <img src="{{ site.url }}/images/about/marin.jpg">
  <figcaption>One of my favorite places: Tiburon, CA</figcaption>
</figure>

