---
layout: post
title:  "2021: The end of software supply chain confidence"
date:   2022-01-06
category: opinion
tags: [strategy, vulnerabilities, software supply chain]
excerpt_separator: <!--more-->
---

Human brains love heuristics and assumptions. Thinking about everything, all at once, is exhausting (see [Kahneman](https://en.wikipedia.org/wiki/Thinking,_Fast_and_Slow)'s System 1 vs System 2). So we use assumptions to simplify the problem space to something we can manage. 

Cyber is full of humans, and so has plenty of these assumptions too. And a common assumption is that **the security of the software supply chain is good _enough_**. Not great, but okay. Certainly, it's a lesser evil than known vulnerabilities, hence the frequent mantra to turn on automatic updates everywhere you can. 

Unfortunately, 2021 was the year when that assumption really came under pressure --- the software supply chain is under active attack, from a motivated and broadening set of adversaries. So cyber people now need to adjust our approach to defending our organisations. Let's talk about those attacks, and then about some adjustments to defences.

<!--more-->

## Mainstream software supply chain attacks

There have been rumours (e.g., [one](https://www.nytimes.com/2008/05/09/business/worldbusiness/09iht-cisco.4.12745413.html), [two](https://en.wikipedia.org/wiki/NSA_ANT_catalog), [three](https://www.bloomberg.com/news/features/2018-10-04/the-big-hack-how-china-used-a-tiny-chip-to-infiltrate-america-s-top-companies)) for years of supply chain attacks, particularly against hardware. Typically, though, this was nation-state-on-nation-state stuff --- industrial spying, making use of the ability to subvert manufacturers or redirect shipping. 

2021 opened, though, with a massive software supply chain attack. An adversary allegedly compromised the software development systems of SolarWinds, placing malicious code into the source of their Orion product, and pushing it out through their legitimate software update mechanism. As organisations dutifully updated to the latest (compromised) version, the malicious code was installed. From there, the attacker targeted some particular organisations of interest ([Wikipedia](https://en.wikipedia.org/wiki/2020_United_States_federal_government_data_breach)), and executed broad-ranging campaigns of lateral movement to gain access to systems and data of interest ([for example](https://www.justice.gov/opcl/department-justice-statement-intrusion-department-s-microsoft-o365-email-environment)).  The collateral impact was significant --- lots of large organisations use the affected product, and had to rapidly undertake incident response and digital forensics to work out if they were affected, and to clean up and patch.

So, we now had malware distributed through a trusted commercial software product. 


2021 continued with a criminal (as opposed to nation state) attack on Kaseya ([Wikipedia](https://en.wikipedia.org/wiki/Kaseya_VSA_ransomware_attack)). Kaseya provides a cloud service that helps organisations manage their endpoints[^endpoint], including software distribution and patching.  For some subset of Kaseya's customers, the attackers then allegedly used their access to install ransomware into those customers' computers, taking them over and demanding payment to restore access. They also offered a sort of bulk discount: for a much larger amount they would provide a key that would restore access for all the affected organisations.  Ultimately, that bulk key was made available ([BBC](https://www.bbc.com/news/technology-57946117)), although Kaseya has [declined to comment on whether a ransom was paid](https://www.bleepingcomputer.com/news/security/kaseya-obtains-universal-decryptor-for-revil-ransomware-victims/).[^insurers]

[^endpoint]: Endpoints: servers, desktops, laptops, etc.
[^insurers]: For the sake of staying on topic, I'm not going to comment here on the interaction between cyber insurance and ransomware, but it would seem to be a factor.

So, we now had malware distributed through a trusted IT management service. 


Third, there's been an increasing set of attacks on open source components that are commonly incorporated into software. 

* **Malicious commits** -- An attacker [attempted to compromise the PHP language interpreter](https://arstechnica.com/gadgets/2021/03/hackers-backdoor-php-source-code-after-breaching-internal-git-server/), by attacking the PHP core team's software repository. While it was detected and blocked, if successful this could have provided a backdoor into lots of internet-facing systems, once they were updated. 
* **Maintainer account takeover** -- In perhaps the most direct attacks, some attackers are targeting maintainers of common packages directly. If an attacker can gain access to these accounts, they may be able to push malware through the same Continuous Integration/Continuous Distribution (CI/CD) and build mechanisms. A good example of this was [the attack on the `ua-parser-js` library](https://github.com/advisories/GHSA-pjwm-rvh2-c87w) in `npm`, through [an attack on the maintainer](https://github.com/faisalman/ua-parser-js/issues/536#issuecomment-949742904) by compromising his account.
* **Dependency confusion** -- Alex Birsan [published a Medium article](https://medium.com/@alex.birsan/dependency-confusion-4a5d60fec610) showing that they were able to inject arbitrary code into several organisations' proprietary software. The attack relied on registering targeted, public versions of private libraries with higher version numbers. Many modern organisations use CI/CD pipelines to automatically build, test and deploy their applications, and these often pull down new versions of libraries as part of each build --- because the rules about what to download and incorporate were insufficiently specific, they could be tricked into downloading and using a malicious version instead of the intended one. 

So, we now have malware being distributed through open source components -- whether that's at the source, by compromise of the legitimate library, or through dependency confusion. 


Finally, the `log4j` incidents at the end of 2021 were an extraordinary way to wrap the year. `log4j` is a common library for logging (a common task) in Java (a common language). It was also commonly incorporated into other software components and frameworks (e.g. [Struts](https://struts.apache.org/announce-2021#a20211212-2)); one [Google analysis](https://security.googleblog.com/2021/12/understanding-impact-of-apache-log4j.html) found it was included in 4% of the libraries in Maven, at an average of five layers deep.  As a result, it was incorporated in lots of software --- both commercial products and proprietary code. Vendors as big as [VMWare](https://www.vmware.com/security/advisories/VMSA-2021-0028.html), [Cisco](https://tools.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-apache-log4j-qRuKNEbd) and [MobileIron](https://forums.ivanti.com/s/article/Security-Bulletin-CVE-2021-44228-Remote-code-injection-in-Log4j?language=en_US) issued emergency patches or workarounds; the [NCSC-NL started maintaining a list](https://github.com/NCSC-NL/log4shell/blob/main/software/README.md) of all the known vulnerable and not-vulnerable products, as did [US CISA](https://github.com/cisagov/log4j-affected-db/blob/develop/SOFTWARE-LIST.md) and [Royce Williams](https://www.techsolvency.com/story-so-far/cve-2021-44228-log4j-log4shell/). Every cyber and IT team jumped in to find and crash-patch everything they had. 

So, this was a useful demonstration of how much open source there is in commercial software products, even though that's typically opaque to the customer. 


What do we draw from all this? In 2021 we had malware distributed through:

* trusted commercial software products. 
* trusted management services. 
* trusted open source components. 

And we had a sharp reminder about how much we don't know about what's embedded in commercial software.

So, it's no longer credible to assume that the software you're getting from others is safe or trusted. (If it ever was.)


## Now what?

There's a lot of talk about "assumed breach" in the cyber community. Usually, that means assuming that attackers have gained access to some accounts or installed some malware, and being constantly vigilant. 

If you haven't already, it's probably time to move  a step further: to "assumed compromise" in software and software components -- whether commercial or open source. 

As much as that's a big challenge technically, it's an even larger cultural change, particularly among your developers and IT ops people.  Developers are implicitly taught to trust software libraries, and are often under time pressure to ship features as quickly as possible. IT ops people are taught to trust commercial software and services.  Turning this around is going to require concerted effort. Particularly in re-setting the "speed vs safety" trade-off in software development.

Beyond the cultural element, here are three suggestions for what you can do right now to improve your position: 

First -- focus on implementing/strengthening the fundamental controls that reduce the impact of software vulnerability. By "fundamental", I mean those things which are continuously active and are attack-independent (i.e. don't have known-bad lists or "signatures" of any form). Perhaps the best hardening-per-dollar is egress filtering on all your systems particularly internet-facing applications, but work your way back through the rest of your systems too. If a system doesn't *need* to be able to initiate outbound connections, don't let it; and if it does, limit it to only those required. If your SolarWinds Orion instance can't respond to an attacker's request, you had extra time to patch it; if your application using `log4j` can't resolve DNS or reach out to an external LDAP system, you've got extra time to patch it. 

Second -- get clear on what software components you're incorporating in your software, and build automated telemetry that tells you what's used where. That might mean instrumenting your CI/CD pipelines to record what libraries are downloaded and ensuring that the version rules are written defensively. If you're still using manual or local builds, now is the right time to move that to a CI/CD pipeline, to build up that central visibility and control. 

Third -- start moving toward being able to patch everything you have within 24 hours. Yes, everything. Yes, 24 hours. Yes, that's a huge, expensive sentence, perhaps to the point of being impractical for most organisations. But that's where the attackers are driving us. Two things go into that: 

1. Ensure everything you have is actively maintained, and that you can deploy upgrades. Does every application and system have a working deployment process, that can be activated on demand? While that's almost certainly true for your critical and modern systems, it also needs to extend to all the user-developed applications, the apps that the business bought a decade ago without telling IT, and so on. 
2. Wherever possible, automate that deployment, *including regression testing*. The faster, easier, and more reliable it is to upgrade, the more likely you are to be able to confidently upgrade in the face of a vulnerability, rather than having to do risk-reward calculus under stress. Again, now is a great time to migrate everything you can to pipelines.

More generally, use your purchasing power to help improve things for everyone. *Reach out to your vendors and ask them what they're doing.* When will they provide a software bill of materials for the products you use, so that you know what's in them? What are they doing to strengthen the security around their code repositories, and their build and distribution mechanisms? Have they got two-factor authentication in place for all their employee access to those systems? What quality tests are they putting in place to ensure their software isn't subverted? And how are they contributing back to improving the security of the open source components they rely on? 

2021 was the year the software supply chain security assumption was invalidated; the urgent work of 2022 is building resilience against it.

*My thanks to Jordan and James for reading and providing feedback on the draft of this post.*
