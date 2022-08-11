layout: post
title: I Ran a Community | Lessons Learned at Ferrous Core Pt.2
tags: [Gaming, Ferrous Core]
caption: A summary of what worked well at CORE, as advice for gaming community owners/operators. 
description: >
  A retrospective about the gaming community I ran for four years. This part focuses on what went well, lessons learned to be taken as advice by others running such communities.
date: 10 August 2022
image: 
  path: /assets/img/projects/solcore-1920-min.png
  srcset: 
    1920w: /assets/img/blog/solcore-1920-min.png
    960w:  /assets/img/blog/solcore-960-min.png
    480w:  /assets/img/blog/solcore-480-min.png
sitemap: false

---

* this unordered seed list will be replaced by the toc
{:toc}

Hi again all. Following up from [Part 1](/blog/2022-06-04-Ferrous-Core-Pt1/), I found that my first version of this post was quickly spinning out into extraneous detail and repetition. Throw in more prep for the CRISC exam and typical summertime schedule shenanigans, and you get a much longer time editing this post than I like. 

For those jumping in new here, this is Part 2 of a retrospective on the intentions behind and lessons learned from building an online gaming community, Ferrous Core. I managed CORE from 2017 into early 2021, at it's peak it topped >1000 registered users. I hope that this can help inform those stewards of that community into the future, and provide lessons useful to other running or seeking to run online communities. 

## First Impressions Matter a Lot

About a year and a half in, we stood up a website just to be a semi-professional looking front end for our community. We ran Wordpress on a small AWS EC2 instance, paid ~$50 for a good looking theme, and threw a basic search engine optimization plugin on. This ran us about $10/month plus annual domain name renewal fees, amounts easily paid for by passing a metaphorical hat around in most communities. 

In this space, a truly *tiny* bit of professional veneer and SEO goes a huge way. Most gaming clans, guilds, etc. don't spend the time, know-how, or cash on these, often opting for nothing at all without realizing that it is seen as a differentiator by many. The group of friends I've since moved on to other games with came to CORE in large part because one of them saw said site and thought "oh these guys look legit." 

Do something, anything, to have a web presence beyond just your various forums or Reddit recruiting posts. It can be as little as an lnk.bio or campsite.bio page, or a Discord.me gateway, or an off the shelf free gaming site like Enjin or Shivtr if you must. (Be cautioned that canned gaming-forum services look samey-same-same very easily and can be seen as a negative) 

## Don't Bullshit your Audience

In order to grow we made use of existing "find a..." communities and tooling. Reddit in particular was a prime source of our initial growth via the r/Fireteams weekly clan recruitment thread and the r/DestinyTheGame "Team Up Tuesday" thread. In our early days we were up front about being a new community, and as we scaled in size we clearly stated an estimate of our monthly active members, average age, our guiding principles, and that the line members generally favoring cooperative content. 

Once we hit around the ~100 players mark, we ramped via word of mouth with only occasional recruiting posts. People felt like we were running a good place and in turn brought in their friends and acquaintances. While welcome, I have no tips to share in that regard other than to run a good environment, and have a bit of luck. 

In a general sense, go where the interest and eyeballs are to advertise. And when doing so, don't pretend to be something you're not. Next time you're looking through a Reddit or Discord find-a-community type of board, take a quick tally of the number of posts that don't pass your smell test, don't make their mistake. Be open and honest about what environment you provide and where you anticipate it going. 

## Minimize Hierarchy

For most of CORE's existence we have had only four hierarchal roles, which were distinguished from each other by the color of the user's name in text chat, which aligned to the drop/gear rarity color scale in Destiny and most RPG-esque games. Respectively: Green --> Blue --> Purple --> Yellow. 
- Greens are newcomers pending a number of endorsements for "full membership."" 
- Blues are voted in full members, and this was expressly communicated as the role that the vast majority of our community would obtain. 
- Purples are "Proven", blues who had distinguished themselves in their actions, knowledge, and attitude. More on that later. 
- Finally, Yellows are the administrators. (Early on we had Yellow - Orange - Red but realized it to be unnecessary, and combined into Yellow)

We went into setting up CORE with the intent to minimize the ranks, roles, and hierarchy as I had seen complex and highly regimented structure play out badly previously. Heavily chain-of-command oriented communities fall into this trap often; by creating a highly segmented hierarchy, you incentivize behaviors where the general membership will chase rank and standing in the community because they see the next rank as something to be achieved or collected. Many members in these communities will pursue said rank even if the behavior they engage in in doing so is detrimental to said community, likely because they see imaginary internet points to be obtained, or feel a sense of need or obligation to "keep up" with their peers. At it's worst, this can feed negative behaviors where members of the community flex their rank over those below them in the hierarchy, disincentivizing newcomers from playing with or interacting with those higher in the hierarchy, driving many away entirely. 

I stated many times that complex rank or standing in a gaming community was just another flavor of **imaginary internet points**, and ascribing value to imaginary internet points deserves ridicule. 

