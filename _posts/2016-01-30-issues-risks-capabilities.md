---
layout: post
title:  "Issues, Risks and Capabilities: Cybersecurity Investment Models"
date:   2016-01-30
category: opinion
tags: [strategy, risk, capability]
excerpt_separator: <!--more-->
---

A recent focus of our strategy research has been to consider how security teams are organised and how they build their strategy and roadmap. In that work, we've been asking people how they'd summarise their project investment strategy. What emerged were three primary strategies, arranged along a maturity curve: 

1. Issue driven investment
2. Risk driven investment
3. Capability driven investment

<!--more-->

Most security teams initially started in **issue driven investment**. This is typified by a focus on "audit issues", whether they come from audit teams, risk teams, security teams, or system owner self-report. Typically, there is no central funding for security projects (control enhancement or system hygiene), and issues provide a clear way to argue for funding allocation. In more mature organisations in this mode, each business unit must invest first in resolving issues before investing in other projects. 

While the issue driven mode can be deployed very effectively, it suffers from two key challenges. The first is that it's a fundamentally reactive approach -- opportunities for strategic planning are limited, and the response cycle of the organisation is lengthened by the being attached to the issue management cycle. The second challenge is the inevitable fragmentation of investments: while effective at liberating funds to fix a given system, this generally doesn't translate to fixing identical issues in adjacent systems, much less the entire population. This makes consistency difficult, and limits economies of scale. 


Over the last five years, many security teams have successfully moved beyond issue driven investment by adopting the language of **risk management** in funding and strategy conversations. In this mode, the organisation develops a framework to describe the threats facing the organisation, the current state of the control framework, and thereby a measure of residual risk.  This typically forms the business case for a control enhancement program, centrally allocated, which proposes to close the gap. 

This Risk driven mode has been very effective for most organisations that have adopted it. Large capability enhancement programs are underway in many of the organisations we have talked to, with some variant of this model at their core. 

That said, it certainly has its own limitations. The model remains fundamentally reactive, although with a much shorter [OODA loop][ooda] compared to the issue driven model; investment is aligned to the threats as we understand them today, and significant changes in the threat environment can take some time to flow through the model. Investments that make sense to security teams but don't align with the risk assessment model are typically difficult to implement, even if an architecture or engineering model suggests they are necessary. 


The most advanced teams are moving toward a **capability driven model**. This approach borrows the concept of Strategic Capabilities from the strategy practice in general management ([Lenz][lenz], see also [Prahalad, 1983][prahalad]). This view focuses instead on what the organisation can do today, and what it will need to be able to do in the future to respond effectively to its expected environment; the gap between these becomes the basis for a set of focused investments. Risk remains an important perspective, particularly when used to compare otherwise-similar investment alternatives.

There are three advantages for the organisations able to adopt this approach. 

First, the focus of a capability driven approach is on ability rather than state; on verbs rather than nouns. A firewall itself is not a capability, but only becomes one when wrapped with appropriate processes and people to operate it. This becomes helpful in shaping investment decisions -- since it is often easier to purchase a tool (capital) than acquire the resources to run it (out of opex), and a capability-view can rebalance that influence.

Second, capability driven investment enables proactive strategy in a more comprehensive way. In moving beyond "the risk as we understand it today", we are instead able to engage with "what the organisation need to be able to do to defend itself". This supports consideration of a multiplicity of perspectives: not just risk, but architecture, engineering, and operations. Testing our investment planning from these perspectives allows us to balance out the quirks of any one model, and deliver more thoughtful outcomes.

Third, capability driven investment is more efficient. In providing a longer time horizon, it allows us to build out foundational capabilities first, rather than taking shortcuts to close individual risks out quickly; this can support the business case for efficient, shared services, rather than duplication. 

Most organisations aren't ready to adopt capability driven investment wholesale for information security -- the activation energy is simply too high. The organisation must feel a significant need for information security investment in the first place, which the security team can support but not control. Similarly, the security team itself requires a set of skills in the strategy domain which must be trained or bought; it must also have earnt credibility not just in its domain but also as a responsible strategist in the context of the organisation's challenges. 

Nonetheless, as a target state, it offers some useful concepts that can be used to improve the conversations we have around investment and strategy.


*Updated*: Thanks to Ross, who pointed out that there's a 0th strategy too. In his words: 

<blockquote>
I would propose that there is also a level 0 investment strategy - ie. Delivering security improvement as a subset of other business investment, leading to sporadic and inconsistent deployments and coverage.
</blockquote> 

He's right, in that lots of teams were once in that mode, and many may still be. It's an uncomfortable place, but might be the only option if management's appetite for security investment is low.

[ooda]: https://en.wikipedia.org/wiki/OODA_loop
[lenz]: http://www.jstor.org/stable/257432?seq=1#page_scan_tab_contents
[prahalad]: http://www.readcube.com/articles/10.1002%2Fhrm.3930220304?r3_referer=wol&tracking_action=preview_click&show_checkout=1&purchase_site_license=LICENSE_DENIED
