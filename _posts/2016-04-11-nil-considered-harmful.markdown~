---
layout: post
title:  "Nil Considered Harmful: How Optionals Work in Swift"
date:   2016-04-11
categories: code cs ios swift
---

One of my favorite features of Swift, Apple's new programming language
for iOS and OS X development, is how it handles nil values through Optionals.
Optionals address the many problems created by nil values, such as 
inadvertently using nil (null) values from function outputs 
or not initializing fields. These easy-to-make mistakes usually lead 
to confusing and difficult-to-debug runtime crashes, especially in 
compiled languages such as Java, C++, and Objective-C.

Swift Optionals address the nil problem by maintaining a distinction between
variables that have a value and variables that may have the absence of any
value (Optionals). Let's take a look at the basics of how they work!

### Regular (Non-Optional) Variables

Let's start with regular variables, declared with just the type name:

{% highlight swift %}
class Foo {
    var count: Int     // regular variables
    var thing: Int = 5 // regular variable assigned value

    init(numPlayers: Int) {
        // must initialize count before it is used
        count = numPlayers
        // thing already has a value, so it does not need to be set
    }
{% endhighlight %}

Any regular instance variable in Swift must have a non-nil value set before
it is used. That ensures that regular variables will always have a value.
For instance, the following code is incorrect:

{% highlight swift %}
var thing = 5     // type inference: thing is a regular Int
thing = nil       // WRONG: would not compile
{% endhighlight %}

So, what does this mean? For instance, if a function returns a regular 
variable, you are guaranteed to receive a value, and do not have to worry
about receiving nil and crashing. Also, if a function signature takes
a regular variable as a parameter, it is guaranteed to receive a value.

{% highlight swift %}
func doubleValue(num: Int) -> Int {
    // num is guaranteed to have a value
    // doubleValue must also return a value
    return num * 2
}
{% endhighlight %}

The behavior of regular variables is different than that of variables
in other languages. Take Java for example:

{% highlight java %}
class Foo {
    Thing t;

    public static void main(String[] args) {
        // oops, forgot to initialize the Thing!
        int val = doubleValue(t);
        System.out.println("value: " + val);
    }

    int doubleValue(Thing t) {
        return t.getValue() * 2;
    }

{% endhighlight %}

This would crash with a NullPointerException because `t` was not initialized
when `doubleValue` tried to access it.

### Optional Variables

So, what if you need to have nil values? Take, for instance, casting a String
to an Int:

{% highlight swift %}
var inputStr = "123456"
var num: Int = Int(inputStr) // WRONG: can't compile, because some Strings
                             // cannot be successfully parsed into an Int! 
{% endhighlight %}

Casting a String to an Int can fail. If it fails, instead of throwing an
exception or crashing the program, the cast will return `nil`. Thus, 
to handle it, we can store the output into an Optional type, declared
with a `?` after the type:

{% highlight swift %}
var inputStr = "lorem ipsum"
var num: Int? = Int(inputStr) // num will be assigned nil
{% endhighlight %}

The `?` indicates that that particular variable may or may not have a
value. These Optionals do not have to be initialized in the constructor
because they can be nil at any time.

So, how do we use Optional variables in places where we want non-nil 
values? You can do this in three different ways, each suiting a specific
purpose.

#### 1. `if let` Optional Binding

First, a slight segue: constants in Swift (declared with `let` 
instead of `var`) are implicitly non-nil, because a nil constant 
would be quite meaningless.

{% highlight swift %}
let firstStr: String = "first"  // ok
let secondStr: String = nil     // WRONG: will not compile
{% endhighlight %}

So, to run some code only if an Optional has a non-nil value, we can 
use the `if let` construct:

{% highlight swift %}
if let definitelyNumber = Int(someString) { // cast may not work
    print("double the num is \(definitelyNumber * 2)!")
}
{% endhighlight %}

This code states that if the Optional returned from the cast contains an
Int, assign it to `definitelyNumber` and run the code inside the `if`.
Otherwise, move on.

One `if let` can be used on multiple optionals, to make sure 
that all variables you need in a code block have an assigned value.

{% highlight swift %}
if let firstNumber = Int(someString),
       secondNumber = Int(anotherString) {
    print("\(firstNumber) and \(secondNumber), both are safe!")
} else {
    print("parsing was not successful :(")
}
{% endhighlight %}


`if let` is very useful in practice, and helps safely and efficiently
handle `nil` cases, in ways explicitly stated by the developer.
It's a clean way to handle `nil` in code and describe exactly how you 
want your program to behave given an Optional.

#### 2. `?` Optional Chaining

`if let` is a powerful tool, but can lead to long, far indented code,
especially when you have to call many functions that return optional
values and use them. To optimize this, you can use `?` after fields
and functions: this will run the code following the `?` only if
the output of the optional is not `nil`.

{% highlight swift %}
// getThingAtIndex returns an optional, so use ? chaining
// function will only be called if all chained optionals were non-nil
getThingAtIndex(index)?.someOptional?.anotherOptional?.function()
{% endhighlight %}

Optional chaining is short and sweet, and works well when you want to
call a function on an object if the object exists.

#### 3. Forced Unwrapping

This is arguably the simplest technique we can use, and the most dangerous.
We can force the wrapping of an Optional to a regular variable using a `!`
following the variable name. If the Optional contained a null value, this 
could result in your program crashing!

{% highlight swift %}
var num = Int(someString)
return doubleNum(num!)  // WARNING: will crash if num is null
{% endhighlight %}

You can also chain forced unwraps:

{% highlight swift %}
// this code will crash if any optionals were nil
// if everything succeeded, notOptional must have a non-nil value
let notOptional = getThingAtIndex(index)!.someOptional!.function()
{% endhighlight %}

Forced unwrapping should only be used in two situations: when you are
confident that a value does not contain `nil`, or when you want your 
program to crash if a value is not present (for example, when checking for
existence of essential data values for your app).

### Implicitly Unwrapped Optionals

Finally, there are cases when you are sure that an optional will always
have a value, or when its absence of a value means critical failure for
your program. In this case, an implicitly unwrapped optional, declared 
with `!` after the type, may be the best choice. Implicitly unwrapped
optionals can be `nil` but never need to be unwrapped, potentially saving
you time and code, at the risk of crashing on `nil` values.

{% highlight swift %}
var implicit: NSTimer! // implicitly unwrapped optional
implicit.fire()        // no need for ? or if let, will crash if nil
{% endhighlight %}

Implicitly unwrapped optionals should not be used if there is a chance
of it becoming `nil` sometime during execution, because this could 
easily lead to crashes. When in doubt, use a regular optional or a 
regular, non-optional variable.

### That's it!

Those were the basics of Optionals in Swift! If you're interested in
more advanced features of Swift Optionals or want to learn more about
the language, check out the links below:

* [Swift Language Guide][appleswift]: Apple's guide to the Swift Programming Language.
* [Swift Resources][resources]: Videos and sample code for Swift.
* [Swift Tutorials][ray]: Tutorials and articles on Swift on raywenderlich. This is a great resource if you want to learn about Swift and iOS development!

Finally, stay tuned to the blog for future posts on Swift, and thanks for reading!

[appleswift]: https://developer.apple.com/library/ios/documentation/Swift/Conceptual/Swift_Programming_Language/TheBasics.html#//apple_ref/doc/uid/TP40014097-CH5-ID309
[resources]: https://developer.apple.com/swift/resources/
[ray]: https://www.raywenderlich.com/category/swift










