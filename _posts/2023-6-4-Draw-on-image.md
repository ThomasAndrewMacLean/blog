---
layout: post
title: Make annotations on an image and download these as a single file.
---

For a lunch-and-learn session at work I made a quick demo how you could draw onto images.

The demo can be found [here](https://weareantenna.github.io/Image-annotation-demo/).


![_config.yml]({{ site.baseurl }}/images/annotation.png)

In the demo I uncommented script tags to add extra functionality.
It has a file input that reads the image and renders that onto canvas 1.
On a second canvas (positioned absolute on top of the next one) I added event listeners for mouse move (and one for mobile devices).
This draws lines on that canvas. On the export button JS grabs both canvases and renders them on an in memory canvas and saves this as an image using the <a download> click hack.

As a last step I got the webcam stream and drew this on the canvas. On save it would take the current snapshot, with the drawnlines on top.
