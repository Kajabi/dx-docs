# Software Sprawl the Golden Path and Scaling Teams With Agency

### Metadata

- Author: charity.wtf
- Full Title: Software Sprawl, the Golden Path, and Scaling Teams With Agency
- Category: #articles
- URL: [https://charity.wtf/2018/12/02/software-sprawl-the-golden-path-and-scaling-teams-with-agency/](https://charity.wtf/2018/12/02/software-sprawl-the-golden-path-and-scaling-teams-with-agency/)

### Highlights

- **Everything is a tradeoff, obviously, but accepting somewhat more chaos in exchange for a stronger sense of individual ownership is usually the right one, and leads to higher-performing teams in the long run.**
- How to build a golden path and reverse software sprawl
   1. Assemble a small council of trusted senior engineers.
   2. Task them with creating a recommended list of default components for developers to use when building out new services. This will be your Golden Path, the path of convergence (and the path of least resistance).
   3. Tell all your engineers that going forward, the Golden Path will be fully supported by the org. Upgrades, patches, security fixes; backups, monitoring, build pipeline; deploy tooling, artifact versioning, development environment, even tier 1 on call support. Pave the path with gold. Nobody HAS to use these components … but if they don’t, they’re on their own. They will have to support it themselves.
   4. Work with team leads to draw up an umbrella plan for adopting the Golden Path for their current projects as well as older production services, as much as is reasonable or possible or desirable. Come up with a timeline for the whole eng org to deprecate as many other tools as possible. Allocate real engineering time to the effort. Hell, make a party out of it!
   5. After the cutoff date (and once things have stabilized), establish a regular process for reviewing and incorporating feedback about the blessed Path and considering any proposed changes, additions or removals.
- Tell all your engineers that going forward, the Golden Path will be fully supported by the org. Upgrades, patches, security fixes; backups, monitoring, build pipeline; deploy tooling, artifact versioning, development environment, even tier 1 on call support. Pave the path with gold. Nobody HAS to use these components … but if they don’t, they’re on their own. They will have to support it themselves.

The process must include talking to and gathering feedback from your engineers, talking to experts outside the company, talking to teams at other companies who are farther along using that technology, coming up with detailed pro/con lists and reasons for their choices. Maybe sometimes it includes prototyping something or investigating the technical depths … but yeah no mostly it’s just the talking.

- (Oh, incidentally, requiring an engineer to write up a proposal any time they want to use a non-standard component, and then defend their case while the council grills them in person — this will be nothing but good for them, guaran-fucking-teed.)
- Three is a good number for a council. More than that gets unwieldy, and may have trouble reaching consensus. Less than three and you run into SPOFs. You never want to have a single person making unilateral decisions because a) the decision-making process will be weaker, b) it sets that person up for too much interpersonal friction, and c) it denies your other engineers the opportunity to practice making these kinds of decisions.
- Your council members need technical breadth more than depth, and should be widely respected by engineers.

At least one member should have a long history with the company so they know lots of stupid little details about what’s been tried before and why it failed.

At least one member should be deeply versed in practical data and operability concerns.

They should all have enough patience and political skill to drive consensus for their decisions. Absolutely no bombthrowers.

Your council should create a detailed written plan describing which technologies are going to be supported … and a stab at what “supported” means. (Ask the experts in each component what the best practices are for backups, versioning, dependency management, etc.)

You might start with something like this:

- Backend lang: Go 1.11 ## we will no longer be supporting backend scripting languages
- Frontend lang: ReactJS v 16.5
- Primary db: Aurora v 2.0 ## Yes, we know postgres is "better", but we have many mysql experts and 0 pg experts except the one guy who is going to complain about this. You know who you are.
- Deploy pipeline: github -> jenkins + docker -> S3 -> custom k8s deploy tooling
- Message broker: kafka v 2.10, confluent build
- Mail: SES
- .... etc

Get approval from leadership to devote a certain amount of time to consolidating your stack and paying down a lump sum of tech debt. It depends on your stage of decay, but a reasonable amount of time might be “25% of engineering time for three months“. Whatever you agree to, make sure it’s enough to make the world demonstrably better for the humans who run it; you don’t want to leave them with a tire fire or you’ll blow your credibility.

- The council and team leads should come up with a rough outer estimate for how long it would take to rewrite everything and move the whole stack on to the Golden Stack. (It’s probably impossible and/or would take years, but that’s okay.) Next, look for the quick wins or swollen, inflamed pain points.

If you are running two pieces of functionally similar software, like postgres and mysql, can you eliminate one?

If you are managing something yourself that AWS could manage for you (e.g. postfix instead of SES, or kafka instead of kinesis), can you migrate that?

If you are managing anything yourself that is not core to your business value, in fact, you should try to not manage it.

If you are running any services by hand on an AWS instance somewhere, could you try using a service?

If you are running your own monitoring software, etc … can you not?

If you have multiple versions of a piece of software, can you upgrade or consolidate on one version?

- Note: These should be asked regularly, at least annual
- Can you write a wrapper so they get a bunch of end-to-end tests for free?
- Pay down as much debt as you can, but be pragmatic: it’s better to get rid of five small things than one large thing, from a support perspective. Your main goal is to shrink the number of types of software your team has to support, particularly databases.
- Do look for ways to make it fun, like … running a competition to see who can move the most tools to AWS in a week, or throwing a hack week party, or giving dorky prizes like trophies that entitle you to put your manager on call instead of you for a day, etc.
- After your target date has come and gone, you probably want to hold a post mortem retrospective and do lots of listening. (Well — first might I recommend a bubble bath and a bottle of champagne? But then a post mortem.)
- How are you going to handle the need for changes to the Golden Path? Monthly discussions? An email list? Quarterly meetings with a formal agenda? I’ve seen people do all of these and more, it doesn’t really matter afaict.
- Nobody likes a cabal, though, so the original council should gradually rotate out. I recommend replacing one person at a time, one per quarter, and rotating in another senior engineer in their place. This provides continuity while giving others a chance to learn these technical and political skills.
- if someone wants to propose adding a new tool to the default golden path, they can always add it themselves and gain some experience in it before bringing it to the council to discuss a formal place for it.

