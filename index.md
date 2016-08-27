---
layout: default
---

Hello, I'm Steven Chen! I'm an undergraduate student at the [University of Texas at Austin](https://www.cs.utexas.edu) majoring in Computer Science. At UT Austin, I am a [Turing Scholar][turing] and [Dean's Scholar][deans], as well as a research assistant working on computer vision and machine learning. 

I'm interested in machine learning, backend development, computer vision, AI, and [IoT][iot], among many other things. Recently, I have been involved in iOS development, as well as competitive programming.

Last summer, I interned at Google in Mountain View, where I worked on [Google Photos][photos] MapReduce backend. Before that, I interned at [RetailMeNot][rmn] in Austin on backend services.

You can find my [resumé here][resume].

In my free time, I like traveling, playing music, auto racing, video games, music and sci-fi. Here are a couple of [my favorite][favorites] board games and PC games. I'm also a [Google Local Guide][local], and I enjoy posting reviews
and photos of places I go on Google Maps.

I post about things I find cool or interesting at [my blog][blog], feel free to take a look below!

<br />
<br />
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