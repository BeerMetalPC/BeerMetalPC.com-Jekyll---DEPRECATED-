---
layout: post
title: Here There Are Monsters 
tags: [project, talk]
image:
   path:   /assets/img/projects/HereThereAreMonsters-480-min.png
   srcset:
          1920w:   /assets/img/projects/HereThereAreMonsters-1920-min.png
          960w:    /assets/img/projects/HereThereAreMonsters-960-min.png 
          480w:    /assets/img/projects/HereThereAreMonsters-480-min.png
caption:     A conference talk about lessons learned working on M&A projects, and steps you can take to prepare for one now. 
description: >
   In the year 2021, mergers and acquisitions (M&A) activity worldwide topped an overall annual value of $5.63 trillion US dollars, shattering the previous record set in 2007. Yet despite increases in both the volume and value of M&A activity in our economy, public knowledge sharing by security practitioners about acquisition and divestiture projects, and more importantly their lessons learned, are both scant and difficult to find.
   In this talk, we take a retrospective view of the speaker's experience as the information security "delivery lead" for M&A projects in a large financial institution. We'll summarize their lessons learned, what worked and what can be done better, and impart practical steps you as a security practitioner can take now to be prepared for an M&A activity and/or to support your organization's existing M&A practice. Asking "what if?" now will prevent a lot of last minute scrambling, hair on fire, and "that's not in my budget!"-ing later.
---

* this unordered seed list will be replaced by the toc
{:toc}

## Context

Here There Are Monsters is the first potential conference talk I've worked on. Following Blue Team Con 2021 I was considering whether I've had any experience worthy of a con talk, and my thoughts kept landing on M&A projects. Over the years I've made multiple efforts to search for lessons learned or advice from security practitioners who have done similar work, and sadly I have found nearly nothing. M&A delivery is a side of security that either few have done, or at least few talk about. 

