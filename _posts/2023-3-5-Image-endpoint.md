---
layout: post
title: NextJS image endpoint.
---

For a project I was saving very small previews of images as base64 strings in a database.
Too show them on the page I first just added all the data as I got it from the server, but soon this got too big of a response for the limits on Vercel.

So I decided to add a /api/preview/imageId.ts endpoint that I could pop in the image's source and fetch it in the backend.
You return the image as a buffer and set the correct headers so the browser knows how to show the image.


```javascript

    const decoded = image.preview
      .toString()
      .replace("data:image/jpeg;base64,", "");
    const imageResp = new Buffer(decoded, "base64");

    res.writeHead(200, {
      "Content-Type": "image/jpeg",
      "Content-Length": imageResp.length,
    });
    
    return res.end(imageResp);
     
```
