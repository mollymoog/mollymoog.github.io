---
layout: post
title:      "CLI Reflection"
date:       2020-09-13 20:27:08 +0000
permalink:  cli_reflection
---


In the three weeks leading up to our first project, I was easily lulled into a sense of safety with the Learn modules; fooling around with the code until the red circle turned to green. While the coding itself wasn’t always easy or straight-forward, I knew what the end goal was, and once all the tests were green, I could move on. Week four — project week hit hard. Not only was the end goal up to us, but there weren’t any red circles to let us know that there was still work to be done. 

When it comes to the internet, where endless scrolling has become second-nature, stopping points are few and far between. Once I had my API scrape working, I found myself buried in information. Not sure where I wanted to go with it, I spent most of my time fooling around in pry. I got to know my dataset, and started to understand its limitations. Finding myself coming back to the languages section, I focused on creating a CLI that would guide users through selecting a plant and learning what that plant is called in english, french, or spanish. With a goal in mind, and the error messages as my red and green circles, I found my way through the first project.

Here’s a method that makes me smile:

```
def self.page_back
   if @@page_number < 2
     @@page_number
   else
     @@page_number -= 1
   end
 end
 ```

