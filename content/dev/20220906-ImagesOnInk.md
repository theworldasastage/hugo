---
title: "How to fix the Ink bug that hides choices with images?"
date: 2022-09-06
categories: ["fix"]
tags: []
type: "dev"
image: img/dance.jpg
draft: false
---

[Ink](https://www.inklestudios.com/ink/) is a fantastic tool to write _choose your own adventure_ type of games. But there is a very annoying bug that can make your experience horrible : 

> When you add an image on your story, sometimes the choices under it don't appear.

Long story short, it's due to the fact that ink does not wait to the image to be loaded to know what size it will take...

Here is a quick fix we used for [our game](https://stepwise.itch.io/midelle-bgw) during the [Ink Jam 2022](https://itch.io/jam/inkjam-2022).

# The fix

To apply the fix, after a web export, open `main.js` and look for the line (should be around line 34) : 

```javascript
    var storyContainer = document.querySelector('#story');
```

And replace it with : 

```javascript
    var storyContainer = document.querySelector('#story');
    // Extend height to fit
    setInterval(() => {
        var needToScroll = (storyContainer.style.height !== contentBottomEdgeY()+"px");
        storyContainer.style.height = contentBottomEdgeY()+"px";
        if (needToScroll){
            scrollDown(contentBottomEdgeY());
        }
    }, 500)
```

# What it does

Instead of computing the container size once and sometimes do it too early, this piece of code computes the new container size every 0.5s and scroll to bottom if the size changes. During our tests it seems to do exactly what we excpect with images and the same as before when there is no images.





