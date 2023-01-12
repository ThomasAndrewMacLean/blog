---
layout: post
title: Kop op een kop.
---

This is a simple website (https://kopopeenkop.be) where you can upload a picture. Using AI and tensorflowJS you can remove the background.
In the next step you choose the colour of your mug and then it takes you to a shopify checkout page.

Before you did this it sends the image to a Google cloud function that saves the image to a bucket and returns its ID.
We save both the ID as the chosen colour to cart attributes so we can reuse it later.

After you finish the checkout the shopify webhook triggers another google cloud function, this has all the info from the order and uses this to create an order on printful using its API.
A few days later the client receives a mug with the chosen image printed on it at his doorstep.
