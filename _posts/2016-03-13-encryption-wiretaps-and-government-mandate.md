---
layout: post
title: "Encryption, Wiretaps and Government Mandate"
date: "2016-03-13 20:43:32 +1100"
---

There's a lot of noise at the moment around the role of tech companies in providing Government with access to encrypted content. The centerpiece dispute is [Apple fighting a court order over a locked device][applevFBI], but there's also apparently a parallel dispute between [WhatsApp (Facebook) and the FBI over a digital "wiretap"][whatsappvFBI].

The two cases are attempts to make case law about two kinds of lawful intercept: access to stored communications (Apple) and communications in transit (WhatsApp). 

One understands the US Government's frustration. Previously useful tools for lawful investigation --- subpoenas on service providers and wiretap orders --- are decreasingly effective. While there have been several attempts to convince Congress to legislate for improved powers, they have declined to do so. This appears to have driven this attempt to use (a novel reading of) the All Writs Act to force Apple to assist. 

At the same time, however, the US Government has made repeated representations as to the misuse of surveillance and intercept by other governments. To pick two examples almost at random, (1) the [State Department criticised China](http://www.state.gov/r/pa/prs/ps/2015/07/244820.htm): 

> We are deeply concerned that the broad scope of the new National Security Law is being used as a legal facade to commit human rights abuses.

and (2) similarly criticised [Russia's use of surveillance and detention laws](http://www.state.gov/j/drl/rls/hrrpt/humanrightsreport/index.htm?year=2014&dlid=236570): 

> There were allegations government officials and others engaged in electronic surveillance without appropriate authorization and entered residences and other premises without warrants.

In both the Apple and WhatsApp cases, the US Government is arguing that backdoors (or equivalent escrow) should be put in place to support their lawful investigation. Unfortunately, equivalent authority is vested in all other national governments. It's simply not possible in law, much less technology, to grant this access to one set of governments but not to the remainder.

The element missing in the US Government's case, therefore, is why these backdoors are so important to US law enforcement that all users of the technology should be exposed to the whim of any relevant government. Certainly, it's largely an economic externality to them, but the rest of us have to live with their decision. 

From the perspective of a cybersecurity defender protecting the content of a call or message, lawful government wiretap, hostile quasi-government attacker and sophisticated criminal all look identical. End-to-end encryption with a well-tested protocol and a strong implementation is the first tool one reaches for. If a government seriously wants to take that away from us, the future is bleaker than it was. 


[applevFBI]: http://www.apple.com/customer-letter/
[whatsappvFBI]: http://www.nytimes.com/2016/03/13/us/politics/whatsapp-encryption-said-to-stymie-wiretap-order.html
