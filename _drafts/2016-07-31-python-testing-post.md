---
title: "Python testing post!"
---

I made a script that lets you move any file from a draft to a post and will
update the date for you automatically.

Here is the code:

{% highlight python %}

import os
import datetime

def main():
    posts = []
    for d1, d2, d3 in os.walk("_drafts"):
        for file in d3:
            if file.lower().endswith("md"):
                posts.append(file)
    
    print "Which file do you want to publish?"
    count = 1
    for post in posts:
        print str(count) + ": "+ post
        count += 1
    selected_post = raw_input() 
    rename_post(posts[int(selected_post)-1])

def rename_post(filename):
    # remove the original date from the front of the filename
    # and add the current date (in proper format)
    if filename[0:2] == "20":
        print filename
        new_name = str(datetime.date.today()) + filename[10:]  
        os.rename("_drafts\\" + filename, "_posts\\" + new_name)

if __name__ == "__main__":
    main()

{% endhighlight %}
