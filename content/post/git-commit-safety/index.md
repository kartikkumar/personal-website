---
title: Git commit safety
date: 2014-03-26 15:22:08+00:00
#summary:
draft: false
featured: false
tags: ["git","tech"]
# Featured image
# To use, place an image named `featured.jpg/png` in your page's folder.
# Placement options: 1 = Full column width, 2 = Out-set, 3 = Screen-width
# Focal point options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
# Set `preview_only` to `true` to just use the image for thumbnails.
#image:
#  placement: 3
#  caption: ""
#  focal_point: "Smart"
#  preview_only: false
#  alt_text:
---

###### ![Git commit horror](http://rafflesmedicalgroup.com.sg/ImgCont/2641/cant-stop-pulling-my-hair.jpg)

_CREDIT: [Raffles Medical Group](http://rafflesmedicalgroup.com.sg/ImgCont/2641/cant-stop-pulling-my-hair.jpg)_


I don't know if I'm the only one that faces it, but I seem to regularly edit the contents of a local Git branch, add/remove files, commit, only to realise that I've been working on the wrong branch! Pulling-your-hair-out kinda stuff when you do it time and time again!

<!-- more -->

I've Googled this a bit and it doesn't seem like there is a "safe mode" for committing. There are a number of [StackOverflow](http://www.stackoverflow.com) threads that suggest solutions (e.g., [Git: committed to wrong branch](http://stackoverflow.com/questions/2941517/git-committed-to-wrong-branch), [Git mess: commits in the wrong branch](http://stackoverflow.com/questions/12018447/git-mess-commits-in-the-wrong-branch), etc.)

It seems like it's easy enough to fix this error by creating a new topic branch off of the branch with the erroneous commits and then reverting the original branch to the hash before those commits.

This though seems to me to be a roundabout way of doing something that I think should be prevented in the first place.

So how would you go about preventing this? My suggestion would be that the git commit command itself should always take the current topic branch name as an argument. The reason for this is that you are then forced to think about the branch that you're committing to. If you end up passing the wrong branch name to git commit (i.e., not the name of the branch you're currently on), git would throw an error indicating as such.

Seems to me that this is a pretty harmless and failsafe method of ensuring that your commits really are on the right branch. Perhaps having to type the branch name in means that your commit workflow takes 2 seconds longer, but I think that's worth the compromise (could be shortened by autocomplete, though that might also mean that you're less aware of the branch name and autocomplete the wrong one!).

For the die-hards that are out there, there could be a setting (global or local) to switch this behavior on or off.

Anyway, any reason why this wouldn't work? Would love to hear your thoughts!
