---
layout: post
title: We Can't Win
author: LB
pitch: <q>Damned if you do, damned if you don't?</q>
---
I caught wind of the <a href="http://www.businessinsider.com/npm-left-pad-controversy-explained-2016-3">NPM Kik</a> controversy this evening and before I had a chance to really form an opinion, I came across a <a href="http://www.haneycodes.net/npm-left-pad-have-we-forgotten-how-to-program/">follow-up</a> post which I certainly had feelings about. The author is astounded that

> &hellip; so many packages took on a dependency for a simple left padding string function, rather than taking 2 minutes to write such a basic function themselves.

{% highlight javascript %}
module.exports = leftpad;
function leftpad (str, len, ch) {
   str = String(str);
   var i = -1;
   if (!ch && ch !== 0) ch = ' ';
   len = len - str.length;
   while (++i < len) {
      str = ch + str;
   }
   return str;
}
{% endhighlight %}

> In my opinion, if you cannot write a left-pad, is-positive-integer, or isArray function in 5 minutes flat (including the time you spend Googling), then you don’t actually know how to code.

What suprises me is that the poster took this opportunity to lay into the folks that had dependencies on this library and suggest that they should have written the code themselves -- bearing in mind that the code didn't fail, the dependency system did. IE: this would have happened whether the packaged associated with this debacle was 1 line or 1,000 lines long.

The poster continues to use this opportunity to belittle the community:

> I get the impression that the NPM ecosystem participants have created a fetish for micro-packages.

Suggests they don't like to write code (positioning the notion negatively):

> Rather than write any functions or code, it seems that they prefer to depend on something that someone else has written.

And suggests they are doing so for personal or business reasons (non-technical):

> It feels to me as if the entire job of an NPM-participating developer is writing the smallest amount of code possible to string existing library calls together in order to create something new that functions uniquely for their personal or business need.

He goes on to posit:

> Functions are too small to make into a package and dependency.

And eventually falls back into larger packages &hellip; like those .NET provides:

> We’d all really like a “trigonometry” dependency instead which encompasses many “tricky” functions that we don’t want to have to write ourselves. This is much more akin to how .NET and other frameworks create a “core” library of basic functionality.

Because:

> Such a library is vetted by the creators of the language and pretty much guaranteed to be correct and bug-free.

Yep. Although, maybe we should take a break and remind ourselves that in this specific scenario, the code didn't break. The dependency system did.

> I can’t help but be amazed by the fact that developers are taking on dependencies for single line functions that they should be able to write with their eyes closed.

I think the poster may be trivializing the general approach and seems to be equating the idea that since you *can* do it, you *should* do it.

> In my opinion, if you cannot write a left-pad, is-positive-integer, or isArray function in 5 minutes flat (including the time you spend Googling), then you don’t actually know how to code.

Wow &hellip; I feel this offensively calls out anyone that proactively chooses *not* to manually implement said functionality.

As a counter to the poster's argument, I'd like to suggest that *just because you can doesn't mean you should.* The point of creating a dependency on 11 lines of code may be more nuanced than they poster is acknowledging or understands. In fact, it most likely isn't about the *simplicity* of the code as much as it is about **risk**. Given the confidence of the writer's tone, I imagine that the author has *not* been in a bind where his own, 11 line, *simple* code block missed something and broke the internet.

[Heartbleed](http://gizmodo.com/how-heartbleed-works-the-code-behind-the-internets-se-1561341209) anyone?

> &hellip; the actual breach that's bringing the internet to its knees happens in this tiny line of code:

{% highlight c %}
memcpy(bp, pl, payload);
{% endhighlight %}

<a href="http://embeddedgurus.com/barr-code/2014/03/apples-gotofail-ssl-security-bug-was-easily-preventable/">Goto Fail</a>?

{% highlight c %}
if ((err = SSLHashSHA1.update(&hashCtx, &signedParams)) != 0)
    goto fail;
    goto fail;
    ...
{% endhighlight %}

*Easily Preventable* as the article says? Sure. Hindsight is 20/20.

> Just ask the React team how well their week has been going, and whether they wish they had written those 11 lines for left-padding a string themselves.

Really? Is that really what they're thinking? Maybe. I'm curious, are they going to go in, re-evaluate and potentially rip out every *simple* dependency they have < 20 lines? Or, maybe < 100 lines? &hellip; or < 200 lines? Is that really the answer? Really?

Read the comments to the post. There are clearly 2 sides - one feels fed up and the other is defending dependencies while trying to explain higher level programming concepts to the best of their ability given the medium.

There are many acceptable software strategies. It seems unfair to trivialize the dependency practices the NPM community has landed on - and use this opportunity of a brittle dependency system to rail on small dependencies in general. At the end of the day, my only point is that, right or wrong, this particular incident does the case make for not having dependencies of some arbitrarily small size. The same outcome would have happened if someone had pulled a large, popular, 10,000 line pacakge out of the system.

And it is under these rules that I guess we're <q>Damned if we do, damned if we don't.</q>