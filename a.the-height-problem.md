# Why height is so messy in Web development ?

It seemed obvious to me that the first component had to be the vertical centering problem.

I mean, any serious web developer has ranted one day about this stupid `vertical-align` that doesn't
do anything near what it's supposed to do.


## A Bit of history
" CSS is bullshit "

Well, that's probably true. CSS is probably one of the most must-know-by-heart languages.
But the particular problem of vertical centering is **NOT** due to CSS. It's due to HTML.

Let me explain.

Back in the early days of the ~~universe~~ Internet, HTML had been created mainly for journalistic purposes. 
The "blog" term didn't exist yet, because almost all web site could be considered as a blog these days.
Complex interfaces that we know today had to wait for around the 2000's to appear. CSS didn't exist, 
JS didn't exist, and even after its creation, JS was considered a bad thing to avoid as often as possible.

The HTML developers made a choice : they set the default mode to a typewriter-like mode.
This is more-or-less the `display: inline` we know today.
This meant that in terms of dimensions, the width of a page was determined by the width of the screen, 
and the content would adapt according to that.

But adapt how ? By increasing the height of the **Document**. And that is where the seed of the vertical centering problem lies. 

## There is a misconception between Screen and Document

When I wrote earlier that Most web developer (me included) often confuses width Screen and Document.

In most of the cases, due to this default mode, the browser *cannot compute height dynamically*. Let's consider this:
```HTML
<div style="">
    <div style="height: 100%">I should be full height</div>
</div>
```

This initial decisions made perfect sense at the time. Doc files work the same way by default. 
The thing that the HTML developers didn't anticipate was that 
**HTML was going to evolve to a more dynamic, complex type of interfaces**.
It went from "purely presentational, without styling" to "presentational with styling and ability to update content" (thanks to JS and CSS).  


TODO parler de pq vertical-align est chelou a cause de ca + cross link vers article vcenter
   

 
