---
layout: default
---

![Stanford](/assets/dc_steven_chen.jpg){:width="350px"}

Hello, I'm Steven Chen. I'm currently a grad student at Stanford studying Computer Science, with a focus in artificial intelligence and computer vision. I completed my undergrad at the University of Texas at Austin, under the [Turing Scholars][turing] CS honors program.

I've been fortunate to work multiple internships in software engineering and data science. My most recent internship was at Riot Games in 2017 as a data scientist, where I worked on machine learning recommenders for League of Legends. In 2016, I interned at Google, where I worked on [Google Photos][photos] MapReduce frameworks. Before that, I worked at [RetailMeNot][rmn] on backend algorithms.

You can find my updated **[resumé here][resume]**.

In my free time, I like to travel, play guitar and saxophone, game, [marvel at architecture][arch], and watch Star Trek. Here are a couple of [my favorite][favorites] board games and PC games. I'm also a [Google Local Guide][local].

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