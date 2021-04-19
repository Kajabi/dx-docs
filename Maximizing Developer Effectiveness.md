# Maximizing Developer Effectiveness

### Metadata

- Author: [martinfowler.com](http://martinfowler.com)
- Full Title: Maximizing Developer Effectiveness
- Category: #articles
- URL: [https://martinfowler.com/articles/developer-effectiveness.html](https://martinfowler.com/articles/developer-effectiveness.html)

### Highlights

- depends on another team’s business capabilities for her feature. **She is able to find documentation and the API spec through a developer portal. She still has some queries, so she jumps into the team’s Slack room and quickly gets some help from another developer who is doing support.**
- **Releases the change gradually to users in production, while monitoring business and operational metrics.**
- **My research has shown that there are a number of key developer feedback loops. I recommend focusing on optimizing these loops, making them fast and simple. Measure the length of the feedback loop, the constraints, and the resulting outcome. When new tools and techniques are introduced, these metrics can clearly show the degree to which developer effectiveness is improved or at least isn't worse.**
- **Feedback Loop, Low Effectiveness, High Effectiveness**
   - **Validate a local code change works, 2 mins, 5-15 seconds (depending on tech choice)**
   - **Find root cause for defect, 4-7 days, 1 day**
   - **Validate component integrates with other components, 3 days - 2 weeks, 2 hours**
   - **Validate a change meets non-functional requirements, 3 months, 1 day - 1 week (depending on scope of change)**
   - **Become productive on new team, 2 months, 4 weeks**
   - **Get answers to an internal technical query, 1-2 weeks, 30 mins**
   - **Launch a new service in production, 2-4 months, 3 days**
   - **Validate a change was useful to the customer, 6 months or never, 1 - 4 weeks (depending on scope of change)**



- In reality, developers will compensate by filling these moments of inactivity with useful things. They might have two tasks going on and toggle between them. They might slow their compile frequency by batching up changes. In my research both of these will lead to a delay in integration of code, and development time.
- **How far do you take optimizing? When is enough? Imagine that now we have that change down to 15 seconds, but we think we can get it to three seconds. Is that worth the investment? It depends on how difficult it is to make that change and the impact it will bring. If you can develop a tool or capability that will speed up 10 teams then it might be worth it. This is where platform thinking, rather than optimizing for individual teams, comes into play.**
- Distributed systems are a particular challenge. There are many valid reasons for splitting systems into different deployable units (usually microservices). However, **distributed systems also make many things difficult (see Microservice Prerequisites), including developer effectiveness. Sometimes teams might optimize for team autonomy or for runtime performance, but they sacrifice developer effectiveness because they do not invest in maintaining fast feedback loops. This is a very common situation my company runs into.**
- Technical leaders continually measure and re-examine effectiveness. Highly effective organizations have created a framework to make data-driven decisions by tracking the four key metrics and other data points important to their context. **This culture starts at the executive level and is communicated to the rest of the organization**.
- Based on this information, engineering managers can decide on priorities for investments. Large problems may require correspondingly large programs of modernization to address a poor developer experience. But often it is more about empowering teams to make continuous improvement.
- **A key principle is to embrace the developer experience. It is common to see a program of work of a team focused on this. ::Developer experience means technical capabilities should be built with the same approaches used for end-user product development, applying the same research, prioritization, outcome-based thinking, and consumer feedback mechanisms.::**
- **To motivate developers, highly effective organizations franchise; that means developers should have the ability to improve their day to day lives. They have a policy for teams to make incremental technical improvements and manage technical debt. There should be a healthy data-backed discussion between developers and product management. Highly effective organizations also provide the ability for developers to innovate; when their teams have clear goals and a clear idea of bottlenecks, developers can be creative in solving problems. These organizations also create ways for the best ideas to "bubble to the top", and then double down, using data to evaluate what is best.**
- **The teams have technical product managers and success metrics related to how they are impacting the consuming teams. For example, a platform capability team focused on observability creates monitoring, logging, alerting, and tracing capabilities so that teams can easily monitor their service health and debug problems in their product.**
- Governance can have a critical role in effectiveness when it is implemented via:

Clear engineering goals

Specifying ways that teams and services communicate with each other

Encouraging useful peer review

Baking best practices into platform capabilities

**Automating control via architecture fitness functions**

- **4 Pillars of Developer Experience**

**::Help me craft products:: ensures we have the right abstractions, libraries, and scaffolding for product engineers to do their work.**

**::Help me develop, test, and deploy:: focuses on product engineers, specifically the development environments themselves (IDEs, linters), unit/integration test patterns/runners, and the deployment tooling and processes.**

**::Help me build with data:: focuses on data scientists and machine learning engineers, making sure the entire data engineering ecosystem is set up in a way that is intuitive, easy to test, and easy to deploy.**

**::Help me reduce toil:: focuses on the on-call engineers, to make sure we build production systems with the appropriate levels of automation, have runbooks and documentation that is easily accessible and current, and we track and prioritize reducing toil-y activities.**

- **They continually verify their effectiveness by tracking metrics including the 4 key metrics, and conducting monthly surveys with developers to capture net promoter scores (NPS).**

