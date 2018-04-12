---
layout: default
---

![Stanford](/assets/dc_steven_chen.jpg){:width="350px"}

Hello, I'm Steven Chen! I'm a Masters student at Stanford studying computer science, with a focus on computer vision and AI. I completed my undergrad at UT Austin, under the [Turing Scholars][turing] CS honors program.

I am passionate about applying computer vision and AI solutions to help improve people's lives at a large scale. I'm particularly interested in autonomous vehicles and their potential to save lives, reduce traffic congestion, and cut emissions. 

I was fortunate to have [Professor Kristen Grauman][grauman] as my research advisor at UT. Our work on visual attributes was recently published in CVPR 2018 ([paper here][paper]).

I've had the opportunity to learn from several internships in engineering and data science. Recently, I worked at [Riot Games][riot] on machine learning recommendation algorithms for League of Legends. I previously worked at Google on [Google Photos][photos] MapReduce APIs, and at [RetailMeNot][rmn] on ranking algorithms. This summer, I'm looking forward to interning at [NVIDIA][nvidia], where I will be working on deep learning for autonomous vehicles. 

I'm currently a teaching assistant for [CS102 Big Data][cs102] at Stanford, and TA'd [CS161 Algorithms][cs161] previously.

You can find my up-to-date **[resumé here][resume]**. If you know me personally, connect with me on **[LinkedIn][linkedin]**!

In my free time, I like to travel, play guitar, read, play strategy games, and watch Star Trek. I enjoy [appreciating architecture][arch], and I like to drive and keep up with advances in the auto industry. Here are a couple of [my favorite games][favorites]. I'm also a [Google Local Guide][local], with over 1 million photo views on Google Maps!

I post ideas I hope are interesting or useful on [my blog][blog], take a look below.

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
[arch]: https://mitpress.mit.edu/books/experiencing-architecture-second-edition
[linkedin]: https://www.linkedin.com/in/stevenzchen
[cs161]: http://cs161.stanford.edu
[cs102]: http://cs102.stanford.edu
[spotify]: https://open.spotify.com/user/stevenzc/playlist/6QPJvtr4AG96c1XUskYHs3?si=2OGtXcHISeSCYOZgKBkpWg
[grauman]: http://www.cs.utexas.edu/users/grauman/
[paper]: https://arxiv.org/abs/1804.00112
[nvidia]: https://www.nvidia.com/en-us/self-driving-cars/
