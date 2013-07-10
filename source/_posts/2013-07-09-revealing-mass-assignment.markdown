---
layout: post
title: "Revealing mass assignment"
date: 2013-07-09 23:38
comments: true
categories: 
---

This past weekend I dove head first into Rails. I quite literally created over seven applications just to familiarize myself with the commands and the generated file system with a clear goal of debunking some of the magic of Rails.I frequently came across the same error regarding “mass assignment.” The simple hassle-free fix was to add the attribute to attr_accessible and *poof* no more error. Although that temporarily fixed my error, this mass assignment concept was still fuzzy. Even the ruby guides surprisingly appeared to be unhelpful to a mere beginner -- as most of the issues surrounding mass assignment have to do with security breaches, a topic I will go into at a later date.

**The definition**
Mass Assignment is the convention Rails assigns the act of constructing your object with a parameters hash while you are assigning many values to attributes with one single assignment operator. Lacking mass assignment would mean a lot of manual labor drawing assignment statements for each and every attribute.
```ruby
class Movie < ActiveRecord::Base

end

#What mass assignment lets us do
attributes = {:name => "The Emperor's Club", :star => "Kevin Kline", :year => 2002}
movie = Movie.new(attributes)
Movie.create(:name => "The Emperor's Club", :star => "Kevin Kline", :year => 2002)
Movie.update(:name => "The Emperor's Club", :star => "Kevin Kline", :year => 2002)
#for any of the above code to work, mass assignment must be allowed for for each attribute assigned in hash.
movie.name
movie.star
movie.year
```
```ruby
#Without mass assignment
attributes = {:name => "The Emperor's Club", :star => "Kevin Kline", :year => 2002}
movie = Movie.new(attributes)
movie.name = attributes[:name]
movie.star = attributes[:star]
movie.year = attributes[:year]
movie.name
movie.star
movie.year etc.
```


**Attr_accessible**
The keyword attr_accessible allows developers to assign specific attributes open to mass assignment. 

Under the hood of the attr_accessible we have a method that looks like

```ruby
  def initialize(attributes_hash)
    attributes_hash.each do |k,v|
      self.send(("#{k}="), v)
    end
  end
end
```

This code takes in an arbitrary amount of key value pairs. Mass assignment  permits us to set a bunch of attributes at once. For each k/v pair sent in above, the name of the key becomes the name of an attribute setter method and the value associated with the key is the name of the value you want to pass to that method. The ruby send method then permits you to call the method name that is the key’s name as well as call the associated value as a param in the key’s method. This is a solid underlying method because we can easily alter the number of attributes in the class and need not worry about editing the initialize method.

Thus without attr_accessible, all attribute fields would be open to mass assignment leading to a potentially perilous situation.


**Security Issue**
Not going to go super indepth here *yet*, but essentially because rails conventions are so, well - conventional - it’s not too tough to merely guess attribute names like :user or worse, :admin. Funny story, actually in order for a developer named Egor Homakov to prove his point that mass assignment is insecure and dangerous, he actually gave himself access to commmit to the rails repo on github. (read more about his awesome hack or lapse in judgement or what he calls “The commit that changed my life” [here](http://egorhomakov.com/post/44506887852/commit-that-changed-my-life). Anyway there are two main ways to get around this.

**Whitelisting**
This is what’s safe and we assume everything else is dangerous. Thus we can assume this is super secure because we are being explicit in what we give access. You tell your application what is allowed. Similarly, attr_accessible makes the attributes accessible while the others are protected aka we are being explicit in what we give global access.

```ruby
class Student < ActiveRecord::Base
attr_accessible :name, :tagline, :twitter, :github
end
```

These attributes are unprotected and can be mass assigned and if we add more we need to add them to this list assuming we want them to be accessible.

**Blacklisting**
Just the opposite. Consider all attributes “good” unless they come from explicit source x. Similarly, the attr_protected method says that the written attributes are protected while everything else IS accessible. 

```ruby
class Student < ActiveRecord::Base
attr_protected :is_admin
end
```

Above we are protecting the is_admin attribute and all other attributes added at a later time will not be automatically protected like :is_admin.



There ya have it! mass-assignment.


