---
layout: post
title: "macOS 'System Data' Cleanup"
---
I've got a base model M1 Macbook Air - 8GB RAM, 256GB of storage. While that's nothing to shout about, most of my work is just in plaintext files (notes, code, etc.), which take up very little space, so that amount of storage SHOULD be plenty. Unfortunately, I've had storage issues for months, leading to sync issues, having to move files to external storage, and all sorts of faffing about I could really do without! 

When I'd go into System Preferences and check out the "Storage" section, it would report 120GB being used by "System Data", and wouldn't elaborate any further as to what that actually was - not very useful. I'd need a better way of finding out where the bloat was!

# Locating the Offending Files
The most useful command in this process was `du`. `du` (short for 'Disk Usage') is a standard UNIX tool that tells you how much storage a given directory is using up. The `-s` option ensures the command only prints an output for the files you specify, and the `-h` option outputs the size in human-readable units (i.e. 1GB instead of 1000000000). The `-t` option allows you to specify a threshold, so `-t 1000` won't show anything under one kilobyte in size - handy when you're looking for just the big files.

Most commonly, I was running `du -sh *`, which shows me how much disk space every file or subdirectory in my current working directory takes up. Starting from the root of the filesystem, I'd find where the biggest files/directories were, and keep going until I'd found something that was a) big, and b) unimportant. If there were lots of files, the `-t` option came in handy, and I'd use that to filter out the smaller files, leaving only the big ones.

# The iOS Simulator Files
Most of my storage issues started after I began playing around with iOS development. This required the installation of Xcode, as well as the appropriate iPhone simulators, and of course copies of the current iOS versions (18.1 and 18.2 at the time). When I eventually deleted Xcode, I thought that would be the end of my woes, but unfortunately not. Xcode had left remnants of the iOS simulators (I believe in /Library/), and I couldn't remove them, not even with `sudo rm -rf`! 

Eventually, I came across a possible solution online - disabling "System Integrity Protection", which sounds like a terrible idea. I believe macOS had mistakenly rendered these iOS simulator files completely untouchable, even to someone logged in as root, and was protecting them from removal. Disabling System Integrity Protection is done by booting into Recovery Mode (done on my machine by holding down the power button to view boot options, then going into "Settings"), opening up a terminal (done from the menu bar), typing in `csrutil disable`, and once that's all done, rebooting. 

Once that was done, I was able to remove the offending folders with `sudo rm -rf` - finally! 

Needless to say, System Integrity Protection is something that probably ought not to be messsed with. I've since turned it back on, before I accidentally nuke something important! While it is annoying that it gets in the way of deleting certain frivolous things like the iOS simulators, it's reasurring to know that macOS won't let me do too much damage to it! 
