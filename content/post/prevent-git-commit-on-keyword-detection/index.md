---
title: Preventing `git commit` on keyword detection
date: 2014-12-21 17:44:50+00:00
summary: Having used [Git](http://git-scm.com/) to maintain my codebases for a while now, I've started fine-tuning my workflow and I've come across a number of features that I think would be interesting as part of the suite of tools already available.
draft: false
featured: false
tags: ["git","software","version control"]
# Featured image
# To use, place an image named `featured.jpg/png` in your page's folder.
# Placement options: 1 = Full column width, 2 = Out-set, 3 = Screen-width
# Focal point options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
# Set `preview_only` to `true` to just use the image for thumbnails.
image:
  placement: 3
  caption: "Preventing git commit on keyword detection"
  focal_point: "Smart"
  preview_only: false
  alt_text: Preventing git commit on keyword detection
---

Having used [Git](http://git-scm.com/) to maintain my codebases for a while now, I've started fine-tuning my workflow and I've come across a number of features that I think would be interesting as part of the suite of tools already available.

<!-- more -->

The latest one I thought about was triggered by my own experiences and discussions on [Hacker News](https://news.ycombinator.com). In particular, this [comment](https://news.ycombinator.com/item?id=8760714#up_8760977) resonated with me. It's startling to think how easy it is to commit sensitive data to a public repository on a platform as widely used and scoured as [Github](https://github.com). It's somewhat perplexing that Github hasn't addressed this themselves in some way, by, at the very least warning users that they might be potentially exposing passwords, authentication tokens etc. Github does provide a [guide](href="https://help.github.com/articles/remove-sensitive-data) as to how you can remove sensitive data from your repository by using the `git filter-branch` feature, but this doesn't stop you from committing the error in the first place and doesn't mitigate the fact that you might already have been compromised.

My use case for a warning of that nature is somewhat less critical, but nevertheless a feature that I think might be worthwhile having. I routinely find myself making errors when committing, which I have to subsequently correct with small commits immediately after. This of course means that my repository history is littered with commit spurts, as I hastily attempt to correct things. Of course, you can go into the history and [rewrite](https://www.atlassian.com/git/tutorials/rewriting-history) things, by squashing, squishing, flattening and whatever other adjective you can think ok, but this after-the-fact strategy is wholly unsatisfactory in my mind, mostly because it tackles the effect and not the cause of the problem.

So, I've been wondering if it would be simple to implement a feature that would prevent you from executing `git commit` if a given keyword, phrase etc. is found in your codebase. Admittedly, for large codebases, this is likely to incur significant overhead, as each commit would require a text scan, but perhaps this could be reduced by ensuring that only files staged for commit are scanned. To clarify the use case, consider the following:


    
    <code class="bash">$ git commit -m "Commit yet another brick in the wall."
    Commit aborted due to keyword detection:
    
    File: hello.cpp
    Line 12: contains keyword "password"
    
    File: byebye.h
    Line 34: contains keyword "auth_token"
    
    Keyword list defined in /Users/me/hello_world/.git_keyword_filter
    </code>



In my case, the problem I often come up against is the fact that I have example config files that I create for my projects, e.g., [config example for D2D](https://github.com/kartikkumar/d2d/blob/master/config/config.json.example). When I'm testing things and playing around with adding new settings to my application, I often work in the same config file that I end up committing to the repository, with all my local settings (I guess this is probably a mistake in itself, but humour me). It would be great if I could define a keyword filter, perhaps even including filters on a per-file basis.

Maybe this is a silly idea, or maybe there's an existing solution. I think though that as a general feature, this could be something useful to have. I'd love to hear your thoughts!
