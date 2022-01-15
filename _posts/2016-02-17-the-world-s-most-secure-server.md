---
layout: post
title: "\"The world's most secure server\""
category: opinion
tags: [vendors, marketing]
date: "2016-02-17 08:55:56 +1100"
---

[IBM has a new mainframe out, the z13s][ibm], and the "s" means "security". The security enhancements in the hardware are: 

* Faster cryptographic coprocessors, and IBM now thinks they're fast enough that performance shouldn't be a roadblock for encrypting things; and
* that's it. 

Additionally, if you buy a z13s or the (presumably less secure) z13, the 

> z Systems Cyber Security Analytics service will be available as a no-charge, beta offering for z13 and z13s customers.

Which seems odd. I don't know a lot of mainframe operators that are both high-security and willing to run beta code on their production systems.  That paragraph also points out that you'll need "IBM&reg; Security QRadar&reg; security software"[^reg] to determine if the "events are simply anomalies or potential threats." Why alert me, if it's not even a *potential* threat? 

The rest of the press release argues that you should host your private cloud on their mainframes, before explaining about all the great security software (particularly IAM) that you should totally bundle with your mainframe purchase. 

Steve Morgan on the Forbes Contributor Network, though, has gone all on on hype: [IBM's New Cyberframe Is The World's Most Secure Server For Data Centers, Cloud And Mobile][forbes][^mobile].

> Today IBM Corp. officially announced its z13s mainframe with speedy encryption, cyber analytics, and other security innovations which are baked into the new machine. Call it a cyberframe and watch the CIOs come running.
>
> [...]
>
> “With the z13s, IBM is enabling mid-market clients to encrypt their entire business – from an order placed by a customer on a mobile phone, to the financial transactions processed in their data center,” said Caleb Barlow, vice president, IBM Security.

"Cyberframe." *sigh.*

Unfortunately, this probably heralds the arrival of cyberwashing. (You remember [greenwashing][green], [cloudwashing][cloudw], and friends.) Expect a bunch of otherwise uninteresting products to get one extra feature and "cyber" or "security" added to the headline. It'd be funny, except for the economic waste it will encourage. 


[ibm]: http://www-03.ibm.com/press/us/en/pressrelease/49021.wss
[forbes]: http://www.forbes.com/sites/stevemorgan/2016/02/16/ibms-new-cyberframe-is-the-worlds-most-secure-server/#4304ce3368fa
[green]: https://en.wikipedia.org/wiki/Greenwashing
[cloudw]: http://www.informationweek.com/cloud/infrastructure-as-a-service/5-worst-cloud-washers-of-2011/d/d-id/1101805?
[^reg]: Terrifyingly, the &reg; signs are in the original.
[^mobile]: What's mobile about a mainframe?!
