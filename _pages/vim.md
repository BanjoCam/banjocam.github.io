---
permalink: /vim/
layout: single
title: "Vim Cheatsheet"
---

<hr>
<span style="font-size: smaller">
### Add line above or below a certain character  
_For example, add a new line above/below every comment in code_
{% highlight vim %}
:g/key/norm oTextToInsert
{% endhighlight %}
(just leave "whatever you want" blank and use a capital O to add the line above!)  
[source](https://stackoverflow.com/questions/9027159/search-for-string-and-add-line-in-vi-vim) also: [all about the normal command](http://learnvimscriptthehardway.stevelosh.com/chapters/29.html)

### Regex match start of line only
Just add ^ to the start of the search. (Works well with the above normal command!) eg:
{% highlight vim %}
:g/^echo/norm Oecho.
{% endhighlight %}
(this adds a newline echo above every echo command in the batch file, but NOT about @echo OFF lines.)
</span>
