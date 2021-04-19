# DX

## Brain dump
- You build it, you run it
  - Need to hire people with more experience with DBA/PostgreSQL, scaling, performance, etc.
  - DX can create skills matrix and suggest learning materials
  - Developers need actual operations experience. Maybe they can shadow on-call. We should have more developers who have hands-on experience with indexing, maintenance, capacity planning, monitoring, etc. for PostgreSQL
- We should have a documented example of leaving the Golden Path
  - Steve has mentioned Themes might want to use EBS to store theme files in Kubernetes. This is leaving the Golden Path, so maybe we could work with them to both train and document the process for leaving the Golden Path.
- Dynamic configuration without environment variables. Redis is a possible candidate, we'd need a good UI and guardrails, automations.
- Scope: Defining and measuring technical debt. Non-scope: Fixing technical debt.
- Scope: Measure and incentivize upgrades/migrations. Non-scope: Upgrading rails, gems, Ruby.
- Scope: Tools and scorecards for SLOs. Non-scope: Defining SLOs. Though consulting with teams to help them define their own SLOs is definitely in scope.
- Non-scope: Developer support. You build it, you run it. The only thing DX supports are the tools we build. (We probably need a developer support team. These would not have to be highly skilled software engineers IMHO, where we _do_ want highly skilled software engineers / PEs on DX. Developer support could likely be outsourced, at least initially).
- Should there be a Staff SDE who owns Rails upgrades (in terms of being the shepherd)? Or can DX own making sure the work is tracked and prioritized?
- How can we actually quantify the priority of gem upgrades?
- WAL based Rails connection resolver.
- Detect long-running experiments
- Create experiments API for sub-experiments
  - In some cases, we want a scientist experiment to have sub-experiments, meaning that we want to track results separately but if the parent experiment runs in a given child request or job, all of its child experiments should also run. Steve ended up using a thread local to conditionally run code regardless of the location in the call stack, but this doesn't allow the results of the sub-experiments to be aggregated.
