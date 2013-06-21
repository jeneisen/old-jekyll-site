---
layout: post
title: "What the foo?"
date: 2013-06-21 00:24
comments: true
categories: 
---

**Questions on Questions**

Learning without questioning. That’s a problem. While learning to program over the past two weeks, I’ve come to realize something: I need to learn to love the questions as much as the answers in order to grow.

Before I so fortunately arrived here [@FlatironSchool](https://twitter.com/FlatironSchool) and discovered that vital piece of info, I dabbled with the world of self-teaching. Some of the resources I attempted to utilize included Codecademy, w3schools, Khan Academy, & even auditing CS classes at UMich. Since the code was never recited aloud to me, the names of variables and methods didn’t cross my mind. One of my goals for this week was to question anything and everything. Quiz yourself until there is no longer a grain left in the argument, I’d say to myself at night. 


To that end, this past week Avi demonstrated examples regarding ruby classes and objects. 

```ruby
class Dog
  def initialize()
  end
end

fido = Dog.new
```

Fido. That name again. Why do I learn about this dumb dog named Fido every few months. Who is Fido and why don’t I know him? Is he brown? Is he friends with **Foo**? What about bar? or *baz*?

Now that the questions were out of the way, it’s time to dig deeper for an answer. Between every programming resource I’ve come across, there appears to be defined terms to name entities such as methods, variables, data, and commands to help demonstrate an abstract system. These aliases for variables in code examples (like foo and baz listed above) are formally known as **metasyntactic variables**. 

**Background**

To reiterate, within the computing sector, there are definite syntactic and semantic conventions in order to help display an abstraction. Metasyntactic variables define the specific words themselves used by programmers universally to assign a non-semantic yet consistent alias to a command or function to indicate that the word must to be replaced by the programmer him or herself, and exist solely to demonstrate a concept. So, these words are mere logical representations or arbitrary objects, like x and y in mathematics.

**Foo who?**

There seems to be no precise lineage dating the instance of Foo to programming but naturally, many theories have been surmised. Sometime within the 1930s, the word foo was cited in a comic called *Smokey Stover* by Bill Holman to mean essentially nothing - or a nonsense word. For example, according to [RFC Archives](http://www.faqs.org/rfcs/rfc3092.html) in the cartoon many license plates read “FOO” and nonsense expressions could be discovered in backgrounds echoing “He who foods last foos best” and “Where there’s foo, there’s fire." When asked for this choice, Holman stated that he took advantage of the three letters because he saw it in a fortune figure meaning “good luck” or sometimes “happiness” in Chinese depending on the pronunciation. Apparently, the word foo was actually quite popular in the thirties -- appearing in many other comics and cartoons like *The Daffy Duck*.

Then, the term took a **major turn**, specifically towards the military in the 1940s, where it merged with the common metasyntactic variable known as FUBAR. FUBAR, as you probably guessed, stands for “F**ked up beyond all repair.” Even during WWII the term “foo fighters” was coined -- referring to people searching for UFOS aka some mysterious/unknown unidentified flying object. 

Technically, the term foo was probably first maintained in a coding manner by the Tech Model Railroad Club in the 1960s. The term was adopted by MIT and in their “train room” there are two buttons labelled foo and bar. Legend has it that these miscellaneous buttons were re-evaluated for any and all random ideas the MIT hackers were working on at the time, further supporting the notion that *foo* and *bar* refer to mere var names. Foobar even appeared in a systems manual by Digital Equipment Corporation in the late 60s.

**Conclusion**

OK this is starting to make sense now. Programming languages take advantage of arbitrary words in the basic structure of a function so we can be left with “good luck” to get through the actual difficult process of making the function work within the scope of our task at hand even though we may have f**ked up the function beyond all repair. Noted. As we say here at Flatiron, failure is learning. Celebrate failure.  Celebrate your FUBAR function.

```ruby
#foo examples
# Declare the variable foo and set equal to 5
foo = 5

# Declare the variable bar and set equal to 12
bar = 12

# Declare a method named baz, which prints the text 'Hello world'
def baz
   puts 'Hello world'
end

#common metasyntactic variables in ruby
foo, bar, baz, quux, gorp, fred, barney 

bar = foo + baz
#wait, is that really better than 
value = var_1 + var_2
```

Thanks to all these handy resources for the helpful info regarding possible foo citations: [Wikipedia Foobar](https://en.wikipedia.org/wiki/Foobar), [Wikipedia Metasyntactic variable](http://en.wikipedia.org/wiki/Metasyntactic_variable), [RFC Archives](http://www.faqs.org/rfcs/rfc3092.html).