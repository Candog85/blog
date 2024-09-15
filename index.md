Hello, My name is Kerdon Chapman, a learning programmer based in NY. I'm learning a variety of languages at the [Brooklyn Steam Center's](https://brooklynsteamcenter.org/) Full-Stack Development pathway.

This will be my devlog in which I'll be going over changes made to my projects and updates to my programming journey.

<br>

# Recent Posts
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title</a>
    </li>
  {% endfor %}
</ul>