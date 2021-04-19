# Myth of Developer Productivity

### Metadata

- Author: [nortal.com](http://nortal.com)
- Full Title: Myth of Developer Productivity
- Category: #articles
- URL: [https://nortal.com/us/blog/the-myth-of-developer-productivity/](https://nortal.com/us/blog/the-myth-of-developer-productivity/)

### Highlights

- **Story points also aren’t consistent between developers. Even if everybody agrees that it’s a 3-point story, based purely on effort and risk, the wall-time delivery will be different depending on who picks it up. One developer who is intimately familiar with that code may be able to finish in 2-3 hours, while a new junior developer may struggle for 1-2 days. This is proof that we’ve decoupled productivity from points, and why it’s a bad metric.**

On the official Scrum forums, practioners always have to explain why story points are not a measure of productivity. The Scrum Alliance even has a whitepaper called The Deadly Disease of Focus Factors, and here is the opening statement of the document:

To check your organizational health, answer these two questions:

1. Do you estimate work in “ideal” hours?
2. Do you follow up on your estimates, comparing it to how many “real” hours work it actually took to get something done?

If so, you may be in big trouble. You are exhibiting symptoms of the lethal disease of the “focus factor”. This is how the illness progresses:

Speed of development will keep dropping together with quality. Predictability will suffer. Unexpected last moment problems and delays in projects are common. Morale will deteriorate. People will do as they are told, but little more. The best people will quit. If anything gets released it is meager, boring and not meeting customer expectations. As changes in the business environment accelerate, the organization will be having trouble keeping up. Competitors will take away the market and eventually the end is unavoidable.

- **::Every time something impedes progress, make a note of what it is, and how long it took to resolve. This is especially good to do for any external dependencies. Any time the work leaves the direct, in-progress control of the developer, track who it goes to, and how long they have it.::**
- Track how long it takes from the point the business requests a work item, to when it’s available for use in production. Over time, this metric will stabilize. If the units of work are somewhat consistently sized, predictability will be gained.
- This one tracks the total amount of wall time taken from when work starts on an item, to when it’s delivered. Again, if the units of work are approximately similar sized, predictability will be gained here.
- This one **tracks the wall time in each phase. Remember how I told you to track external organizations? You should be tracking every phase.** The design phase, the dev phase, the QA phase, the code review phase, even the deployment phase. By having every phase tracked, you can identify the slower phases, and see if there is any room for optimization.

