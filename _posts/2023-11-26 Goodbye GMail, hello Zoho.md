---
layout: post
title: Goodbye GMail, hello Zoho
tags:
  - project
caption: Lessons from upgrading my personal email to business class
description: In October 2021 I jumped from freebie GMail to business-class email provider Zoho. This is guidance on how you can get started and what resources may help.
date: 26 November 2023
image:
  path: /assets/img/projects/ZohoConsole1-1920-min.png
  srcset:
    1920w: /assets/img/projects/ZohoConsole1-1920-min.png
    960w: assets/img/projects/ZohoConsole1-960-min.png
    480w: /assets/img/projects/ZohoConsole1-480-min.png
sitemap: false
---

* this unordered seed list will be replaced by the toc
{:toc}

In October 2021 I jumped from freebie GMail to business-class email provider Zoho. We have been living in the age of cloud computing and "free" services (in exchange for harvesting your data) for some time now. Paying for so basic a tool as personal email no longer sits well with most consumers, but I've since seen tangible benefits from moving from Gmail to a paid service. 

In this post, I'll talk through this decision, lessons learned, and provide resources that were helpful in making the switch. 

## Why Move? 

I was becoming increasingly frustrated with the spam and phishing messages I received in my GMail inbox. I felt that Google wasn't providing enough control or insight into how these messages could be filtered and prevented. 

