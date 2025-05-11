---
layout: post
title: "edmil.net: More newer! Even improvier!"
---
# The Old Site
I bought this domain nearly a year ago - 14th of April 2024 - and it took quite a long time for me to actually get around to doing anything with it! I set up a machine at home to act as a web server over the Christmas / New Years break for 2024/25, making a simple HTML-only website. It wasn't pretty, but it was my very own little corner of the web, and it was entirely self-hosted, which was very important to me!

The machine I used to host it was an old Dell Optiplex I had lying around, which conveniently had Ubuntu 20.04 installed on it already, from when it used to be my main machine. Setting up Apache wasn't too much faff (I'd been through it before already at uni for System Administration). I set up SSH too, so I could remotely administer the machine, as well as a Dynamic DNS (DDNS) client for self-hosting without a static IP. That was a little confusing to set up, but I got it working in the end!

The site itself was very basic, with a brief description of who I am, what I'm interested in, and a picture of some very tasty ribs my friend Lewis got me while we were in Brussels (they're from a place called Amadeus by the way - 28 Euro for Unlimited Ribs, what a barg!). Below is a picture of the old site in Safari 4.0, on my Power Macintosh G4. Obviously it works fine, because there's barely anything to go wrong with it!

![edmil.net on my PowerMac G4](/assets/edmil.net_powermac.jpg)

# The New Site (yes, this one!)
Needless to say, the old site was a bit lacking, and it wouldn't really do! Besides, it was raw HTML, so managing multiple pages and giving them a uniform look and structure was going to be a bit awkward. I needed some kind of framework to manage my site, and get it looking presentable. I've decided on Jekyll, as I have a little bit of experience with it. The [aberCompSoc website](https://abercompsoc.github.io) uses Jekyll, and I'd been tinkering with that in an attempt to set up a 'Directory' page, listing all of the active members of CompSoc (or at least, the ones that don't mind being bothered!). 

One of the key things I'd like my website to be is accessible on older devices. Being a Static Site Generator (SSG - a program which generates HTML web pages from easy-to-write markup languages like Markdown), there's not much in the way of fancy JavaScript, which is one of the biggest reasons modern sites are so slow on older or less powerful hardware. 
Ideally, I'd like my site to be accessible on my old Macintosh SE. For context, that's got an 8MHz Motorola 68000, and 2.5 megabytes of memory, so absolute bare-bones, old-fashioned HTML will be necessary, no style or flair! In order to enable access on such underpowered hardware, I might create a 'lite' version of my site (e.g. 'lite.edmil.net'). I'd still like all the same content to be accessible, so I'd need to either use an existing, super simple SSG, or create my own! One of the options I've found which looks promising is [Zodiac](https://github.com/nuex/zodiac), written in _sh_ and _awk_.
