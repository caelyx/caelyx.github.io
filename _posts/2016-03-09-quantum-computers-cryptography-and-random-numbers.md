---
layout: post
title: "Quantum computers, cryptography and random numbers"
category: opinion
tags: [quantum, strategy, encryption]
date: "2016-03-09 07:48:31 +1100"
---

I spoke recently on [a panel at the RSA Conference][panel], titled *Quantum Technologies and Real-World Information Security Challenges*. We talked about quantum computers and their potential to threaten asymmetric cryptography, quantum key distribution (roughly, quantum-secured link encryption), and quantum random number generation. We had a lot of fun, with [Jeff's][jeff] strongly declared facts, and [Jaya's][jaya] pragmatic, immediate approach. 

Here's some of what I had to say on the panel. 

*Your expertise is in the banking system.  How do you think Quantum Computing will affect financial services?*

Quantum computing exacerbates an existing truth – cryptography is fundamentally an exercise in economics. 

If you’re encrypting something or signing something, you are doing so because you want to protect it. From the perspective of an attacker seeking to undo that protection, the more valuable the protected asset, the greater the resources a rational attacker will put in.  Encryption is a particularly powerful control because the asymmetry is so strong: it is many orders of magnitude more difficult to attack encrypted data than it is to encrypt that data.

If both the algorithm and implementation are reliable (itself a non-trivial assumption) then the primary avenue for a sophisticated attacker is the key.  

Therefore, we can magnify the strength of the effective protection around our asset by minimising the value of any given key. This can be achieved by increasing the granularity of keying – rather than using a single master key to protect everything in a data store, use a new key for each data element. As an example, if we can key every file in an S3 data store differently, we radically reduce the value of any given key and thereby maximise the attacker’s cost. We make the economics work for us. 

Quantum computing exacerbates how important this is. Essentially, if quantum computers turn out to be practical in the ways we currently expect, they will radically reduce the cost to attack many classes of keys. Asymmetric systems, like RSA, are particularly vulnerable.  

It’s important to remember, though, that cheap isn’t free. A putative quantum attacker will still have to spend energy attacking each key. High-volume, high-quality random allows us to minimise the value of each key through key diversity, which maximises the attackers’ costs, even in a post-quantum computing world.  

That buys us a lot while we wait for the post-quantum computing cryptography options to stabilise and standardise.


*If we assume that practical quantum computing is probably a decade away, what does this mean for financial services?*

For organisations with long-lived core systems, it’s always the fundamentals that make the most difference.  Defence in depth, minimised privilege, interlocking controls. If you have a sophisticated, layered, control fabric, you minimise the reliance on any one control being effective, even one as powerful as asymmetric encryption. 

I’m reminded of the big cryptanalytic result on SHA-1 a decade ago, which took collision resistance from 2^160 to 2^69. Jon Callas put it well: “walk, but do not run, to the fire exits.” There are still plenty of systems using SHA-1 today; for that matter, there are plenty still using MD5! But good stewards of those systems design and operate them with an understanding of the practical level of security rather than the theoretical level.

As always, we need to be thoughtful in building long-lived systems to ensure that we factor in the likelihood of quantum computing delivering a cryptanalytic breakthrough, and design appropriate compensating controls. Those can include network and endpoint controls, alternative authentication protocols, and increased use of symmetric cryptographic systems that are likely quantum-resistant.


*How do you see the evolution of security systems in your field?*

We’ve talked a bit about quantum key distribution here; while we’re watching that space with interest, we don’t think it’s yet a good capability match for us.

Quantum random number generation (RNG) is an area we’re actively exploring, that we think has great promise. 

The ideal RNG is both high-volume and strong. Strong, in this context, means unpredictable, typically as measured by the relevant NIST test suites.

Current RNG techniques – think `/dev/random` – are reasonably strong, but low-volume. On a normal server in 2016, you can expect maybe a couple of hundred bytes/second of entropy from the software RNG. If you need more random than that, it’s normal for the system to use cryptographic tricks to expand that seed into a bigger set of bytes, but it’s ultimately still the same small amount of entropy underneath; it’s not very strong. Effectively, then, we have a trade-off between high-strength and high-volume random.

There have been plenty of hardware tricks developed over the years to try to harness random physical phenomena and build a larger pool of entropy. Thermal noise is a favourite of many; many embedded platforms recommend using an ADC to sample the voltage of a floating pin and then use that to seed the software RNG. 

Quantum, though, offers a radical step-change in what’s possible. Using a compact optics package, it’s possible to sample quantum phase noise; and we're seeing commercial products that harness that phenomena. The result in one implementation is about 1 gigabit per second of random that passes the NIST test suites. Effectively, that breaks the constraint, and we have both high-volume and high-entropy random. 


*How do security strategies and systems adapt to practical quantum computing if it arrives?*

It sounds boring, but we already have most of the answers we need. Fundamentally, quantum computing threatens asymmetric cryptography; so anywhere where an organisation is really relying on asymmetric crypto, it’s time to re-evaluate the threat model. 

Perhaps the most critical change is in the web domain, where TLS (the little yellow padlock) relies almost entirely on RSA. But even here, there have already been somewhwat-equivalent attacks like CA compromises, and the world didn’t end. At the front-end, more frequent rotation of the TLS keys – perhaps daily – is relatively easy to automate and forces an attacker to go after a new key each time. At the back-end, organisations already make extensive use of out-of-band strong authentication, fraud detection systems, and other controls to provide an integrated, defence in depth approach. 

Interestingly, lots of core systems still mostly rely on symmetric cryptography – AES and 3DES. Since these systems typically didn’t upgrade to quantum-vulnerable algorithms, the amount of rework in the core plumbing is likely to be quite limited. 


*Last words?*

As with all these things, it's important to neither overreact or underreact. We should be thoughtful about including a consideration of quantum computing's possibilities when designing systems today, particularly long-lived ones, as part of an overall risk management framework. At the same time, quantum RNG implementations are now available, and worth considering, particularly for virtualised workloads and sensitive data.


*Disclosure:* my employer is an investor in a company that sells a QRNG ([source][a], [source][b], [source][c]). 

[panel]: https://www.rsaconference.com/events/us16/agenda/sessions/2395/quantum-technologies-and-real-world-information
[jaya]: https://twitter.com/jayabaloo
[jeff]: https://www.rsaconference.com/events/us16/speakers/jeffrey-hunt
[a]: http://www.afr.com/technology/encryption-key-as-westpac-buys-into-aussie-tech-security-firm-quintessencelabs-20150612-ghmnaz
[b]: http://www.quintessencelabs.com/about-us/newsroom/press-releases/6846/
[c]: http://www.westpac.com.au/about-westpac/media/media-releases/2015/16-june-2