The increase in unwanted and probable malicious mail to this address was inevitable. The account in question had been created in my teens and was used for the full range of purposes in my life without any purpose-defined aliases or filtering. As of the time of this post, the GMail address in question has been in 15 known data breaches per [HaveIBeenPwned.com](https://haveibeenpwned.com/). Two of these breaches pose an increased phishing risk as they involve accounts capable of financial transactions. These attempts ran the full spectrum: from fake invoices, to [Google Forms notifications](https://blog.talosintelligence.com/google-forms-quiz-spam/), unwanted [calendar invites](https://www.androidpolice.com/google-calendar-spam-protection-default/) that automatically sync with Google Calendar, and even mass spam with subject and body text in a Cyrillic alphabet language with a PDF attachment which you would *think* Google would be great at catching by now. 🙄

I came to feel that given Google's inconsistency in preventing delivery of obvious phishing attempts to this inbox, and the volume of such attempts, an accidental click or open action on an attachment had become a matter of when rather than if. I can no longer trust this GMail account for human interactions or conversations and have now relegated it to information-only use.

## Candidate Services

I initially considered an encrypted email provider a la [Tuta](https://tuta.com/) or [ProtonMail](https://proton.me/mail). These were ruled out as nobody else in my contacts list was on these email providers, rendering their automatic same-service end-to-end encryption not relevant. I do recommend you do your own due diligence. These are impressive services, albeit relatively expensive. I merely determined that I have other solutions available for E2EE communication e.g. Keybase and Signal, and can fall back on manually applied email PGP if necessary. 

I also evaluated Google Workspaces/GSuite but was unconvinced that the security and administrative controls provided by the paid-tier features would be sufficient to address my concerns.

Meanwhile, my father, a self-taught computerist with no background in enterprise IT, was mid-adventure to reduce his usage of Google services. He had settled on Zoho's mail lite plan for his own email. He claimed the water was warm, and at $1/month I figured it was worth dipping a toe in. 

## Resources

Two caveats before we continue. 

First, instead of providing a step-by-step guide that may not be comprehensive and could quickly become outdated, I will share the links to Zoho's documentation for important features in the order I believe you will require them. 

Second: the admin console for Zoho is featured as if for an enterprise organization, so some features are overkill or unnecessary for the personal email use case. Proceed accordingly. 

### Setup

**Most Important:** Zoho's own instructions for [Email Hosting Setup in Zoho.](https://www.zoho.com/mail/help/adminconsole/email-hosting-setup.html) 

[**Pricing**](https://www.zoho.com/mail/zohomail-pricing.html): So far the Mail Lite plan at 5GB per user has been more than enough for my needs. 

**[MX (DNS) records configuration](https://www.zoho.com/mail/help/adminconsole/configure-email-delivery.html)**: Most of the work here will be in your registrar's admin panel. 
- Also set up [**SPF**](https://www.zoho.com/mail/help/adminconsole/spf-configuration.html), **[DKIM](https://www.zoho.com/mail/help/adminconsole/dkim-configuration.html)**, and **[DMARC](https://www.zoho.com/mail/help/adminconsole/dmarc-policy.html)** records while you're at it. 
- **Other [Domain Settings**](https://www.zoho.com/mail/help/adminconsole/domain-settings.html): most of these probably won't be relevant to you, but do set [Catch-all and Notification addresses](https://www.zoho.com/mail/help/adminconsole/catch-all-setup.html#alink2). 

If you plan to use Zoho mail accounts in 3rd-party apps via [IMAP](https://www.zoho.com/mail/help/imap-access.html) or POP, you will need to create **[Application-Specific Passwords](https://www.zoho.com/mail/help/adminconsole/two-factor-authentication.html#alink7)**. 
### Spam Controls

Due to my relative inexperience with the plumbing of email, I've set most of the [Spam Verification](https://mailadmin.zoho.com/cpanel/home.do#securityAndCompliance/spamControl/verification) options in the admin console to quarantine mail that fails these checks. I started out with these settings so that I could see what was coming in, with the intent to move to the permanent reject option later. 

That said, DNSBL check failures I set to permanently reject; if the sending domain/email or IP address appears in Zoho's [DNSBL](https://en.wikipedia.org/wiki/Domain_Name_System_blocklist) block list, that mail is rejected outright. There does not, however, appear to be a way to define your own or additional DNSBLs (E.g. [Spamhaus](https://www.spamhaus.org/)' Zen). Your only option is to trust Zoho in this regard, but if like me you're coming over from a consumer email product you wouldn't have had any insight or control into this function anyway. 🤷

You are also able to define explicit allows and blocks, pattern blocking, recipient-based blocking, and, most interesting to me: language-based, country-based, and whole TLD blocks. 

How the [internationalized spam ](https://www.zoho.com/mail/help/adminconsole/spam-control-lists.html#alink2) language and country-based blocking are implemented is left opaque in Zoho's documentation. But, as an ignorant American challenged by any tongue but my native English, I do have several languages blocked based solely on past experience with received spam and phishing. 

As for [TLD blocking](https://www.zoho.com/mail/help/adminconsole/spam-control-lists.html#alink8), I periodically check the top-abused TLDs (ref: [Spamhaus](https://www.spamhaus.org/statistics/tlds/) & [SURBL](https://surbl.org/tld)) for both professional interest, and for blocking in Zoho and my home network firewall. I recommend blocking any you see as concerning or have no current reason to be interacting with. You can always unblock later if necessary. I can't attest whether a proper mail admin would consider this best practice or not, but it feels like the right thing to do. 

The [Malware Processing](https://mailadmin.zoho.com/cpanel/home.do#securityAndCompliance/antiPhishing/settings) section is also worth a look if you want to restrict email based on content or HTML tags. Any emails containing the listed content or tags are placed in the Spam folder. This could also break various mass and marketing emails, but it's not like we need any *more* of those. 

After completing your work, it's a good idea to review the [Security and Compliance Dashboard](https://mailadmin.zoho.com/cpanel/home.do#securityAndCompliance/dashboard) to ensure that you haven't overlooked any major issues

## Misc. Observations

### The Bad 

**Syncing contacts sucks.** It has been, and remains, a bad user experience to sync contacts across multiple walled gardens. Zoho *can* export [via CardDAV](https://www.zoho.com/mail/help/CardDAV.html), but in my experience this may introduce more problems for you than it solves if you already treat e.g. Apple or Google Contacts as your contact book of record.

### The Good

**The price.** Thus far the Mail Lite plan at $1/user/month for 5GB on a single user has been more than enough for my needs, and upgrading to 10GB storage is quoted at $1.25/user/month. That said, some features e.g. S/MIME do require you to step up to the next tier at $4/user/month. As always, do your own due diligence on the product and services you may need. 

**Plenty of domains and aliases.** At the time of this writing, I have associated three domains to this account and a boatload of aliases across them for various downstream accounts and filtering. All with relative ease through the admin console, and without the need to step up to a higher features tier. Do keep a note somewhere of all aliases you've configured and if/how/where they are filtered, it makes upkeep significantly easier. 

**Zoho Mail contains no advertising.** In the ~13 years I used GMail, I, like all GMail users, have assumed the role of the slowly boiled frog. The steady creep of advertising into the platform until advertisements disguised as emails arrived took me by more surprise than it should have. It is refreshing to experience an email client free from advertising and distractions-not-of-my-own-making, even if I must pay for the privilege. 

And to a lesser extent, a near-total reduction in phishing and spam directed to my primary email address. However, I won't represent this as a success due to the platform just yet, as this domain has yet to appear in significant, public data breaches as my GMail had. 

### The Meh

**Configuration.** You need to put some work in yourself in setting DNS records, SPF, DKIM, DMARC, etc., defining various settings, troubleshooting any issues, on top of managing your email a la filtering rules, tags, folders, etc. But, the good news is Zoho's documentation is generally good in my experience, and all can be done in GUI-land. 

**Configuring third-party clients** e.g. Apple Mail or Thunderbird still isn't quick per se. I recommend closely following Zoho's own instructions for [Apple Mail ](https://www.zoho.com/mail/help/apple-mac-imap.html) or [Thunderbird](https://www.zoho.com/mail/help/thunderbird-imap-access.html) and referencing their instructions for [Enabling IMAP Access](https://www.zoho.com/mail/help/imap-access.html#EnableIMAP) which also contains the relevant server addresses, ports, and other settings.  


---

Overall, Zoho Mail is worth consideration for those in need of a reliable and affordable email client. I hope that this serves as an effective entry, and jumping-off point for your own move away from consumer-grade, advertising-laden options. 










