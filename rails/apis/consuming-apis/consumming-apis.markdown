# Comsuming APIs in Rails

### Before Continuing

Make sure you are familiar with RESTful Web services before using the following gems.

  - [REST API Tutorial](http://www.restapitutorial.com/)

## Overview

Prior to Rails 4.0 consuming APIs could have been accomplished with a component included in Rails called ActiveResource. Since Rails 4.0 that functionality has been extracted to the gem `activeresource`. However, gems like `httparty` and `faraday` have become the choice for many developers and are widely implemented. This guide serves as an intro to these three gems.

But wait a minute...

Many popular web services (Twitter, Flickr, Linkedin, etc) have gems created specifically for that service. It is recommended to use such specific gems first if one is available. Here is a list of API client gems already available:

[https://www.ruby-toolbox.com/categories/api_clients](https://www.ruby-toolbox.com/categories/api_clients)

### activeresouce

Model classes are mapped to remote REST resources by Active Resource much the same way Active Record maps model classes to database tables. When a request is made to a remote resource, a REST JSON request is generated, transmitted, and the result received and serialized into a usable Ruby object.
 
- Download and installation

>The latest version of Active Resource can be installed with RubyGems:

  `sudo gem install activeresource`

>Or added to a Gemfile:

  `gem 'activeresource'`

- Configuration and Usage

>Putting Active Resource to use is very similar to Active Record.  It's as simple as creating a model class
>that inherits from ActiveResource::Base and providing a <tt>site</tt> class variable to it:

  `class Person < ActiveResource::Base
      self.site = "http://api.people.com:3000"
  end`

>Now the Person class is REST enabled and can invoke REST services very similarly to how Active Record invokes
>life cycle methods that operate against a persistent store.

   Find a person with id = 1
   tyler = Person.find(1)
   Person.exists?(1)  # => true

>As you can see, the methods are quite similar to Active Record's methods for dealing with database
>records.  But rather than dealing directly with a database record, you're dealing with HTTP resources (which may or may not >be database records).

[activeresource on Github](https://github.com/rails/activeresource)

### httparty

[httparty on Github](https://github.com/jnunemaker/httparty)

### faraday

[faraday on Github](https://github.com/lostisland/faraday)

* Item 1 with link
* Item 2 with link

## Sources

* Item 1 with link
* Item 2 with link
