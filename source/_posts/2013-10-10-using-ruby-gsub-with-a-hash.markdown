---
layout: post
title: "Using Ruby gsub with a hash"
date: 2013-10-10 22:47
comments: true
categories: ["Ruby", "String", "gsub"]
---
** Gsub with Hash **
We all have used gsub for global substitution of a pattern in string. The cool thing I came across today is, you can use hash to define the replacement.

```ruby
def cool_gsub_with_hash(str)
  str.gsub(/[aeiou]/, 'a' => '1', 'e' => '2', 'i' => '3', 'o' => '4', 'u' => '5')
end

> cool_gsub_with_hash("We all have used gsub for global substitution of a pattern in string. ")

 => "W2 1ll h1v2 5s2d gs5b f4r gl4b1l s5bst3t5t34n 4f 1 p1tt2rn 3n str3ng. "

> cool_gsub_with_hash("hello")

 => "h2ll4"

```
Here we are not restricted with single character replacements:
```ruby
def gsub_word_with_hash(str)
  str.gsub(/H(ello)?i?/, 'Hi' => "Namaste", "Hello" => "Wannakam")
end

> gsub_word_with_hash("Hello Chandan")
 => "Wannakam Chandan"
> gsub_word_with_hash("Hi Chandan")
 => "Namaste Chandan"
```

I found it quite interesting. Courtesy: Bozahidar
