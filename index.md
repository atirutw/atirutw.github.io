---
title: Home
---

# Home
Hi! Welcome to my blog site thingy! I assume you've read my GitHub profile? Most of the information is there, but to recap: I'm Atirut, you may otherwise know me as Wattana. I'm interested in lots of nerdy topics, yada yada yada. This is where I ramble on and on.

## Recent posts

{% if site.posts and site.posts.size > 0 %}
{% for post in site.posts limit: 5 %}
- [{{ post.title }}]({{ post.url | relative_url }}) — {{ post.date | date: "%b %-d, %Y" }}
{% endfor %}

[View all posts]({{ '/posts/' | relative_url }})
{% else %}
No posts yet.
{% endif %}
