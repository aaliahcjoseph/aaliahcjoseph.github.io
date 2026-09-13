---
layout: single
title: "And Other Things"
permalink: /and-other-things/
author_profile: false
---

**This is where all the other things go.**

Not everything needs to become a project. Or a side quest. Or really anything at all.

Sometimes I learn something interesting. Sometimes I have a question I can't stop thinking about. Sometimes I find a story worth sharing. Sometimes there's a very cute dog on the internet and I think you should see it too.

This is where those things go. Things I've learned, things I've noticed, things I found interesting, things that made me laugh, and whatever else has my attention at the moment.

There is no real theme here. That's kind of the point.

---

{% assign things = site.other-things | sort: "date" | reverse %}

<div class="other-things-feed">

{% for thing in things %}

<article class="other-thing-entry">

  <h2>
    <a href="{{ thing.url | relative_url }}">{{ thing.title }}</a>
  </h2>

  <div class="other-thing-meta">
    <span>{{ thing.date | date: "%B %-d, %Y" }}</span>

    {% if thing.tags %}
      <span class="other-thing-tags">
        {% for tag in thing.tags %}
          <span>{{ tag }}</span>
        {% endfor %}
      </span>
    {% endif %}
  </div>

  <p class="other-thing-excerpt">
    {{ thing.excerpt | strip_html | truncatewords: 35 }}
  </p>

  <a class="other-thing-read-more" href="{{ thing.url | relative_url }}">
    Read more →
  </a>

</article>

{% endfor %}

</div>
