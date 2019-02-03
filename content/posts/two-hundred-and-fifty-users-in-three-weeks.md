---
title: "Two Hundred Fifty Users in Three Weeks"
date: 2019-02-03T12:56:18-05:00
thumbnail: "/images/jobletter-site.png"
draft: false
---

At [three-weeks](https://joecmarshall.com/introducing-jobletter/), the ongoing experiement in writing a [newsletter for junior devs](https://jobletter.io) and [open strategizing](https://joecmarshall.com/one-hundred-users-in-two-weeks/) is in full swing.

Quick recap: Three weeks ago a friend and I launched [jobletter](https://jobletter.io) a job newsletter targeted early career devs looking for quality listings and career information.

Writing about this experience provides an opportunity to chronicle our efforts. If it grows this will be a fun account of why, if not, then we learned a lot, and these posts will teach us more.

So - adding [150 users in one week](https://joecmarshall.com/one-hundred-users-in-two-weeks/) is a big expansion. What happened?

We got a big 'ol bear hug from Hacker News, that's what.

![](/images/jobletter-hug-hn-post.png)

## \*Hugs*

To put into perspective what a [Hacker News](https://news.ycombinator.com) "hug" looks like, here are the stats for this site, [joecmarshall.com](https://joecmarshall.com).

![](/images/jobletter-hug-analytics-joecmarshall.png)

(If it looks like that 2,150 users is jumping up from a number *incredibly* close to zero, well...)

Then a portion of that audience was naturally curious to follow up and see what the fuss was about. Here's how the equivalent numbers look for the [jobletter](https://jobletter.io) referral traffic.

![](/images/jobletter-hug-analytics-jobletter.png)

And in the referral view.

![](/images/jobletter-hug-analytics-jobletter-referrals.png)

## Conversions

You can see in the acquisition dashboard that this traffic translated to 78 goal 1 ("Subscribe") completions, which map to email sign ups - but this is Hacker News! There should be a larger percentage of people signing up who are using adblockers or otherwise blocking GA.

One of the more indirect ways would be to just... go to [Mailchimp](https://mailchimp.com). It's not incredibly precise, but at this small scale, when we're building our subscription base on fits and starts that correspond directly to our activity, we can basically go to mailchimp and see the effects of the spike.

![](/images/jobletter-hug-mailchimp-after.png)

Some nice results! Especially considering the total amount of traffic we ended up getting all the way to our actual [jobletter](https://jobletter.io) sign up form. We picked up the slack from getting people to the site by having a high conversion rate for those who make it all the way there.

![](/images/jobletter-hug-mailchimp-50.png)

![](/images/jobletter-hug-mailchimp-56.png)

Looking at the sign ups driven from the post Sunday night and the continued activity through the next day, we got a growth of over a 100 subscribers - enough to put us over the 250 mark!

## Lessons Learned

1. One lesson learned from the data is that we can experiment with moving the form closer to the traffic. See late in this post for this idea in action (that's *agility*).

2. [Netlify](https://netlify.com) again seems like a great choice for its ability to easily weather these sorts of traffic surges. It would be technological malpractice to host essentially a landing page on a web application framework, (on some low-memory Digital Ocean droplet if we're nasty) but nevertheless, going for the most stripped down, static, easily hosted option has paid off.

3. [Hacker News](https://news.ycombinator.com) is awesome. Sometimes the criticism needs to be taken with a grain of salt - the VC/marketing/growth crowd and the programmer/hacker crowd sometimes results in a sort of split brain - but the quality and distribution of it can tell you a lot.

4. The sugar high off a boost like this lasts for another day or so after the original post, at most. After that it begins to level off. It might eventual shift the needle on something organic, or otherwise support the site in some other way, but the immediate impact is over.

5. The readers of Hacker News seemed to respond to reading about other people struggling with the same barriers and with the same goals (e.g. building something your own, even if it's small). It was a great note of support and validation that even on a small scale, for something that doesn't require vast technical innovation, there's interest in just hearing some one think through things out loud.

## Downsides

There are limits to the success of this sort of strategy. For one, it's difficult to rank articles on any aggregator consistently, and takes a lot of time to analyze, write, edit, and promote new pieces. For another, it's going to be heavily limited by the visibility of the post - there's not much of a possibility that subscribers can drive other subscription growth (virality), for this sort of writing at least - and the half life of an individual post is fairly short.

The strategy we've been using can't be our only option going forward. It won't get us into the 1,000s or drive the sustained growth we want.

We have some ideas... and you'll be seeing them soon (*slide whistle*) but they include, broadly: developing standalone lead magnets, exploring new content forms /channels, and doing some old fashioned product engineering on the newsletter itself.

## Stay in Touch

If getting high-quality, hand-curated, early-career-dev jobs sounds appealing to you - or you just want to follow along at home, sign up for [Jobletter](https://jobletter.io) below. 

And check back - I'll be writing more in the coming weeks.

<link href="//cdn-images.mailchimp.com/embedcode/classic-10_7.css" rel="stylesheet" type="text/css">
<style type="text/css">
    #mc_embed_signup{background:#fff; clear:left; font:14px Helvetica,Arial,sans-serif; }
</style>
<div id="mc_embed_signup">
<form action="https://jobletter.us9.list-manage.com/subscribe/post?u=50452eee01aae18a82d9dd092&amp;id=9b8fa5c4b2" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_blank" novalidate>
    <div id="mc_embed_signup_scroll">
<div class="mc-field-group">
    <label for="mce-EMAIL">Email Address </label>
    <input type="email" value="" name="EMAIL" class="required email" id="mce-EMAIL">
</div>
<div class="mc-field-group">
    <label for="mce-FNAME">First Name </label>
    <input type="text" value="" name="FNAME" class="" id="mce-FNAME">
</div>
<div class="mc-field-group">
    <label for="mce-LNAME">Last Name </label>
    <input type="text" value="" name="LNAME" class="" id="mce-LNAME">
</div>
<div class="mc-field-group input-group">
    <strong>Frequency </strong>
    <ul><li><input type="radio" value="Weekly" name="MMERGE5" id="mce-MMERGE5-0"><label for="mce-MMERGE5-0">Weekly</label></li>
<li><input type="radio" value="Monthly" name="MMERGE5" id="mce-MMERGE5-1"><label for="mce-MMERGE5-1">Monthly</label></li>
</ul>
</div>
    <div id="mce-responses" class="clear">
        <div class="response" id="mce-error-response" style="display:none"></div>
        <div class="response" id="mce-success-response" style="display:none"></div>
    </div>    <!-- real people should not fill this in and expect good things - do not remove this or risk form bot signups-->
    <div style="position: absolute; left: -5000px;" aria-hidden="true"><input type="text" name="b_50452eee01aae18a82d9dd092_9b8fa5c4b2" tabindex="-1" value=""></div>
    <div class="clear"><input type="submit" value="Subscribe" name="subscribe" id="mc-embedded-subscribe" class="button"></div>
    </div>
</form>
</div>