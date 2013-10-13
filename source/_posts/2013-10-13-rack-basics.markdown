---
layout: post
title: "Rack Basics"
date: 2013-10-13 20:04
comments: true
categories: [Rack, Proc, Sinatra, Rails]
---
Today I explored Rack, an awesome API connecting web servers and web frameworks by Christian Neukirchen. Here is an <a href="http://chneukirchen.org/blog/archive/2007/02/introducing-rack.html" target="_blank">introduction article</a> by Christian Neukirchen. 

<a href="http://rack.github.io/" target="_blank">Rack</a> was insipired from python's <a href="http://wsgi.readthedocs.org/en/latest/">WSGI</a>.

<h3>What is Rack?</h3>
To put in the words of Christian,</br>
<p style="font-style:italic;margin:1.5em;">Rack provides a minimal, modular and adaptable interface for developing web applications in Ruby. By wrapping HTTP requests and responses in the simplest way possible, it unifies and distills the API for web servers, web frameworks, and software in between (the so-called middleware) into a single method call.</p>


Instead of going deeper in documentation, I'll walk through what exactly Rack is, and how it fits in different web-frameworks in Ruby. I've put the references at the end of the post, which helped me understand Rack.

<!-- more -->

Rack is very simple yet very powerful tool. Rack has <a href="http://rack.rubyforge.org/doc/SPEC.html" target="_blank">specifications</a> on how Rack application and web server should communicate. As long as you follow them, you don't need 'rack' gem to develop you framework.

<p style="font-style:italic;margin:1.5em;">A Rack application is a Ruby object(not a class) that responds to <span style="text-decoration:underline">call</span>. It takes exactly one argument, the environment and return an Array of exactly three values: The status, the headers, and the body.</p>

<h3>TODO</h3>
{% gist 6963372 %}
<h3><span style="text-decoration:underline">References</span>:-</h3>
<div style="margin-left:50px;">
<ol>
	<li><a href="https://github.com/rack/rack/wiki/Tutorials" target="_blank">Rack Tutorials</a></li>
	<li><a href="http://rubylearning.com/blog/a-quick-introduction-to-rack/" target="_blank">A Quick Introduction to Rack by Satish Talim</a></li>
	<li><a href="http://m.onkey.org/ruby-on-rack-1-hello-rack" target="_blank">Ruby on Rack #1 by Pratik Naik</a></li>
	<li><a href="http://m.onkey.org/ruby-on-rack-2-the-builder" target="_blank">Ruby on Rack #2 by Pratik Naik</a></li>
	<li><a href="http://net.tutsplus.com/tutorials/exploring-rack/" target="_blank">Exploring Rack</a></li>
	<li><a href="https://devcenter.heroku.com/articles/static-sites-ruby" target="_blank">Creating Static Sites in Ruby with Rack</a></li>
	<li><a href="http://chneukirchen.org/blog/archive/2007/02/introducing-rack.html" target="_blank">introduction article by Christian Neukirchen</a></li>
	<li><a href="http://library.edgecase.com/rails-routing-and-rack-endpoints" target="_blank">RAILS 3 ROUTING AND RACK ENDPOINTS by Matt Yoho</a></li>	
</ol>	
</div>
<ul>
<li style="font-style:italic;">PS: The whole credit of this article goes to the author of <em>References</em> listed above. I have just jotted down, what I learnt today mostly as note for my own reference.</li>
</ul>

