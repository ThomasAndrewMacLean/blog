---
layout: post
title: Creating an array in Shopify Liquid and adding objects to it.
---

The way to create an empty array in Shopify is assigning an empty string and splitting it.

```
{% raw %}{% assign our_array = "" | split: "," %}{% endraw %}
```

Now to add stuff to the array we create new array from the object we want to add.
We use the double reverse trick for this:

```
{% raw %}{% assign object_to_add_as_array = object_to_add | reverse | reverse %}{% endraw %}
```


And then we concatenate the two arrays into a new array.

```
{% raw %}{% assign our_array = our_array | concat: object_to_add_as_array %}{% endraw %}
```

On the internet you find some examples that just uses "push", but this is an array function that Jekyll added, and is not a part of Liquid.