Unfortunately, I have not yet had occaison to give this talk in any formal or public setting. Given the rarity of talks and material covering Security in M&A, sitting on this material waiting to win the CFP lottery feels irresponsible. I am making [my slides](https://www.dropbox.com/s/xyv265znlgrn9pi/Here%20there%20are%20Monsters%2C%20Security%20delivery%20in%20M%26A%20RC4%2020220125.pptx?dl=0) available for the sake of open knowledge sharing, and I've coverted the bulk of this talk into text, below. I started in this role knowing nothing about the M&A process in general, let alone how security fit into it, and I want the next bright eyed analyst that falls over backwards into this type of role to have a better footing to start from than I had. 

### Resources
- [My slides](https://www.dropbox.com/s/xyv265znlgrn9pi/Here%20there%20are%20Monsters%2C%20Security%20delivery%20in%20M%26A%20RC4%2020220125.pptx?dl=0) contain the vast majority of my content in the presentation notes, and you can get most of my lessons learned by reading through the deck in that manner.

### Credit
- Jim N, for embracing chaos and being the best mentor in this role / work I could have ever found. 
- [SlidesCarnival](https://www.slidescarnival.com/moth-free-presentation-template/12025) for the colorful monsters slides template. 

## Security Delivery in M&A Projects 
**Note**: the text version below hits the high notes, I've left jokes and anecdotes out of this version for the sake of being concise and readable, or at least approaching those things. Besides, I need to hold the jokes back so they'll feel new if I ever get to speak at a con. 🙃

### Disclaimers
- Any/all content in this talk does not represent any thoughts/opinions of my employer, nor is it a blueprint of any of their internal processes. 
- I am not a lawyer - this talk is not legal, financial, regulatory, or relationship advice. 
- I am not a thought leader or authority figure, I am not dictating how things must be done. I'm just someone who found themselves working in what seems to be an uncommon niche of securty, and am here to share that experience and lessons learned. 

## What is M&A Delivery? 
Resource(s) from a business or technical group (e.g. security, network, HR, etc.) who would act a) as an input and SME or organization guide for their area throughout the lifecycle of an M&A activity, particularly in pre-activity due diligence, acquisition/divestiture deal readiness, and integration/seperation activity. 

Role entailed juggling multiple stakeholders from the central M&A office, technology, and security, and driving them all towards completion of estimates and tasks. Constant balancing act of doing security right, but also following a risk and materiality based approach. Heavy emphasis in pre-deal activities on materiality and understanding whether factors, anticipated work to integrate/separate, would have an impact to the final quoted cost(s) or contractual verbiage. 

## Three Phases 
Three general phases of an acquisition from our Security perspective. (A central M&A office itself may have additional phases)
- Due diligence - risk assess, what will it take for us to acquire and integrate them?
- Transfer ownership - what do we need to put in place to be reasonably secure the day of the legal handoff?
- Integration - Do the hard stuff, secure what didn’t make the legal day 1 cut, look in all the closets, and find all the scary technical debt. 

## Key Dates
A few key dates, terminology, to understand regarding the milestones of such projects. 
- Day 0
	- Date of deal signing. Not super relevant to security, but does generally allow free-er access to SMEs in the other org. 
-  Legal Day 1 (LD1)
	- Date of ownership and control transfer. As of this day, their problems are officially **your** problems, ready or not. 
- Conversion Day 1 (CD1) or Day 2
	- Date of integration cutover, and/or date when transition services are concluded. You might have a transition of services agreement, especially in deals where a line of business (or multiple) are being carved out of a parent company. (This doesn't seem to be a standard term across all orgs, but it is used in mine)

## Due Diligence 

Obligatory note that your organization may have a different process than what I describe here. Normally we in delivery / SMEs would be engaged once the target is selected and a due diligence sprint begins. This would typically entail a 3-4 week sprint alongside SMEs from other teams. All engaged personnel at this step would be under NDA with a focus on least privilege, need to know personnel only. That said, we did have the freedom to speak to other stakeholders in non-specific terms. E.g. “Hypothetically, what would your area need to do if we added 200 endpoints?” 

**Is it material to the deal?** > The focus here is on materiality and what assumptions, knowns, and unknowns are going to add cost or savings on the deal? Especially if anything needs to be captured in legal or contractual verbiage.

Four key items to capture
- What assumptions are we making? Including: how are we integrating them? (full conversion to our systems? Keep the best of each org? Keep them separate?) 
- Make a best effort to capture specific integration tasks and align them to project phase. (LD1, CD1, etc.)
- Make a best effort to capture specific costs of those tasks.
- Do we need any contractual verbiage? (I personally have not encountered this, but again I am not a lawyer) 

At the end of the sprint the focus would shift from uncovering and documenting information, to packaging it all up, secure approvals (e.g. CISO), and presenting the full package to the M&A office and to the CTO (each SME would speak to their respective area). It's very sobering to go from being the analyst way down at the bottom to being the guy representing info security presenting to the CTO.

### Read everything

Typically, M&A assessment team(s) receive docs, question responses, etc. into a virtual data room. Our standard practice was to read everything in the data room, starting with your own area of responsiblity but expanding outward to consume information triaged for other teams. As we would discover information that may be relevant to other SMEs, we would route that info to them and vice versa. 

Do understand that the completeness of what you receive from the target may vary. Sometimes documents will be very bare bones, but may sometimes be very detailed. Typically for an acquisition I'd expect to see anonymized HR details (compensation), tech stack info, insurance policies, network diagrams (ranging from notional to detailed), board and risk committee minutes, etc. 

You will typically have at least an opportunity to ask questions of the target, do so. If you're going to be doing this type of work regularly, have a list of questions for the target’s IT/IS staff ready to go, generic to any deal. Understand however that just because you can ask, that does not mean you are guaranteed a straight answer. To my understanding, pre-deal, the other party does not have to give you nitty gritty detail. They might, but aren’t required. 
In deals where the target is entertaining multiple suitors, you might just get a canned response or a standardized set of documents or responses across all suitors. (Is that good for the deal? Maybe or maybe not. I am not a lawyer.)

## Adding Value as a Security Practitioner

Maybe you don’t participate in assessing the target. Why should you care about the due diligence phase? Care because we need to be on the lookout for opportunities to add value to the business and our partner functions. Or at least find wins that look good at performance review time. 

First, understand that your M&A function handles insider information, and may themselves own crown jewel assets. (depending on how, what thresholds, you use to define crown jewel) Further, the M&A function may not have considered that they own crown jewels; consider the data room, their sharepoint sites, collaboration tools, etc. If you work for a publicly traded entity, take note. Apply controls accordingly. 

Do you have a red team program? Pentest your data room or 3rd party data room provider. If you remember the [Accelion File Transfer Appliance](https://www.cisa.gov/uscert/ncas/alerts/aa21-055a) breach(es) in March 2021, that’s exactly the type of appliance that could be involved in this activity. 

If you have an insider threat monitoring capability, have a chat with people who would run an M&A activity. Consider creating an enhanced monitoring group for any personnel under NDA for a due diligence activity. Similarly, consider some type of enhanced monitorng when divesting a line of business; consider how you would watch for client poaching or assets walking out the door in this context. 

Lastly, and much more open ended, I believe there's enormous potential here to use OSINT and business intelligence techniques to glean information about e.g. an acquisition target. I unfortunately lack that skill set, but if you have it (or have it in house), give it a try and **PLEASE** give a conference talk about it, I'd love to see it. 

## Legal Day 1 / LD1

What you need for LD1 varies by deal and integration approach. The overall emphasis here is on getting the necessary functions in place to support the acquisition or separation so the purchase/sale can go through. Below are some items to consider, they are NOT an exhaustive list. 

- Security leadership to provide a shortlist of high(est) priority concerns and need-to-knows. Team(s) to verify.
- Find your long tail items and get them involved as soon as possible. 
- Asset inventories and book(s) of record. Check that there’s a plan to get the acquired applications enrolled in the inventory book of record. Other processes likely rely on the inventory to triage and prioritize their own activities. 
- Security Ops is going to want logging and monitoring visibility at bare minimum. Also escalation paths, who responds to what type of incident. 
- You may also want to get permission for security ops or an internal threat hunting or red team to go poke around the acquired environment. Look in the closets. See if they find anything scary. 
- IAM and Vendor assessment probably both want to know about any surge of tickets coming in. 
- IAM also needs to worry about PAM.
- Vuln management to understand their vuln & patch management hygiene, understand low hanging fruit to patch/resolve.

### Empathy

It is critical in an acquisition that you bring a sense of empathy to the table in dealing with your new colleagues. You must understand that the acquired people are experiencing a moment of uncertainty in their professional career. This directly affects their sense of safety and stability, **especially so if any of the communication about their being acquired was unclear.**

I know this sounds basic, but I say this because I have seen it be a problem before. These people are your coworkers now, not your adversary. You might not be able to trust the acquired network, systems, environment; but you do need to show these people that you are here to help, and you have to trust that they want to do the same.

### Use your risk appetite!

**Talk to the business about the deal, where's the value?** What are we securing? You / security leadership need to have a frank conversation with the business or driving force regarding the acquired entity, what their value drivers and crown jewels are. Determine what must be in place to protect the jewels during integration, and what can wait for a later phase? 

Be careful with tooling deployments. IME the more of the initial validation / recon / assessment that can be done with EUC or appliance-ized tools, the better. Agents can be a hard sell, especially if the acquired see it as duplication of an existing capability or a performance hit. Play nice, try not to be too disruptive.

Understand that **Sometimes your assumptions are wrong** and you’ll have to roll with the punches.

## Conversion Day 1 / CD1

**Here there be monsters.** I’m going to skip the fine detail here because this is where all of the unique challenges and weeds are, every one of these is different and you have to find your way through it. 

Think of the worst piece of legacy enterprise shitware you have in your environment. Now consider that almost every organization has one of those too. If you acquire an org, you’ll find it eventually.
			- Legacy OS in prod?
			- Incomplete or nonexistent network segmentation? 
			- Bad vulnerability or patch management practices? 
			
### "This isn't in my budget!"

Maybe you’re sitting here thinking “Hey Frank I don’t care about the phases or risk bits. How do I be prepared? How do I make this repeatable?”
-   **SWAG (Scientific wild ass guess) your potential costs and known issues/concerns**
    -   Product and process owners: at least SWAG your potential costs and known issues/concerns before you find yourself in a "we just bought a company" situation.
    -   Do it because it'll make you look great if/when this happens. Build it out once, update it once a year.
-   **Tabletop**
    -   For an acquisition of 300 employees:
        -   how many new seats/licenses or appliances, capacity, etc. will you need?
        -   Will you need new a new FTE or e.g. a contractor for 6 months to absorb the onboarding or additional workload?
        -   Do you anticipate needing to develop or deploy stuff in their environment until conversion or migration can occur?
            -   Agents and appliances
            -   Firewall, IDS/IPS rules, DLP rules, etc.
            -   Can you do this with their existing solutions and existing personnel?

I know much of this sounds basic, but I had problems getting straight answers to many of these, and I suspect you will too.

## Make it Repeatable

Like any good practice, we had several issues to overcome to make our M&A security function repeatable and sustainable. 

**Cost Estimates.** Most importantely, get good work effort and cost estimates in hand ***now***. Have a “most likely scenario” pre-made for an M&A project. Get a best guess on hourly rate, allocation (bucket of hours or per week), appliances and licensing, any impacts where they would need more headcount, etc. If you have a business management or finance people for your security group, go find them. Buy them a coffee. Ask how they can help. 

**Documentation.** When I started we had a policy document, but didn’t have the procedure, job aides, or knowledge sharing in place for someone else to pick the role up if we got hit by a bus. Remember, if it isn’t documented, it isn’t repeatable. Document your processes. Once you've done that, get the advice you would give orally out of your head and onto something sharable, even if it's only a text file. One such challenge we faced was that our documentation and reporting templates were suitable for an M&A audience, but didn't quickly convey the information important to our security leadership. Always keep your executives happy. 

**Organizational debt.** Specifically, during the time I was in the role, certain conceptions about the function were held by management that we had to gradually overcome. In a slow period, maybe a quarter, maybe a year, specialist personnel like M&A security delivery would be tapped for other projects. This is fine, but it took several hard lessons learned for that management structure to learn that a M&A project or a due diligence sprint was a "drop everything" event. This prompted a saying with one of our directors: "M&A is cold until it isn’t." Once the fire is lit underneath, M&A is going to be off and running right now and running hot, and it can happen with very little heads up warning.  

Additionally, Don’t bury your strategic projects personnel in the org chart. If you have people handling high criticality, strategic, super duper important (whatever terms you like) projects, you need to have some amount of trust in them. This is doubly importnt if you work in a shop that has a chain of command culture. Establish norms with these personnel, but also establish the trust and authority with them such that they can go straight to the CISO when necessary. 

### What's in your security stack? How would you know?

This is the storytime part of the talk. We bought a company, and it quickly became clear we needed to keep most of their existing environment because of the special sauce we bought them for. I had to identify what parts of our security stack needed to be deployed into their environment, and when. 

There was no central place where I could find a listing of tools, critical, necessary, or otherwise. Nothing. Security business management were in the midst of a similar effort. They had a list of tools, but hadn’t mapped any of them to functions and owners. IT finance only had the contract view, and no understanding of contracts included what tools for what service/function. We did what anyone out of options with only half the puzzle would do. We built a spreadsheet of doom. It was messy, it was manual, it was out of date the moment we started using it. But it was good enough to get all of the major players and their tooling captured and start forecasting costs. 

The point is, figure this out if for no other reason so you understand what you as a security program are paying for. And then, if a strategic project comes along like an acquisition, this is on hand to map capabilities and needs in tabletops, scenario planning, due diligence, etc.

### Don't Panic

-   Create loose process, reporting templates, and your approval workflow now.
-   Create that most likely tabletop scenario. 
    -   What will my area of responsibility need to do?
    -   What assumptions are we making? (especially on incomplete or missing info)
    -   How much will it cost? (+/- 50%)
    -   How long will it take? (+/- 50%)
    -   What remaining concerns, unknowns, or known issues may require contractual verbiage, or may impact the deal?

Like it says in Hitchhiker’s Guide to the Galaxy, don’t panic. At the end of the day this is just a project with some unique wrinkles and structure. Button up your documentation: process and templates especially so that someone who stumbles into the role in 3, 5 years can pick it up and run. I just ask that you think about these scenarios now so that you don’t later have to build the railroad while the train is in motion.
