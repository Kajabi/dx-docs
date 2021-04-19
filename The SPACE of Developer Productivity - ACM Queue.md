# The SPACE of Developer Productivity - ACM Queue

### Metadata

- Author: [queue.acm.org](http://queue.acm.org)
- Full Title: The SPACE of Developer Productivity - ACM Queue
- Category: #articles
- URL: [https://queue.acm.org/detail.cfm?id=3454124](https://queue.acm.org/detail.cfm?id=3454124)

### Highlights

- The prevalence of these myths and the need to bust them motivated our work to develop a practical multidimensional framework, because ::**only by examining a constellation of metrics in tension can we understand and influence developer productivity**.:: **This framework, called SPACE, captures ::the most important dimensions of developer productivity: satisfaction and well-being; performance; activity; communication and collaboration; and efficiency and flow.::**
- Myth: Productivity is only about engineering systems and developer tools

While developer tools and workflows have a large impact on developer productivity, human factors such as environment and work culture have substantial impact too. **::Often the critical work needed to keep the environment and culture healthy can be "invisible" to many members of the organization or to metrics traditionally used for measuring productivity.:: Work such as morale building, mentoring, and knowledge sharing are all critical to supporting a productive work environment and yet are often not measured. The "invisible" work that benefits the overall productivity of the team is just as important as other more commonly-measured dimensions. [21]**

- **Satisfaction is how fulfilled developers feel with their work, team, tools, or culture; well-being is how healthy and happy they are, and how their work impacts it. Measuring satisfaction and well-being can be beneficial for understanding productivity [20] and perhaps even for predicting it. [15]** For example, productivity and satisfaction are correlated, and it is possible that satisfaction could serve as a leading indicator for productivity; a decline in satisfaction and engagement could signal upcoming burnout and reduced productivity. [13
- **To assess the satisfaction dimension, you might measure the following:**

**::• Employee satisfaction.:: The degree of satisfaction among employees, and whether they would recommend their team to others.**

**::• Developer efficacy.:: Whether developers have the tools and resources they need to get their work done.**

**• ::Burnout.:: Exhaustion caused by excessive and prolonged workplace stress.**

- **::performance is often best evaluated as outcomes instead of output::**. The most simplified view of software developer performance could be, Did the code written by the developer reliably do what it was supposed to do? **Example metrics to capture the performance dimension include:**

**• ::Quality.:: Reliability, absence of bugs, ongoing service health.**

**• ::Impact::. Customer satisfaction, customer adoption and retention, feature usage, cost reduction.**

- **::A well-designed engineering system, however, will help in capturing activity metrics along different phases of the software development life cycle and quantify developer activity at scale.:: Some of the developer activities that can be measured and quantified relatively easily are:**

**• Design and coding. Volume or count of design documents and specs, work items, pull requests, commits, and code reviews.**

**• Continuous integration and deployment. Count of build, test, deployment/release, and infrastructure utilization.**

**• Operational activity. Count or volume of incidents/issues and distribution based on their severities, on-call participation, and incident mitigation.**

- **Software development is a collaborative and creative task that relies on extensive and effective communication, coordination, and collaboration within and between teams. [11]** **::Effective teams that successfully contribute to and integrate each other's work efficiently rely on high transparency [5] and awareness [6] of team member activities and task priorities. In addition, how information flows within and across teams impacts the availability and discoverability of documentation that is needed for the effective alignment and integration of work. Teams that are diverse and inclusive are higher performing. [22]::** More effective teams work on the right problems, are more likely to be successful at brainstorming new ideas, and will choose better solutions from all the alternatives.
- That said, the following are examples of metrics that may be used as proxies to measure communication, collaboration, and coordination:

**• Discoverability of documentation and expertise.**

**• How quickly work is integrated.**

**• Quality of reviews of work contributed by team members.**

**• Network metrics that show who is connected to whom and how.**

**• Onboarding time for and experience of new members.**

- **::Some research associates productivity with the ability to get complex tasks done with minimal distractions or interruptions. [2]::** This conceptualization of productivity is echoed by many developers when they talk about "getting into the flow" when doing their work—or the difficulty in finding and optimizing for it, with many books and discussions addressing how this positive state can be achieved in a controlled way.4 **::For individual efficiency (flow), it's important to set boundaries to get productive and stay productive::—for example, by blocking off time for a focus period. Individual efficiency is often measured by uninterrupted focus time or the time within value-creating apps (e.g., the time a developer spends in the integrated development environment is likely to be considered "productive" time).**
- At the team and system level, efficiency is related to value-stream mapping, which captures the steps needed to take software from idea and creation to delivering it to the end customer. To optimize the flow in the value stream, **::it is important to minimize delays and handoffs::. The DORA (DevOps Research and Assessment) framework introduced several metrics to monitor flow within teams [9]—for example, deployment frequency measures how often an organization successfully releases to production, and lead time for changes measures the amount of time it takes a commit to get into production.**
- In addition to the flow of changes through the system, the flow of knowledge and information is important. Certain aspects of efficiency and flow may be hard to measure, but it is often possible to spot and remove inefficiencies in the value stream. Activities that produce no value for the customer or user are often referred to as software development waste19—for example, duplicated work, rework because the work was not done correctly, or time-consuming rote activities.

**Some example metrics to capture the efficiency and flow dimension are:**

**• Number of handoffs in a process; number of handoffs across different teams in a process.**

**• Perceived ability to stay in flow and complete work.**

**• Interruptions: quantity, timing, how spaced, impact on development work and flow.**

**• Time measures through a system: total time, value-added time, wait time.**

- Having too many metrics may also lead to confusion and lower motivation; not all dimensions need to be included for the framework to be helpful. For example, if developers and teams are presented with an extensive list of metrics and improvement targets, meeting them may feel like an unattainable goal. With this in mind, note that **::a good measure of productivity consists of a handful of metrics across at least three dimensions; these can prompt a holistic view, and they can be sufficient to evoke improvement.::**
- We have written elsewhere about the limitations inherent in the use of story points,9 which could give teams incentive to focus on their own work at the expense of collaborating on important projects.
- **Teams and organizations should be cognizant of developer privacy and report only anonymized, aggregate results at the team or group level.** (In some countries, reporting on individual productivity isn't legal.)
- **::any measurement paradigm should check for biases and norms.::** These are external influences that may shift or influence the measures. Some examples are included here, but they aren't exhaustive, so all teams are encouraged to look for and think about external influences that may be present in their data:

• **Peer review and gender. Research shows that women are more likely to receive negative comments and less likely to receive positive comments in their code reviews. [16]** Any analysis of satisfaction with the review process should check for this in your environment. Understand that developers are likely influenced by the broader tech industry even if the patterns are not in your organization or team. Take these effects into account.

• **Normalizing measures across time. Teams should be careful about any methods used to normalize time, especially across long periods. For example, looking at metrics over a year would bias against those taking parental leave.**

• Perceptual measures. Teams and organizations should be mindful of cultural norms—and embrace these. Some cultures naturally report higher, while some report lower. It doesn't mean perceptual measures can't be trusted; it just means measures from these different cultures will have a different baseline and shouldn't be compared with each other.

- **Satisfaction: how satisfied SREs are with the IM process, escalation and routing, and on-call rotations are key metrics to capture, especially since burnout is a significant issue among SREs.**

**• Performance: these measures focus on system reliability; monitoring systems' ability to detect and flag issues faster, before they hit the customer and become an incident. MTTR (mean time to repair) overall, and by severity.**

**• Activity: number of issues caught by the monitoring systems, number of incidents created, number of incidents resolved—and their severity distribution.**

• **Communication and collaboration: people included in resolving the incident, how many teams those people came from, and how they communicate during an incident. Incident resolution documentation outlines the steps involved in resolving incidents; this can be measured by completeness (to check if any resolution data was entered) or quick quality scores (e.g., thumbs up/down). Teams may also include a metric that measures the percentage of incidents resolved that reference these guides and documentation.**

**• Efficiency and flow: incident handoffs, incident assignment/re-assignment, number of hops an incident has to take before it is assigned to the right individual or team.**

- [2]: Brumby, D. P., Janssen, C. P., Mark, G. 2019. How do interruptions affect productivity? In Rethinking Productivity in Software Engineering, ed. C. Sadowski and T. Zimmermann, 85-107. Berkeley, CA: Apress; [https://link.springer.com/chapter/10.1007/978-1-4842-4221-6_9](https://link.springer.com/chapter/10.1007/978-1-4842-4221-6_9).
- [5]: Dabbish, L., Stuart, C., Tsay, J., Herbsleb, J. 2012. Social coding in GitHub: transparency and collaboration in an open software repository. In Proceedings of the ACM 2012 Conference on Computer-supported Cooperative Work (February), 1277-1286; [https://dl.acm.org/doi/10.1145/2145204.2145396](https://dl.acm.org/doi/10.1145/2145204.2145396).
- [6]: Dourish, P., Bellotti, V. 1992. Awareness and coordination in shared workspaces. In Proceedings of the 1992 ACM Conference on Computer-supported Cooperative Work (December), 107-114; [https://dl.acm.org/doi/10.1145/143457.143468](https://dl.acm.org/doi/10.1145/143457.143468).
- [9]: Forsgren, N., Humble, J. Kim, G. 2018. Accelerate: The Science of Lean Software and DevOps: Building and Scaling High Performing Technology Organizations. IT Revolution Press.
- [11]: Fuks, H., Raposo, A., Gerosa, M. A., Pimental, M. 2008. The 3C collaboration model. In Encyclopedia of E-Collaboration, ed. Ned Kock, 637-644. IGI Global; [https://www.researchgate.net/publication/292220266_The_3C_collaboration_model](https://www.researchgate.net/publication/292220266_The_3C_collaboration_model).
- [15]: Murphy-Hill, E., Jaspan, C., Sadowski, C., Shepherd, D., Phillips, M., Winter, C., Knight, A., Smith, E., Jorde, M. 2019. What predicts software developers' productivity? IEEE Transactions on Software Engineering; [https://ieeexplore.ieee.org/document/8643844/](https://ieeexplore.ieee.org/document/8643844/).
- [16]: Paul, R., Bosu, A., Sultana, K. Z. 2019. Expressions of sentiments during code reviews: male vs. female. In IEEE 26th International Conference on Software Analysis, Evolution and Reengineering (SANER) , 26-37; [https://ieeexplore.ieee.org/document/8667987](https://ieeexplore.ieee.org/document/8667987).
- [20]: Storey, M. A., Zimmermann, T., Bird, C., Czerwonka, J., Murphy, B., Kalliamvakou, E. 2019. Towards a theory of software developer job satisfaction and perceived productivity. IEEE Transactions on Software Engineering; [https://ieeexplore.ieee.org/document/8851296](https://ieeexplore.ieee.org/document/8851296).
- [21]: Suchman, L. 1995. Making work visible. Communications of the ACM 38(9), 56-64; [https://dl.acm.org/doi/10.1145/223248.223263](https://dl.acm.org/doi/10.1145/223248.223263).
- [22]: Vasilescu, B., Posnett, D., Ray, B., van den Brand, M. G. J., Serebrenik, A., Devanbu, P., Filkov, V. 2015. Gender and tenure diversity in GitHub teams. In Proceedings of the 33rd Annual ACM Conference on Human Factors in Computing Systems (April), 3789-3798; [https://dl.acm.org/doi/abs/10.1145/2702123.2702549](https://dl.acm.org/doi/abs/10.1145/2702123.2702549).

