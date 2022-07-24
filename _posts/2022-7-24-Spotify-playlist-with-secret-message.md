---
layout: post
title: Creating a Spotify app to generate playlists containing a secret message.
---

During my holiday I was playing around with the Spotify API and created this little application. I have not submitted it as an app to shopify, so it can only be used for testing by 25 people at the moment.
The gist of it is creating a playlist where when you read the beginning of every song title you read a secret message.

First thing you have to do is register an app at [shopify](https://developer.spotify.com/) that will give as a client ID we need to pass along when fetching our token. We also have to specify the return URL.

After logging in we have the user his token (with playlist-modify-public scope) and ask for the name of the playlist and the secret message. We create the new playlist and then query spotify for every word, trying to find a song where the title starts with this word.


![_config.yml]({{ site.baseurl }}/images/playlist-create.png)

Once this is done we embed an iframe of this playlist using the ID returned when creating it.


![_config.yml]({{ site.baseurl }}/images/playlist-share.png)
