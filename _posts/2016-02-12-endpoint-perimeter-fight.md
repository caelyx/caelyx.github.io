---
layout: post
title: "Endpoint! Perimeter! Fight!"
date: "2016-02-12 18:14:10 +1100"
category: opinion
tags: [strategy, vendors, marketing]
excerpt_separator: <!--more-->
---

[There's an interesting podcast on the A16Z feed][podcast] with Ben Horowitz interviewing Orion Hindawi, the founder of Tanium. In it, Orion spends a lot of time bashing his former company, BigFix, since acquired by IBM<!--more-->[^1]. He then moves on, though, to an extended criticism of perimeter security technologies, particularly FireEye and Palo Alto (which they nearly, but don't quite, name). 

> (12:44) They've all realised that the perimeter is not a protective mechanism. What it is useful for is reducing noise, and it's useful because you can block a lot (you're not going to block everything but you can block a lot), and it's useful for being able to get indications of what you should look for internally. There are these sandboxes and they're really good at telling you, "hey, you're getting attacked in this way"; now you need to figure out where that actually landed and that's the part most people hadn't got before Tanium got there.

> (13:19) Without that, all they're doing is basically sending up a flare and saying: "hey, another trojan horse got in. We don't know what's in there, like, there may be some soldiers, there might be a bomb, whatever, but, like, another one came in. You go figure it out." 

> (13:32) Horowitz: So you're telling me that if I buy a state-of-the art firewall from a great company that may have a South Bay name, since we're not naming-names, all I'm really going to know is something about how people are trying to attack me, but I'm not going to know that they didn't succeed, because I'm not going to be securing necessarily all the ways into my company, and I'm not going to be able to know how far along it is, or any of those kinds of things? 
> Hindawi: If you look at the design of those tools, they're designed to let the first attack through. The first attack comes in and it takes them five or ten minutes to test whether that is actually an attack, so they let it through and it lands on that endpoint then they process for five minutes and if it's a problem they send up a flare. 
> Horowitz: So they don't let the second attack in.
> Hindawi: Or the twentieth attack, if there was nineteen of them that got through in the first five minutes. Essentially, it's to reduce the noise.

By coincidence, a friend reported attending an industry event this week, in which a senior representative of a perimeter security technology company was presenting[^2]. The session started with the traditional genuflection to the terror of the threat landscape and a brief overview of their technology, but much of the session was apparently spent bashing endpoint solutions. The greatest hits --- "you can't possibly get code onto *every* endpoint", "endpoint agents burn too much CPU", and "perimeter controls still work if the client is owned" --- featured heavily. 

This rhetoric, frankly, doesn't build confidence in either company's technology. 

It's not clear what each is trying to achieve by mocking the other.  The notion of a sufficiently powerful single security control has long passed from the dreams of the security community, even a nirvana as desirable as perfect hygiene on the endpoints.  But both seem to be arguing that their control is more important, and should be the primary focus of investment. It inches perilously close to claiming to be the silver bullet. 

Balance and depth are the core of an effective security strategy. That means a strong perimeter and well managed endpoints, and a balance between prevention and detection/response.  Whenever we've forgotten this --- relying on anti-virus to protect internet-connected clients, or investing disproportionately in prevention --- the aggregate result has been chaotic. Remember MIT's assertion that [Kerberos displaces firewalls][mit][^mit]?

Hindawi makes pretty much this point, albeit in the opposite direction, with endpoint information dramatically increasing the utility of a perimeter-generated alert, at about 5:50 and then again at about 20:15.

If a solution provider does not understand that they operate as part of that fabric of useful controls, then we shouldn't expect their tech to play nicely with others. The effective operation of our overall environment is predicated on those products working well together. 

If someone wants to assert that their endpoint control is good replacement for the other controls on the endpoint, then that's a conversation worth having; Tanium might well be the best possible option for that component. 

Asserting, though, that the endpoints don't need the perimeter, or that the perimeter can protect any endpoint, is hubris. 

(*Thanks to Ross and Jordan for their thoughts.*)

[^1]: He really kicks off at 9:00 with a joke about enjoying having to compete with "70-year old grey hairs at IBM".
[^2]: Unnamed because I wasn't there, and this is therefore hearsay.
[^3]: Admittedly, probably apocryphal.
[^mit]: "Some sites attempt to use firewalls to solve their network security problems. Unfortunately, firewalls assume that "the bad guys" are on the outside, which is often a very bad assumption. [...] Firewalls also have a significant disadvantage in that they restrict how your users can use the Internet. [...] Kerberos is a solution to your network security problems. It provides the tools of authentication and strong cryptography over the network to help you secure your information systems across your entire enterprise."

[podcast]: http://a16z.com/2016/01/20/a16z-podcast-the-fundamentals-of-security-and-the-story-of-taniums-growth/
[mit]: http://web.mit.edu/kerberos/www/
