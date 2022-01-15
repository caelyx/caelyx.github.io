---
layout: post
title: White House Meeting on Software Security
date: "2022-01-15 18:54:23 +1100"
category: link
tags: [vulnerabilities, software supply chain, tools]
external-link: https://www.whitehouse.gov/briefing-room/statements-releases/2022/01/13/readout-of-white-house-meeting-on-software-security/
---

Following on from the [`log4j` vulnerabilities]({% post_url 2021-12-19-links %}) of late last year, the White House held a meeting on software security with government, private sector and *open source* representatives. ([I was wrong](https://twitter.com/caelyxsec/status/1481797611518857217): they invited the Apache Software Foundation). 

The [readout provided by the White House](https://www.whitehouse.gov/briefing-room/statements-releases/2022/01/13/readout-of-white-house-meeting-on-software-security/) sounds like the conversation was directionally positive, and developed a useful framework for how to proceed: 

> The discussion focused on three topics: Preventing security defects and vulnerabilities in code and open source packages, improving the process for finding defects and fixing them, and shortening the response time for distributing and implementing fixes. 
>
> In the first category, participants discussed ideas to make it easier for developers to write secure code by integrating security features into development tools and securing the infrastructure used to build, warehouse and distribute code, like using techniques such as code signing and stronger digital identities. 
>
> In the second category, participants discussed how to prioritize the most important open source projects and put in place sustainable mechanisms to maintain them. 
>
> In the final category, participants discussed ways to accelerate and improve the use of Software Bills of Material, as required in the President’s Executive Order, to make it easier to know what is in the software we purchase and use. 

The participants from ApacheSF published their [Position Paper](https://cwiki.apache.org/confluence/display/COMDEV/Position+Paper) in the lead in to the conversation, which is interesting reading. The paper is cogent and worth reading. 

That said, it seems determined to perpetuate a "buyer beware" approach to software, which is isn't great. It's entirely understandable that an open source organisation like ASF can't exactly offer a warranty for their software, but that same belief bleeds into commercial software and is one of the root causes of our global cyber problems.

The other theme that comes through the paper is a frustration with how few *users* of open source software then also become *contributors* to open source (particularly large companies which rely on those components to generate revenue). This is a theme that seems to be burning quietly underground in a few parts of the community, occasionally appearing as spot fires, like [the deliberate corruption of two `npm` libraries](https://www.bleepingcomputer.com/news/security/dev-corrupts-npm-libs-colors-and-faker-breaking-thousands-of-apps/) as a protest over a lack of funding. Here's hoping that we're on an inflection point around making open source more sustainable, this isn't a sign that the great open source experiment isn't on the precipice of a slow collapse. 