To this end we explicitly stated in our FAQs and documentation that asking "How do I become *rankname*?" was a sure way to demonstrate not understanding the traits and character that our community valued. We also made it a point to never use these ranks as a punitive tool. People participate in CORE of their own volition on their time; to take something away like a rank or role earned as recognition would both be counter to our principles and following in the footsteps of some of the more toxic, megalomaniac moderators I'd witnessed before. 

## Vote In, But With Low Friction

One system that I had seen work well before was to have some form of probationary period for new members, and to grant membership in the community once the user passed some threshold of affirmative votes. In the context of a past community: they were based around a vBulletin forum as their primary communication platform. They performed this function by creating a sub-forum under the Apply For Membership board which was only visible to full members. A vote thread was created for each applicant, with the norm in effect that any "No" votes would be accompanied by a post in the thread with the rationale why. Likewise, any issues or red flags could also be brought up either in thread or by direct message with an officer/admin. It was a fair bit of administrative overhead, and may have disincentivized good people from joining who were unwilling to jump through the hoop. 

I had also experienced "open" gaming communities, where one could just come in and put the `[xyz]` tag in front of their name, to represent that community, without any say or input from the extant membership. While I appreciated their willingness to welcome newcomers in if on little more than if they felt at home, the most prominent of said communities had issues with both bad fits coming in with no control of flow, and with the extant membership of a certain mindset using the founding document of the community as a cudgel with which to No True Scotsman their peers. 

I wanted the best of both: to establish a low-barrier(s)-to-entry, low-friction intake for newcomers to CORE, *and* for the members to have a say in whether newcomers were a good fit with the community and our guiding principles. 

To achieve this, we created a Discord text channel called Aux-Reviews that was visible only to our voted in members, our "Regulars" and above. Similar to the former community in these examples, extant members who played with a newcomer would post a couple sentences in this channel, essentially stating that they played with the newcomer and thought they were good / not good with a brief explanation. Once the newcomer passed a threshold of affirmative votes, they were in as a Regular. If they had negative reviews, they would essentially be paused in the newcomer state until/unless we saw an improvement, or continued negative behavior warranting a "this isn't going to work" dismissal. 

### Automate Whatever You Can

Initially, this tracking of votes was all manual, spreadsheet based, and unsustainable. Eventually, one of our admins wrote a chatbot and a very lightweight database to handle this voting function. With the bot in place, this system has worked reliably for going on four years now. In a general sense I would point to this as a good lesson from the business / technology world: automate as much of the busy background work in running such a place as possible, if for no other reason than so that the thing you do for fun does not become a chore. 

I'd recommend a similar approach, both in voting and letting a chatbot do the tracking, for anyone running a similar community. But do understand that this worked because the voting was done in the same social hub / tool as the rest of our interactions and that a custom bot was needed. (An off-the-shelf bot may exist, but I do not know of one) 

## Contextual Responsibility

Akin to minimizing rank and structure, we also did not want to gate play sessions, event hosting, raids, and the like to "you must be this tall to ride" ranks or measures. Instead of a highly regimented, structured hierarchy, I felt the members and participants in the community should have the agency to take initiative, schedule events, do things with no or minimal approval. I'll call this *"contextual responsibility"*,  although I'm sure there's a proper term for it that I have yet to encounter. 

