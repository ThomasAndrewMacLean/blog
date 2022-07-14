---
layout: post
title: Setting up new blog.
---

As mandatory, first blog post describes how the blog is set up. All that had to be done is fork the jekyll-now repo in github. They recommend to use your_username.github.io as the name for your repo, as this will automatically be served as a static site on that url.

But you can also save it under a other name and use githubpages (settings > pages) to serve the root folder as your blog. You will need to add the name of the repo to the \_config.yml file. 

![_config.yml]({{ site.baseurl }}/images/config.png)

Alternatively you can host your blog on a custom domain. This can be done by adding a CNAME file to your repository, or by using the settings interface. After you add the name (blog.thomasmaclean.be in my case) you should head over to your DNS records and add a CNAM record for blog that redirects to your_username.github.io.

In the \_config.yml file you can fill in some other stuff like your name, social links. Plenty of comments help you do this. Then in the \_posts folder you see an example post that you can edit, as I am doing now, in your browser in github. After any push to the master branch it will trigger a build and your new blogpost will be live 🥳.
