---
title: Mining and Stats
categories:
  - Javascript
  - Data Mining
  - SQLite
header:
  image: /images/mound.png
tags:
  - Javascript
---
# [FISH] Milan Kundera 

I've always been a gamer, it relieves stress and does not cost much. It does
cost the time you could of put into something else though. How can we manage 
the time? 

I started playing War Brokers because it was Linux compatible. 
[Warbrokers](http://warbrokers.io) is renowned for its active community of 
interesting players. Here is a link to my OG player profile: 
[Milan Kundera](https://stats.warbrokers.io/players/i/60a6a302d142af1f1d389c83).

You can see that we've had a lot of fun, but there where some tedious aspects
of keeping track of stats, so the project just grew incrementally. It started as
a 20 line replit, then it became a serverless firebase project, and now it is a 
node / sqlite / github hybrid project.

I have learned a lot from this project, ultimately, stick with what you are good
at, which for me, is SQL, So firebase was limiting for me. Also, a lot of these
wonderful services offered online can bite you.

In my case, firebase was free but after changing some deployment settings I got
a bill.

Now MSFISH actively tracks my friends but also tracking the amount of time I 
play - I am trying to keep it under 150 kills per day. 🤐

<figure>
  <img src="{{site.url}}/images/Screenshot from 2023-01-18 16-05-34.png" 
  alt="MSFISH Discord Bot Mining"/>
  <figcaption>MSFISH Discord Bot Mining</figcaption>
</figure>

# [FISH] Repoman

The entire project is hosted on Github with a more detailed breakdown how it 
works in the README.

[https://github.com/ddupas/msfish](https://github.com/ddupas/msfish)

<figure>
  <img src="{{site.url}}/images/Screenshot from 2023-01-18 16-09-06.png" 
  alt="MSFISH Charts Screenshot"/>
  <figcaption>MSFISH Charts </figcaption>
</figure>

[MSFISH Charts](/msfish/)

If you are interested in data mining there are a few interesting things to
chew on here. There is a lot of subtle async / await / promise code in this
project. I feel that the way the charts page accesses its data, using embedded
sqlite is also something I have never seen anywhere, but sql.js, is vn. 🙃

🤡 Ask me about it! 🤡
