---
layout: post
title: "ActiveRecord logger in rails console"
date: 2013-10-12 14:51
comments: true
categories: 
---
This came to my surprise, as I was going through 'The Rails 4 Way' by Obie Fernandez, that we can have our own logger instances in Rails. 

Watch, what ActiveRecord is doing with your query in console itself. :)
{% gist 6947792 %}

I came across blog of Jamis Buck, and he had given on more interesting piece of hack to see the log in console.  In your config/environment.rb define following method:
```ruby
def log_to(stream)
  ActiveRecord::Base.logger = Logger.new(stream)
  ActiveRecrod::Base.clear_active_connections!
end
```

Now you can buffer your logs in a local variable.
```ruby
> log_to STDOUT
=> ..
> Post.find(:first)
  Post Load (0.000138)   SELECT * FROM posts LIMIT 1
=> #<Post:0x1234 ...>
> buffer = StringIO.new
=> ..
> log_to buffer
=> ..
User.first(:first)
=> #<User:0x1234...>
> p buffer.string
=> "\e...." # Logs here
```
This can be found useful at many place you want to check the behavior of certain queries in console.

Thanks Jamis/Obie :)
