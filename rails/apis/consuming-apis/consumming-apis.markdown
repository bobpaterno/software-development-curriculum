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
 
- #### Download and installation

The latest version of Active Resource can be installed with RubyGems:

  `sudo gem install activeresource`

Or added to a Gemfile:

  `gem 'activeresource'`

- #### Configuration and Usage

Putting Active Resource to use is very similar to Active Record.  It's as simple as creating a model class
that inherits from ActiveResource::Base and providing a <tt>site</tt> class variable to it:

  `class Person < ActiveResource::Base
      self.site = "http://api.people.com:3000"
  end`

Now the Person class is REST enabled and can invoke REST services very similarly to how Active Record invokes
life cycle methods that operate against a persistent store.

   Find a person with id = 1
   tyler = Person.find(1)
   Person.exists?(1)  # => true

As you can see, the methods are quite similar to Active Record's methods for dealing with database
records.  But rather than dealing directly with a database record, you're dealing with HTTP resources (which may or may not be database records).

[activeresource on Github](https://github.com/rails/activeresource)

### httparty

- #### Install

`gem install httparty`

- #### Examples

```ruby
# Use the class methods to get down to business quickly
response = HTTParty.get('https://api.stackexchange.com/2.2/questions?site=stackoverflow')

puts response.body, response.code, response.message, response.headers.inspect

# Or wrap things up in your own class
class StackExchange
  include HTTParty
  base_uri 'api.stackexchange.com'

  def initialize(service, page)
    @options = { query: {site: service, page: page} }
  end

  def questions
    self.class.get("/2.2/questions", @options)
  end

  def users
    self.class.get("/2.2/users", @options)
  end
end

stack_exchange = StackExchange.new("stackoverflow", 1)
puts stack_exchange.questions
puts stack_exchange.users
```

[httparty on Github](https://github.com/jnunemaker/httparty)

### faraday

Faraday is an HTTP client lib that provides a common interface over many adapters (such as Net::HTTP) and embraces the concept of Rack middleware when processing the request/response cycle.

- #### Usage

```ruby
conn = Faraday.new(:url => 'http://sushi.com') do |faraday|
  faraday.request  :url_encoded             # form-encode POST params
  faraday.response :logger                  # log requests to STDOUT
  faraday.adapter  Faraday.default_adapter  # make requests with Net::HTTP
end

## GET ##

response = conn.get '/nigiri/sake.json'     # GET http://sushi.com/nigiri/sake.json
response.body

conn.get '/nigiri', { :name => 'Maguro' }   # GET http://sushi.com/nigiri?name=Maguro

conn.get do |req|                           # GET http://sushi.com/search?page=2&limit=100
  req.url '/search', :page => 2
  req.params['limit'] = 100
end

## POST ##

conn.post '/nigiri', { :name => 'Maguro' }  # POST "name=maguro" to http://sushi.com/nigiri

# post payload as JSON instead of "www-form-urlencoded" encoding:
conn.post do |req|
  req.url '/nigiri'
  req.headers['Content-Type'] = 'application/json'
  req.body = '{ "name": "Unagi" }'
end

## Per-request options ##

conn.get do |req|
  req.url '/search'
  req.options.timeout = 5           # open/read timeout in seconds
  req.options.open_timeout = 2      # connection open timeout in seconds
end
```

If you don't need to set up anything, you can roll with just the bare minimum:

```ruby
# using the default stack:
response = Faraday.get 'http://sushi.com/nigiri/sake.json'
```

[faraday on Github](https://github.com/lostisland/faraday)


* Item 1 with link
* Item 2 with link

## Sources

* Item 1 with link
* Item 2 with link
