# Structuring a Cloud Infrastructure Organization

### Metadata

- Author: [bravenewgeek.com](http://bravenewgeek.com)
- Full Title: Structuring a Cloud Infrastructure Organization
- Category: #articles
- URL: [https://bravenewgeek.com/structuring-a-cloud-infrastructure-organization/](https://bravenewgeek.com/structuring-a-cloud-infrastructure-organization/)

### Highlights

- While we approach this problem holistically, it can generally be looked at as two components: product development and infrastructure. One might wonder if this is still the case with the shift to DevOps and cloud, but as we’ll see, these two groups still play important and distinct roles.
- **The idea of Developer Enablement is ::shifting the focus of ops teams from being “masters” of production to “enablers” of production by applying a product lens to operations::. In practical terms, this means less running production workloads on behalf of developers and more providing tools and products that allow developers to run workloads themselves. It also means thinking of operations less as a task-driven service model and more as a strategic enabler. However, Developer Enablement is not about giving full autonomy to developers to do as they please, it’s about providing the abstractions they need to be successful on the platform while realizing the operational efficiencies possible in a larger organization. This means providing common tooling, products, and patterns. These are developed in partnership with product teams so that they meet the needs of the organization. Some companies might refer to this as a “platform” team, though I think this has a slightly different meaning. So how does this map to an actual organization?**
- We like to model the infrastructure organization as three teams: Developer Productivity, Infrastructure Engineering, and Cloud Engineering.
- Developer Productivity

**::Developer Productivity is tasked with getting ideas from an engineer’s brain to a deployable artifact as efficiently as possible.:: This involves building or providing solutions for things like CI/CD, artifact repositories, documentation portals, developer onboarding, and general developer tooling. This team is primarily an engineering spend multiplier. Often a small Developer Productivity team can create a great deal of leverage by providing these different tools and products to the organization. Their core mandate is reducing friction in the delivery process.**

- Infrastructure Engineering

**::The Infrastructure Engineering team is responsible for making the process of getting a deployable artifact to production and managing it as painless as possible for product teams.:: Often this looks like providing an “opinionated platform” on top of the cloud provider**

- Completely opening up a platform such as AWS for developers to freely use can be problematic for larger organizations because of cost and time inefficiencies. It also makes security and compliance teams’ jobs much more difficult. Therefore, this group must walk the fine line between providing developers with enough flexibility to be productive and move fast while ensuring aggregate efficiencies to maintain organization-wide throughput as well as manage costs and risk. **This can look like providing a Kubernetes cluster as a service with opinions around components like load balancing, logging, monitoring, deployments, and intra-service communication patterns. Infrastructure Engineering should also provide tooling for teams to manage production services in a way that meets the organization’s regulatory requirements.**
- **The question of ownership is important. In some organizations, the Infrastructure Engineering team may own and operate infrastructure services, such as common compute clusters, databases, or message queues. In others, they might simply provide opinionated guard rails around these things. Most commonly, it is a combination of both. Without this, it’s easy to end up with every team running their own unique messaging system, database, cache, or other piece of infrastructure.** You’ll have lots of architecture astronauts on your hands, and they will need to be able to answer questions around things like high availability and disaster recovery. This leads to significant inefficiencies and operational issues. Even if there isn’t shared infrastructure, it’s valuable to have an opinionated set of technologies to consolidate institutional knowledge, tooling, patterns, and practices. This doesn’t have to act as a hard-and-fast rule, but it means teams should be able to make a good case for operating outside of the guard rails provided.
- **This group should also own standards around things like logging and instrumentation. These standards allow the team to develop tools and services that deal with this data across the entire organization.** I’ve talked about this notion with the Observability Pipeline.
- **Other examples of this include network configuration, certificate management, logging agents, intrusion detection, and SIEM.**
- **In terms of realizing efficiencies, this mostly consists of managing AWS accounts, organization policies (another important security facet), and billing. This group owns cloud spend across the organization and, as a result, is able to monitor cumulative usage and identify areas for optimization. This might look like implementing resource-tagging policies, managing Reserved Instances, or negotiating with AWS on committed spend agreements.**
- Cloud Engineering

