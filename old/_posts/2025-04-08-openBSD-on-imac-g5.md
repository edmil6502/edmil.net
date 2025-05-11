---
layout: post
title: "Installing OpenBSD on an iMac G5"
---
Now that I'm home for the Easter break, I've decided I'll revamp my home server setup. Out with the Optiplex, and in with the iMac! I'd always wanted to self-host using some more interesting hardware, the Optiplex was only ever a temporary solution. I'd say my iMac G5 qualifies as pretty interesting hardware (PowerPC - exotic!), and given that it's just sat around collecting dust, I think it's about time I put it to good use!

# How I did it
The first step is to create a disk that my iMac can boot into. The instructions for the installation procedure can be found [here](https://www.openbsd.org/faq/faq4.html#bsd.rd). I burnt the latest image for 'macppc' onto a DVD (right-click on the .iso file in Finder, and click "Burn to Disk"). From there, it's the standard procedure for booting from an optical disk on Mac - hold 'C' on startup (C for CD). Alternatively, you could use the boot picker by holding 'option' on startup.

Once I'd booted into the OpenBSD install disk, the installation process is pretty self-explanatory from there! Guidance is available on the OpenBSD website, but I didn't really find it necessary. I ended up just wiping my MacOS 10.4 installation (after backing up my home directory), and just using the whole disk for OpenBSD. If I do dual-boot later on, I'll update this post to say how I did it!

The installation mostly seemed to go mostly smoothly, but would run into issues at the end. Sometimes I would get segmentation faults, but there would always be an issue at the final "Relinking the kernel" step. To attempt to remedy this, I downgraded to OpenBSD 7.4, as I'd seen other people online successfully installing using that. Still, I was running into problems - the main issue was that any time I'd use any of the package commands ('pkg_add', 'pkg_info', etc.) I'd get a segmentation fault!

After searching for a solution for a couple of hours, I
