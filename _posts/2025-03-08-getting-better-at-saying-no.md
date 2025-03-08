---
layout: post
title: Getting better at saying "no"
date: 2025-03-08 16:15 +1100
category: opinion
tags: [productivity, generative-ai, tools]
---

I really like to help people - it feels good, and it generates value.  Fortunately, work is full of lots of opportunities to help people.  Unfortunately, I also tend to be wildly optimistic about how much capacity I actually have - underestimating how long it will take to help with something, and underestimating my existing commitments. The intersection of those various things means that I sometimes get wildly overcommitted - and have to work silly hours to dig my way back out of those commitments. That works _okay, I guess_... but I'm not in my 20s any more (or my 30s), and I'd prefer to reduce how often this happens.

Improving things has meant:

* Moving to a single view of all of my existing commitments, so that I can see at a glance how much is already on my plate.
* Sharpening my decision algorithm from "Could I help with this?" to "Am I the _best person_ to help with this?" (and "best person" doesn't mean "most experienced" -- routing work to people who want to grow in that area is a gift to them).
* Changing my capacity attribute from "Will I have time?" to "Will I have both time and _energy_?".

All of those are habit changes, so it's a bit of an iterative change process - but those habits are starting to shift. As a result, that decision process is increasingly telling me I should say "no" to more requests.

At the same time, I have a lot of anxiety about disappointing people or saying the wrong thing. Saying "no" feels like it is going to be disappointing. And coming up with the right thing to say can be a bit agonising - it's not unusual for me to spend five minutes rewriting a "Sorry, this isn't something I can help with right now" email. All that means that I sometimes end up saying "yes" when I don't want to, because saying "no" burns up too much energy. 

A colleague brought this up at a dinner the other night and had come up with a great tactic: "We just have a list of standard ways to say "no" to meeting requests - and we pick one at random each time!" Simple, brilliant. Even if you don't use the templated phrase exactly, you're not starting with a blank page, so it's much easier to get it done. I wanted that list too. 

In parallel, I've been experimenting with using LLM chatbots for more things at home to get a sense of where they can be helpful. Anthropic's [Claude](https://claude.ai) Sonnet 3.7 is currently my default for anything complex that requires an online model. Asking Claude: 

> Come up with a phrase book for how to gently say “no” in various contexts at work. (Context: I’m a professional manager with [n] direct reports and about [n] people overall, and I’m in [country].) Include at least 40 phrases overall, all professional, and include a mix of “no”, “not now”, delegation and other scenarios.

emitted a surprisingly useful list of 50 phrases in about five categories. That inspired some other categories, so a few more requests caused Claude to add some other categories and phrases. I printed a copy and put it next to my desk.

A few days later, I was running an errand and got a question which was best delegated -- but I didn't have the list handy. I copied the list into Notes.app, but then thought that it'd be cute if it was a basic web app too. Fortunately, Claude is now really good at this too. I asked it:

> Create a simple, plain Javascript web page based on the attached Markdown file, which prompts the user to select a list, and then shows a randomly-selected item from the list.
> 
> Items are grouped into lists under second-level headings (starting with "## "). Each list should be shown as a big button, with the name of the list appearing as the title on the button.
> 
> Lists are grouped into topics under first-level headings (starting with "# "). Each group should be shown as a box around the list buttons for that group, with the name of the group appearing in the top left of the box. Each group should have a different color, and the list buttons in that group are that color.
> 
> When the user presses a button, the app randomly selects one quote from that list, covers the page with a large, semi-transparent box, and prints the quote in large text in that box. The quote text should be large enough to easily read, but still all fit on one screen. Within that box, underneath the quote, two buttons appear: "Retry" and "Close". If the user clicks "Retry", the app selects a different quote from the same list, and updates the large quote text to that value. If the user clicks "Close", the app removes the large quote box and returns to its original state. 
> 
> The app should be entirely contained in no more than three files: an HTML file, a CSS file, and a JavaScript file.

The result was impressively functional - about 95% right in one shot. A few adjustments to the phrasing of the quotes, reorganising the categories to make them a little more consistent, and the layout of the CSS, and it was good enough to call `v0.1`. I was really impressed at what Claude can churn out quickly -- building this myself would realistically have taken a couple of hours, rather than the ~15 minutes it took using the LLM. 

You can play with the resulting app at [no.luckandskill.io](https://no.luckandskill.io), and the code is available on [GitHub](https://github.com/caelyx/no). I hope it helps lower the friction on saying "no", so you can make more progress on the things that really need your attention.