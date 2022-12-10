---
layout: post
title: Verifying Shopify webhooks using Next JS.
---

One of the ways to add functionality to your shopify store is to subscribe to webhooks. 
Shopify signs every request it sends so you can verify that the incoming request is truely coming from your Shopify store.

In its docs it shows how to do this for Ruby, PHP and Python, but not for node/javascript.
The main thing you need to know is that we need the raw request body to verify the signature, in nextJS this means we need to
export a config object in our api route, declaring we do not want to use a bodyparser.

![_config.yml]({{ site.baseurl }}/images/no bodyparser.png)

```javascript
import { json, buffer } from "micro";
```

Of course we also want the data from within the webhook, for this we use an npm package called micro from vercel.
This gives us a function to get the data from the request, as well as a function to create a buffer from the raw request.

We can use this buffer, together with the apps secret and check if it matches the X-Shopify-Hmac-SHA256 that shopify adds to every request.



![_config.yml]({{ site.baseurl }}/images/verify webhook.png)


```javascript
// Verify incoming webhook.
function verifyWebhook(payload: any, hmac: any) {
  const message = payload.toString();
  const genHash = crypto
    .createHmac("sha256", process.env.API_SECRET!)
    .update(message, "utf8")
    .digest("base64");
  return genHash === hmac;
}
```