- Runbooks plugin for Radiator (c.f. https://process.st and gitlab/runbooks (jsonnet))
- On-call plugin for Radiator with declarative schedules and pager fatigue detection.
- Scientist plugin for Radiator
  - Abstract backends for observations include Redis and DynamoDB
- Feature toggle plugin for Radiator
- Amplitude plugin for Radiator
- A/B testing (Optimizely) plugin for Radiator
- Operation readiness checklists plugin for Radiator
- SLOs plugin for Radiator
- Breaking changes to environments should be opt-out and use a deprecation pattern (same interface, but give instructions to use new one and how to opt-out).
- Post release migrations docs
- shipit: mark as unsafe to rollback if non-deterministic (feature flags, migrations, etc.)
- Track deploys and correlate deploys with errors and error rate
- Move session storage to memcached
- Service template
  - Each service has SLOs. Before something can be extracted from the monolith, SLOs must be defined for it, but more importantly, for all the things that depend on it.
- Send survey to devs and EMs about DX
- Move SpecStats to spec_helper.rb
- Buy don't build (unless building provides competitive advantage)
- https://github.blog/2015-06-30-scripts-to-rule-them-all/
- https://github.com/nullobject/rein
- Production and dev should share a docker container. The container should support a flag to switch to "dev" mode, in which case it has different configuration. It should accept a separate flag that runs in production-like mode but uses local files.
- Throttle writes to PostgreSQL
  - Create patterns and perhaps even a gem or API that allows for following the Rails Way but that intelligently throttles write throughput. e.g. `dependent: :destroy` could be extended to enqueue a throttled background job for large tables.
  - Extend https://github.com/github/freno or write a PostgreSQL version from scratch that allows clients to coordinate when writing to a database.
- Fix MockRedis (c.f. https://kajabi.slack.com/archives/C9CLGUP7S/p1616542936203100)
- https://github.com/shopify/semian
- Benefit of Slack / ChatOps: Discoverability. Every time it's used by someone, it's teaching everyone else how to use it.
- Add "unsafe" allowances from Rails upgrade to Radiator
- Radiator dependency tracking plugin that requires a reason for existing and ownership team
- Radiator plugin for migrations (esp Rails upgrades) that include Gantt chart, test metrics, deprecation metrics, and ownership teams. c.f. https://engineering.atspotify.com/2020/06/25/tech-migrations-the-spotify-way/
- If we need to create our own tool for Radiator, we need a pretty thorough write up of why existing tools like Backstage aren't a good fit. Buy don't build. Is there a commercial solution? https://www.getcortexapp.com doesn't look extensible.
- Squash Rails migrations
- Heroku CLI replacement
- [WIP - Rspecq integration](https://github.com/Kajabi/kajabi-products/pull/17167)
- [Stdout bug fix and pass timeout as a param](https://github.com/Kajabi/rspecq/pull/2)
- Profile CI and reduce memory usage
- Make post release migrations use PgLock
- Document and extend terragrunt or write our own opinionated wrapper. Maybe a Kajabi course? terragrunt is documented kind of poorly and if we want devs to use it, we need to make it compelling. e.g. renaming state files is a PITA
- Terraform Datadog and OpsGenie
- Slack RFC
- Demo data migrations and post release migrations during Engineering Discussion
- Write up a case for head count
- If DX is same team as PE, how do we deal with on-call?
- We should only start on a project if dev capacity is allocated.
- Monolith Golden Path: Controller actions and jobs are categorized by data access patterns
- Tag errors with Ruby & Rails version for debugging dual booting
- https://github.blog/2020-12-16-reducing-flaky-builds-by-18x/, especially the screenshot of GitHub’s internal CI tooling.

- shipit
  - [[Proposal] Restructuring PullRequest](https://github.com/Shopify/shipit-engine/issues/1093)
  - [Allow deployment of branch](https://github.com/Shopify/shipit-engine/issues/181)
  - [Merge Queue v2 in shipit-engine?](https://github.com/Shopify/shipit-engine/issues/956)

- Shopify's Slack bot

```
#war-room
---
@hormoz: spy incident start me "Wholesale app data loss"

@spy: :fire: An incident was reported at 2017-08-23 14:39:42 UTC. @hormoz is the IMOC.
      Status summary: "Wholesale app data loss"
      Incident was bound to #war-room. Please use #war-room for communications, or rebind the incident with `incident channel ...`.

@hormoz DM
---
@spy: :fire: You are IMOC for the incident being tracked in #war-room: "Wholesale app data loss". :red-circle: Please update the [status page](https://url.for.status.page).

@etchensketch DM (stakeholder)
---
@spy: :warning: Hey @etchensketch, and incident ("Wholesale app data loss") is active and has been bound to #war-room. You may contact the IMOC (@hormoz) for more details.
```

```
#deploy
---

@thomson: spy shipit lock shopify "Prepping for an isolated rollout of https://github.com/Shopify/shopify/pull/124030 - I will deploy the backlog first"

@spy: :lock: [shopify/shopify/production](https://url.for.shipit) locked
      :ship: :lock: @thomson just locked [shopify/production] because:
      > Prepping for an isolated rollout of https://github.com/Shopify/shopify/pull/124030 - I will deploy the backlog first
      @thomson: Switch to a new exceptions handler (#124030)
      Please don't merge while master is locked! Use the [merge queue]() and/or [Here Comes The Walrus]().

@bergen: FYI: we're rolling out changes to exception reporting. We want to make sure nothing else gets deployed at the same time, because we would be blind for any other issues that would pop up
@bergen: spy oncall imoc

@spy: Currently on call for ProdEng IMOC:
      ProdEng IMOC Primary: @ryanbrush (ryan.brushett@shopify.com) Until: 2017-08-01T20:00:00Z UTC
```

```
@jarthorn DM
---
@spy: :ship: Your commit is deploying for [shopify/production]()
      *Deployer*: (Shipit)
      *Deploying to Revision*: `d60c6988`
      *Links*: ([logs]()/[abort]()/[rollback]()|[diff]())
      Please keep an eye on #operations, and the [deploy dashboard]() until it's complete.

      - `fe89db32` @jarthorn: Add operations as service slack channel (#123418)

@spy: :ship: :green-check: Deploy of the following commit completed successfully.

      - `fe89db32` @jarthorn: Add operations as service slack channel (#123418)

      Please make sure your changes work and perform correctly.
      If they don't, [rollback]().
      If something is broken that is impacting customers, page IMOC using `spy page IMOC [message]` to start an incident.
```

> Engineering Productivity uses infrastructure, systems expertise, metrics and insights to build efficiency and effectiveness in our developer workflow. Building new products and features is one thing, making them scalable, reliable, and efficiently {developed, tested, released, monitored} is another story altogether — equally complicated, potentially more largely unexplored at Google's scale and complexity.
> -- Michael Bachman, VP Engineering at Google

