---
layout: post
title: Trustpilot API.
---

A client wanted to show its Trustpilot reviews on their webshop, but wanted more options than the Trustpilot Widget allowed.
Once you login to the Trustpilot Business portal you can get an API key and use that to get the data.

The following 3 endpoints provided me with all the data I needed for the job:

```javascript
        'https://api.trustpilot.com/v1/business-units/{{ BUSINESS_ID }}/reviews?apikey={{ APIKEY }}&stars=3,4,5&language=en'
```

This gives you the service reviews. The Weglote javascript object gave me the information about the current language, and I added an eventlistener 
to check when the user would change language to fetch new reviews in the correct language.

```javascript
        'https://api.trustpilot.com/v1/business-units/{{ BUSINESS_ID }}?apikey={{ APIKEY }}'
```

Of course, we also want to show the overall score, and the amount of reviews. This API endpoint provided this data, as well as an endpoint to get the
green stars image to show on your site.

```javascript
      'https://api.trustpilot.com/v1/product-reviews/business-units/{{ BUSINESS_ID }}?apikey={{ APIKEY }}&sku={{ SKU }}'
```

A last request was to show the individual product scores for every product. Here we get individual values for value for money and quality.
