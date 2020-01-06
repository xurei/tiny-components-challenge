# PAS FINI


# Why CSS height is so weird ?

Consider this: 
```HTML
<div style="width: 200px; height: 200px; background: #ddd">
    <div style="background: yellow; height: 200px">
        <div style="width: 50%; height: 50%; background: red">
            Hello world
        </div>
    </div>
</div>
```
![The height problem](./a.the-height-problem.png)

Nothing weird here: the child div is half width, half height of its parent. That is what's expected.

But what happens if we remove the height of the direct parent ?
```HTML
<div style="width: 200px; height: 200px; background: #ddd">
    <div style="background: yellow;">
        <div style="width: 50%; height: 50%; background: red">
            Hello world
        </div>
    </div>
</div>
```
![The height problem](./a.the-height-problem2.png)

The height is still defined in the root div, so the leaf should be half
The width seems to use calculate its weight with the grand-parent, but not for the height...
What's going on ?


## A Bit of history
" CSS is bullshit "

Well, that's probably true. CSS is probably one of the most must-know-by-heart languages.
But the particular problem of vertical centering is **NOT** due to CSS. It's due to HTML.

Let me explain.

Back in the early days of the ~~universe~~ Internet, HTML had been created mainly for "journalistic" purposes.
The very first HTML pages were written by researchers showing their results. 
The "blog" term didn't exist yet, but most web sites could be considered as blogs these days.
Complex interfaces that we know today had to wait for around the 2000's to appear. CSS didn't exist, 
JS didn't exist, and even after its creation, JS was considered a bad thing to avoid like the plague.

The HTML developers made a choice : they considered HTML as a kind-of typewriting, flowing document. 
Like a scroll.

This is more-or-less the `display: inline` we know today.

In terms of dimensions, the width of a document was determined by the width of the screen, and the content would adapt according to that.

The height of the document, was determined by the amount of space required to contain the whole document.

It is still like this today, and it actually makes sense in many cases. 
But it was the roots of an issue that is sticking with us since then.  

## Browsers cannot always predict height correctly

### The weirdness of flowing layout


If you are an experienced web developer, you know it is  

When I wrote earlier that 

Most web developer (me included) often confuses width Screen and Document.

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
TODO parler de margin et padding en %, qui prennent la largeur et pas la hauteur pour le calcul

 
