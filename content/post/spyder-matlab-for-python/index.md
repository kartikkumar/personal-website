---
title: Spyder -- MATLAB for Python
date: 2013-07-28 08:13:29+00:00
#summary:
draft: false
featured: false
tags: ["academia","tech"]
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

Having "grown up" on [MathWorks MATLAB](http://www.mathworks.nl/products/matlab/) for my high-level scientific computing applications, I've grown accustomed to the easy, click-to-inspect interface that MATLAB provides when prototyping new algorithms. MATLAB is sold as the _Language of Technical Computing_, with good reason. For rapid prototyping and visualization, it's a great package, and the folks at MathWorks are continuously improving the interface. 

The major downside however is that with great quality comes great prices (or something like that ...). I'm still enjoying being able to use an academic license at the moment, however, not knowing where my future lies, I've realised that it's probably a worthwhile endeavour to expand my horizons, break the shackles, and move to a free, open-source alternative.

Enter [Python](http://www.python.org/). I've been toying with the idea of stepping over to Python for my scientific computing applications for a number of years now, but have mostly held back because of my perception of a lack of maturity of scientific packages. Recently, I've discovered that this perception is completely unfounded. So, I've been gradually moving my scientific computing applications in MATLAB over to Python, using the [PyLab](http://wiki.scipy.org/PyLab) libraries, and so far so good. 

[IPython](http://wiki.scipy.org/PyLab) is a great invention, and I've had the fortune of sitting in on a demo-based class given by the guru himself, [Fernando Perez](http://fperez.org/), at UC Berkeley (unfortunately, I had to leave Berkeley before being able to attend one of the Python bootcamps that I've heard so much about). The class convinced me that Python is mature enough now to really consider giving up on my MATLAB addiction. 

I've tried using [IPython Notebook](http://ipython.org/notebook.html) for a while now, and as much as I love the [](http://www.wolfram.com/mathematica/)/[](http://www.maplesoft.com/products/maple/)-like worksheet approach, it's definitely too cumbersome to prototype code. For all my code-editing purposes, I'm using [Sublime Text 2](http://www.sublimetext.com/2) at the moment (if you're not on the bandwagon yet, what da heck are you waiting for???), however, I miss the ability to inspect the value of variables, objects, structures by a simple click. In addition, MATLAB's debug and profiling utilities are fantastic, and I've only realised since moving to Python how much I make use of them.

So, struggling to figure out whether I can stick to Python for all my high-level code development, I stumbled across [Spyder](https://code.google.com/p/spyderlib/). My first day or so of coding within the Spyder environment is great ... feels like I never left MATLAB! Sure, there are a number of differences, and in particularly, I'm not a fan yet of the editor, which I hope to be able to tinker with (if anyone knows if there's a way to plug the ST2 editor in Spyder, hit me up!). In any case, I'm genuinely happy, and not missing MATLAB for one second!

At the moment, my only remaining gripe with regards to the Python-MATLAB substitution is that I REALLY don't like the 3D plotting capabilities in Python ... plots look well, downright awful. MATLAB is really nice in this regard. If I can solve this, then I think I can say GOODBYE MATLAB ... something to look into ...
