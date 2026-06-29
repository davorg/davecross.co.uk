---
layout: single
title: "Looking for the Wrong Dave?"
permalink: /wrong-dave/
---

If you've arrived here after searching for **Dave Cross** or **David Cross**, there's a good chance you're looking for someone else.

Over the years I've received emails intended for football coaches, comedians, Photoshop experts and other people who happen to share my name. Rather than simply replying "wrong Dave", I thought it would be more useful to point people towards the person they were actually trying to find.

## The Dave You're Looking For?

{% for dave in site.data.daves %}

### {{ dave.name }}

{{ dave.description }}

{% if dave.keywords %}

**You might be looking for this {{ dave.name | split: " " | first }} if your search included:**

{% assign list = dave.keywords | array_to_sentence_string: "or" %}
{{ list | replace: ", or ", " or " }}

{% endif %}

{% if dave.url %}
**More information:** <{{ dave.url }}>
{% endif %}

---
{% endfor %}

## Still not sure?

If none of these look right, then there may be yet another Dave or David Cross that I've not discovered yet. Please let me know and I'll happily add them to the list.

