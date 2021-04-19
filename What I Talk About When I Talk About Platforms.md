# What I Talk About When I Talk About Platforms

### Metadata

- Author: [martinfowler.com](http://martinfowler.com)
- Full Title: What I Talk About When I Talk About Platforms
- Category: #articles
- URL: [https://martinfowler.com/articles/talk-about-platforms.html](https://martinfowler.com/articles/talk-about-platforms.html)

### Highlights

- #### Backlog coupling happens when changes have dependencies across the backlogs (work queues) of multiple teams

It’s a simple concept - if a large number of items in the backlog of a digital product team require a corresponding backlog item to be raised in another team, then productivity and responsiveness suffer enormously. Backlogs get chained across the organisation, each being prioritised according to a different system. Tasks acquire big red ‘blocked’ stickers on kanbans, stakeholders get angry, the shared service providers react as best they can - usually responding to the loudest voice.

- **The recent tradition of ‘scaling agile’ tries to solve this in one way - by introducing planning ceremonies that attempt to align priorities across multiple teams. This explicitly trades off an increase in alignment for overall reduced autonomy, responsiveness and ability to respond to change.** This cannot be the only way.
- **::So clearly a characteristic of a good platform must be that it reduces the amount of backlog coupling. The platform must provide services that do not require tickets to be raised and work to be assigned. Self-service is a key defining characteristic for a good platform::.**
- Autonomy speeds time to market, increases innovation

Most organisations I meet have a default setting of “build for re-use”: centralisation of capabilities driven by a combination of risk-aversion and cost reduction.

- As part of the migration, product teams at WebBiz were given complete autonomy over how they configured and ran every part of their stack. The approach was named ‘Team Managed Infrastructure’ - although there were some defaults established early on, each team would make it’s own decisions on every part of the stack with almost no central mandates.

WebBiz had successfully reversed the typical default bias for organisations: favouring technology diversification and invention. This drove up the level of staff engagement, with engineers getting experience deeper in the stack of technology, drove invention, quickly established a level of responsibility for what was deployed, and eliminated the bulk of team dependencies. It also attracted engineers to work at WebBiz who are interested in both taking on responsibility for what they run, who respond well to autonomy, and who are interested in solving difficult business and technical problems.

Technology diversification increases drag

**However, for all the benefits there is a definite cost to shifting to full autonomy.**

- **In addition to the maintenance drag of duplicated infrastructure, there is an ongoing overhead for each team to continually research and evaluate their infrastructure choices There’s also a friction created which works against the transfer of skills and even staff between teams which are running distinctly different stacks.**
- WebBiz is now beginning to establish a more-clearly defined delivery infrastructure platform - a compelling set of defaults that product teams can consume to reduce the amount of drag and increase their productivity.

But do they risk losing the benefits that autonomy has brought?

- **::Platform as an internal product::**

**It is a real struggle to find the right balance between autonomous diversification and mandated consolidation, and that is even more difficult to predict up front. A key ingredient for success in finding this balance is that platforms must be compelling to use, they cannot stand on a mandate alone.** Your existing shared infrastructure function has a monopoly and delivery teams have no viable alternative. **A little competition is a necessary ingredient to drive the product thinking ensuring that every platform feature adds value instead of creating constraints and coupling.**

A key ingredient for success in finding this balance is that platforms must be compelling to use

What makes a platform compelling? Here are a few ideas:

#### ::The platform is self-service for the overwhelming majority of use cases.::

#### ::The platform is composable, containing discrete services that can be used independently.::

#### ::The platform does not force an inflexible way of working upon the delivery team.::

#### ::The platform is quick and cheap to start using, with an easy on-ramp (e.g. Quick start guides, documentation, code samples)::

#### ::The platform has a rich internal user community for sharing::

#### ::The platform is secure and compliant by default::

The platform is up to date

- Ultimately the delivery infrastructure platform is compelling when it is easier to consume the platform capability than building and maintaining your own thing. Netflix describes their centralised tooling as ‘the paved road’ - teams do not have to make use of the tooling but are responsible for all the costs of maintaining their own alternatives.

#### ::A platform should also be more than just software and APIs - it is documentation, and consulting, and support and evangelism, and templates and guidelines.::

- You may choose to build a team to build and operate a delivery infrastructure platform - I think in most cases that’s going to be the best way to get started. If so, **you should be very clear on the scope of responsibilities for the platform team vs its customers - which I’ll call application teams for clarity.**

**Application teams build, deploy, monitor, and are on call for the application components and application infrastructure that they provision and deploy on the platform. Platform teams build, deploy, monitor, and are on call for the platform components and underlying platform infrastructure.**

#### The platform team ideally doesn’t even know what applications are running on the platform, they are only responsible for the availability of the platform services themselves.

In this way both application teams and platform teams have responsibility for build and run of their own products. ‘You build it, you run it’ still applies.

