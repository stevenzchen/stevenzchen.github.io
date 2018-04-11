---
layout: default
---

![Stanford](/assets/dc_steven_chen.jpg){:width="350px"}

Hello, I'm Steven Chen! I'm a grad student at Stanford studying computer science, with a focus in AI and computer vision. I completed my undergrad at UT Austin, under the [Turing Scholars][turing] CS honors program.

I've been fortunate to work multiple internships in software engineering and data science. Last year, I was a data science intern at Riot Games, where I worked on machine learning recommendation algorithms for League of Legends. In 2016, I interned at Google, where I worked on [Google Photos][photos] MapReduce frameworks. Before that, I worked at [RetailMeNot][rmn] on backend ranking algorithms.

I'm currently a TA for [CS102 Big Data][cs102], and have TA'd [CS161 Algorithms][cs161] the past two quarters. This summer, I will be interning at NVIDIA, working on deep learning for autonomous vehicles.

You can find my up-to-date **[resumé here][resume]**. If you know me personally, connect with me on **[LinkedIn][linkedin]**!

In my free time, I like to travel, play guitar and saxophone, read, game, [appreciate architecture][arch], and watch Star Trek. Here are a couple of [my favorite][favorites] board games and video games, and here's my gigantic personal [Spotify playlist][spotify]. I'm also a [Google Local Guide][local], with over 1 million photo views on Google Maps!

I post about things I hope are interesting or useful on [my blog][blog], take a look below!

<br />

<h2 class="recent-title">Recent Posts</h2>

<ul class="post-list">
    {% for post in site.posts limit:3 %}
      <li>
        <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
        
        <a class="post-link" href="{{ post.url | prepend: site.baserurl }}">{{ post.title }}</a>
        
        {{ post.content | strip_html | truncatewords: 50 }}

      </li>
    {% endfor %}
</ul>

[turing]: https://www.cs.utexas.edu/turing-scholars
[deans]: https://cns.utexas.edu/honors/honors-programs-center/deans-scholars
[iot]: https://en.wikipedia.org/wiki/Internet_of_Things
[rmn]: http://www.retailmenot.com
[google]: http://www.google.com
[mtnview]: http://www.google.com/about/careers/locations/mountain-view/
[photos]: https://www.google.com/photos/about/?page=auto-backup
[resume]: /assets/steven_chen_resume.pdf
[favorites]: http://amzn.com/w/3M7DGS728ZX5Q
[local]: https://www.google.com/local/guides/
[blog]: /blog
[riot]: http://www.riotgames.com
[arch]: https://mitpress.mit.edu/books/experiencing-architecture
[linkedin]: https://www.linkedin.com/in/stevenzchen
[cs161]: http://cs161.stanford.edu
[cs102]: http://cs102.stanford.edu
[spotify]: https://open.spotify.com/user/stevenzc/playlist/6QPJvtr4AG96c1XUskYHs3?si=2OGtXcHISeSCYOZgKBkpWg
