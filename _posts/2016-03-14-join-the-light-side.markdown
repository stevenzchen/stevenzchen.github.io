---
layout: post
title:  "Join The (solarized) Light Side!"
date:   2016-03-14
---

![Solarized Logo](/assets/solarized-yinyang.png)

You may have noticed that this website has a light amber background that (hopefully!) makes it easier on the eyes. Or, perhaps you didn't even notice at all, because you're using software like [flux][flux] to warm your screen colors and the website looks like everything else on your screen. And then, maybe you did in fact notice, and found it annoying a site would use anything other than white as a background color. So, no matter where you come from, I'd like to take a minute and talk about [Solarized Light][solarized], the color scheme that I use for pretty much everything, and explain why I chose `#fff6e5` instead of `#ffffff`.

## What is it?

[Solarized][solarized] is a color scheme for code syntax highlighting, and is one of the most popular color schemes today. The creator, Ethan Schoonover, spent [six months][newsarticle] designing the palette, using color wheel and lightness relationships to choose the sixteen colors that form the Solarized Light and Solarized Dark schemes. Solarized is present everywhere, from terminal emulators to text editors, IDEs, and even [keyboards][keyboard].

## Why join the light side?

So sure, Solarized is very popular, and plenty of people use it. But why do I use the Light color scheme, or any dark on light color scheme at all? 

This subject is a source of great contention, and one very much based on personal preference, or even on [how different people perceive color][stackoverflow]. I'd like to talk about why I choose the light side over joining the dark side: (besides Yoda, of course!)

* #### Easy to read, easy on the eyes

I find Solarized Light very easy to read: its look and feel resembles that of an old book under an incandescent bulb, or that of an old Kindle underneath the shade. The soft yellow tones help decrease the popping of the TODO

* #### Many others joined the Light

TODO Peer pressure, man! 

* #### Glossy displays

TODO

## But, the dark side has cookies!

TODO

## Why use it for the site?

TODO: mixes well with other websites, people like dark text on white background for the web, comfortable reading of code snippets.

**Java:**
{% highlight java %}
public class Fibonacci {
    public static void main(String... args) {
        int num = 303;
        int fibResult = fib(303);
        System.out.printf("The %dth Fibonacci number is %d.", num, fibResult);
    }

    public int fib(int n) {
        int prev = 0;
        int curr = 1;
        int result = 0;
        for (int i = 1; i < n; i++) {
            result = prev + curr;
            prev = next;
            next = result;
        }
        return result;
    }
}
{% endhighlight %}

**Python:**
{% highlight python %}
def fib(n):
    prev = 0
    curr = 1
    result = 0
    for _ in range(1, n):
        result = prev + curr
        prev = next
        next = result
    }
    return result

num = 303
fib_number = fib(num)
print("The {}th Fibonacci number is {}.".format(num, fib_number))

{% endhighlight %}

**Swift:**
{% highlight swift %}
func fib(n: Int) -> Int {
    var prev = 0
    var curr = 1
    var result = 0
    for _ in 1 ..< n {
        result = prev + curr
        prev = next
        next = result
    }
    return result
}

let num = 303
let fibNumber = fib(num)
println("The \(num)th Fibonacci number is \(fibNumber).")
{% endhighlight %}

TODO Explain why I don't use the full scheme: it's a compromise!

## Try it out!

TODO add links

[solarized]: http://ethanschoonover.com/solarized
[flux]: https://justgetflux.com
[newsarticle]: http://observer.com/2015/02/meet-the-man-behind-solarized-the-most-important-color-scheme-in-computer-history/
[keyboard]: https://nyoobserver.files.wordpress.com/2014/12/screen-shot-2014-12-17-at-10-26-35-pm.png
[stackoverflow]: http://graphicdesign.stackexchange.com/questions/15142/which-is-easier-on-the-eyes-dark-on-light-or-light-on-dark