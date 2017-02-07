---
layout: post
title: "AutoValue: Easy Java Value Classes"
date: 2017-02-06
---

Let's say you want to write a simple Java class to represent an colored polar coordinate. Perhaps you'd whip up something like this:

{% highlight java %}
public class Coordinate {
    double r;
    double theta;
    Color color;

    public Coordinate(double r, double theta, Color color) {
        this.r = r;
        this.theta = theta;
        this.color = color;
    }
}
{% endhighlight %}

Looks fine, right? Well, as you start using the class, you start running into problems:

{% highlight java %}
Coordinate x = new Coordinate(1.5, 60.0, Color.RED);
Coordinate y = new Coordinate(1.5, 60.0, Color.RED);
x.equals(y); // Returns false!
{% endhighlight %}

Oh, forgot to implement `.equals()`!

You fix that and keep working. Then, when you start using a hashMap, you remember that you need to implement `hashCode()` too. 

Finally, the class is ready for others to use, right? Not quite. The `Coordinate` should have private fields and public constructors to control behavior and have immutability, and still needs to check for null as a parameter to the constructor.

In the end, your simple class has turned into this:

{% highlight java %}
public class Coordinate {
    private double r;
    private double theta;
    private Color color;

    public Coordinate(double r, double theta, Color color) {
        this.r = r;
        this.theta = theta;
        if (color == null) {
            throw new NullPointerException("color cannot be null");
        }
        this.color = color;
    }

    public getR() {
        return r;
    }

    public getTheta() {
        return theta;
    }

    public getColor() {
        return color;
    }

    @Override
    public boolean equals(Object obj) {
        if (coord == null || !(obj instanceof Coordinate)) {
            return false;
        }
        Coordinate coord = (Coordinate) obj;
        return (r == coord.getR()) && 
                (theta == coord.getTheta()) && 
                (color.equals(coord.getColor());
    }

    @Override
    public int hashCode() {
        int hash = 1000003;
        hash ^= this.r;
        hash *= 1000003;
        hash ^= this.theta;
        hash *= 1000003;
        hash ^= this.color;
        return hash;
    }
}
{% endhighlight %}

That's a lot of code for a point! 

AutoValue, an open source framework by Google, helps you easily generate robust, immutable value classes in Java. You define a simple abstract class for your value, with static factory methods and abstract getters, and AutoValue does the rest. here's our polar coordinate class, using AutoValue:

{% highlight java %}
import com.google.auto.value.AutoValue;

@AutoValue
public abstract class Coordinate {
    public static Coordinate create(double r, double theta, Color color) {
        return new AutoValue_Coordinate(r, theta, color);
    }

    public abstract double getR();
    public abstract double getTheta();
    public abstract Color getColor();
}
{% endhighlight %}

That's it! AutoValue will automatically generate a hidden, concrete `Coordinate` class, with proper private fields and exposed getters. It'll also implement `hashCode()` and `equals()`, and check for null too.

You would use the class just as you'd expect:

{% highlight java %}
Coordinate x = Coordinate.create(8.0, 46.5, Color.BLUE);
Coordinate y = Coordinate.create(8.0, 46.5, Color.BLUE);
System.out.println(x.getColor());
x.equals(y); // Returns true
Coordinate z = Coordinate.create(1.0, 3.0, null); // Throws Exception
{% endhighlight %}

AutoValue is completely invisible to the user: they interact solely through the interface of your abstract class, and use your abstract class' static factory methods to create new instances.

So, how does AutoValue work? In short, it's a framework that runs as an annotation processor in the java compiler, generating a concrete class implementing your abstract class that fills in the gaps for you, implementing the `AutoValue_Object` without any trace to the user.

## Conclusion

Many developers coming from other programming languages find Java's lack of a tuple or simple struct very annoying, and thus write small value classes to aid them in storing and returning compound values. However, these quick and dirty implementations tend to be flimsy and can result in serious errors down the line, while a thorough and detailed implementation can be tiring and even difficult to implement properly. AutoValue comes to the rescue here, generating robust and expressive value classes from short, readable abstract classes, while staying completely user-invisible. I'd suggest giving it a shot the next time you're writing Java!

*AutoValue documentation and usage guide [here][autovalue]*

[autovalue]: https://github.com/google/auto/blob/master/value/userguide/index.md