For the sake of example: let's say you want to raid this week. You've got a real hankering to run Last Wish, probably because it's been three years and I still haven't gotten [One Thousand Voices](https://www.destinypedia.com/One_Thousand_Voices) to drop from the last chest ask me how I know I'm not bitter at all 😑 
... Ahem... So you set up a raid on our The100.io group, enough of your fellow CORE members sign up over the next couple days to round out a team, plus an extra / backup. Let's say you're pressed for time: you want to do all the bosses, but you can't commit to much more than that.

When the time of the event comes, it's your event. You set it up, you get to define how it will run. You get to set the tone and pace. 
- Worried about time? You want a quick and dirty lets get it done run, it's your event, so you just say so. No wish wall. No bonus chests. Skip wall to Vault. It's your decision. 
- It's time to start and one of the sign ups isn't present? You make the call to wait for that person, or to bring that backup player in. 
- You're not super familiar with a couple of the encounters, but D-Buddy is here and you know they can make all the callouts on two hours of sleep and blindfolded while also topping the board for damage. You can defer to them, it's your decision. 
That's it. No intricate web of conditions or hierarchy to memorize. You set up the event, it's **your** event; you set the expectations, the tone, the pace. 

We extended this not just to in game activity, but to creation of things like graphics and how-to guides, use of CORE logos and art in our content creators' streams and videos, party game nights e.g. Cards Against Humanity, specific content coaching such as replay reviews, 1v1 and 3v3 PvP tournaments, etc. Instead of asking for the thing, start doing the thing and ask others to help; we the admin team would support it with announcements, Discord channels, event nights, whatever was within our power. 

Set the norms and expectations clearly for what you'd like to see people in your organization. Give them the flexibility and comfort that they can go forth and do things within a defined risk tolerance, and to do so without having to run up layers of hierarchy. Correct the errors and amend guidance as issues occur, if you want people to be creative self-starters, you need to let them do so without you knowing all the details in advance.

## Transparency as a Differentiator

One of the gripes I have had with organizations in virtual and meatspace settings both is a lack of visibility into or explanation of their administrative decision making, particularly when paired with problematic and inadequate choices and communication thereof. When such events occur paired with this failing, it feeds a lack of trust in turn opening doors to fear, uncertainty, and doubt as to the intentions and capability of those in decision making roles. 
From the start, I wanted to ensure our members had consistent insight into how CORE addressed administrative or moderation decisions, even if we couldn't get it nitty-gritty detail we could at least explain *how* something came to pass. Additionally, I thought it best to provide self-serve tools for the members of the community to validate (at least in part) what was being communicated by the admin team. 

If we could not truly provide total transparency, then we could at least provide something akin to it. Translucency, perhaps? 

### Tone From the Top

We emphasized that everyone with additional permissions, Admins, Moderators, and the like were in a **service position**, and not one of superior rank or stature. I tried very hard to impress upon all involved that an @Admins ping always deserved a serious and reasoned response, no matter how frivolous or eye-roll inducing the ask may seem. This does not mean dropping everything to deal with an @Admins, we have lives and obligations outside of this place we derive fun from in our spare time; merely taking administrative acts with our "Admin Hat On" seriously and solemnly. 

For general awareness, we set a cadence of monthly, "community update" postings in our Announcements channel. These were a long form post to provide updates on both occurrences of the past month, administrative asks or topics on our minds that needed more fleshing out and feedback, and general upkeep such as Auxiliaries becoming Regulars / full members. While seemingly minor, and outsized in the time I had to invest writing relative to playing the game itself, these provided a feeling of connection and involvement to the general membership. It served as a consistent window into what was on the collective minds of the admin team, and standing prompt for feedback and suggestions. 

When disciplinary issues arose, the expectation for admins and moderators was to communicate what's occurred and the expectations, and let the recipient demonstrate if they've heard or not. "Do this or else" statements are internet tough guy nonsense which wastes everyone's time. When issues resulted in someone being kicked out, I insisted that an explanation *always* be provided to the general membership. This was done consistently no matter the standing of the individual, whether it be a long time member, or a spambot. Additionally, I made it clear that we would bring receipts: chat logs, server logs, evidence, albeit sanitized of any personal or sensitive details and disclaimed as such. We did this especially for any circumstances with lots of back and forth and heated exchanges, and especially where these occurred outside of public view. 

### Let People Look Under the Hood

Discord provides an "audit log" pane in the server settings view that allows a user to view moderation actions on the part of both users and bots. Further, general-purpose administration bots, in our case [Dyno](https://dyno.gg/) and later [Ser Aymeric](https://seraymeric.com/), provide the ability to log more common user actions such as voice channel and server join and leave events, message deletions and edits, etc. to a text channel, which we set to read-only. The "Admin Discussion" channel was however exempted from the bot audit log, and clearly stated as such, in order to prevent leaking of admin discussions where user privacy was a concern.

We implemented a self-serve, opt-in role called "Auditors" that any user could toggle on/off at any time which granted access to both the Discord Audit Log and "Bot Audit Log" channel. To say this is worth doing is an understatement. These settings were painless to set up, and both supported investigation following an issue and backed many moderation actions after the fact with a clear, average-user-verifiable chain of events. That latter point I feel was a key reason why we never had any significant issues with misinformation or FUD around admin team actions.

### Involve the Membership in Decisions

Originally, I had intended for the Proven (purple) role to not just be distinguished members, but to also have access to the Admin Discussion channel. This was ultimately unsustainable, the community's growth resulted in several more Proven than originally envisioned and a growing tendency towards admin discussions beating dead horses. This feature was dropped relatively quickly in our first year.
About a year and a half later we revisited the idea and created a function called the "Orators." Every month we selected two members at random; one from an opt-in "Candidates" role, and another from the full list of Regulars and Proven; that is all full, voted-in members of the community. 

Orators were always given clear expectations up front. They could be as (un)involved as their time or interest allowed for. They were always posed the option to decline, no question asked, and allow for a re-draw for who would fill that seat. Once agreed, they would be publicly announced in the community update announcement at the start of the month, and have access to participate in the admin discussion channel for ~30 days. 

This approach only works if you treat this role, such as our Orators, such that they belong in the conversation. Don't just "value their input", act upon it. We made it clear to all Orators that their voices had the same standing and clout as a yellow-name administrator. Any topics they wanted to table for discussion, any issues, any suggestions or "why is that?" questions, were valid and deserving of our time and effort. 

## Part 3 Preview: What can be done better

- No in game organization structure is leagues better than a badly implemented one. Game developers take heed. 
- We tried to be a big tent appealing to both the "casual" and "hardcore" players. There needs to be a differentiation, but our attempt created an "us and them" split and caused more issues than it solved.
- Cut toxic personalities from the group as early as possible. No amount of redeeming qualities is worth the issues they create. No amount of fairness can undo the damage caused by allowing shitty opinions voiced by bad faith actors to persist. 
- Don't let the thing you do for fun become a chore. 

> Image credit to Ferrous Core member advent_g0d
