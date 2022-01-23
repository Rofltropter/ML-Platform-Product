ML Platform Product

Presentation Flow:

- Powerpoint Slides for initial walkthrough
- Confluence for deeper documentation and historical revision
- Github for launchpad of written material
- Notion for storyboarding and roadmaps
- Mural for user journey

Presentation Conversation Flow:

*Introduction*
- First Email about Borealis (to Doug Douma I believe?)
- History on work at RBC. Connect to Borealis work
- History on AI talks and NVIDIA work, mention initial interviews of cnvrg, Domino data, and run.AI

*Problem Introduction*
- To examine this scenario aptly, we must look at two things: Industry, and Current State Internally
- Talk on Key industry issues (segregated compute, infancy of microservice scheduling for ML jobs - how microservices close the user experience gap - end to end platform.
- Speak about the Brain, where it sits currently (as I see it)
- Speak on the RBC's (and The Brain's) 'On-Premises Problem'
- Speak on Borealis and how they stand to benefit from fixing it.

*The Common Use Platform - Product Approach*
- Switch to Confluence view (or integrate into Powerpoint)
- To fix a problem, one must first approach with a well proven method of fixing problem...
- Speak on the Management style approach
- Speak on the Mission Statement, core vision, and then build and relate to problem space
- Speak on the key pillars of the solution space  (ML Development, engineering, and business contexts applied)
- Speak on the Core services of the Common Use suite (with DAG) as related to the key pillars of success
- Mention Pinky as the sidekick to The Brain - relate to ML Common Use Platform.
- Describe team management approach (Agile) in relation to Core Services. How work orchestration will be undergone, and optimization for task at hand will be implemented into workflow

*The Common Use Platform - Features and Goal Setting*
- Break down FR's and NFR's
- Build Simple Architecture Diagrams for Common Use Platform: The ML Platform and its internal and adjacent services. Include architecture (rough) diagrams, how v1->v2 movement will work, where team structures exist (in relation to existing team management approach)
- Visualize user experience journey in AD use-cases (problem space pillars of success)
- Visualize future state of platform components and integrations (with Galileo, and others)
- Build Stage breakdown (onboarding, Data exploration and access, Data movement, etc.) as well as Draft core stories to fulfill each stage

Work Flow:

- Document Product Management Strategy
- Derive Problem Statements
- Generate Core Vision Statement
- Build Platform Pillars of Success
- Segregate Platform Suite into Core Services (Build DAG for Service Organization)
- Creating AD pages for each Core Service
- Draft Features for each Core Service
- Create SWOT Analysis of Borealis AI
- Organize Accomplishments across goals


Work to be done:
- Create Core Functional and Non-Functional Requirements of Platform Suite Product
- Divvy platform suite into different functional groups
- Assign different development and business groups to these functional groups
- Separate document listing OCP structure of namespaces and purpose (automation)
- Figure out how we host S3 at RBC
- What does an average ML Developers product lifecycle look like, from experimentation to inferencing? Ask people at RBC.
- build ML user journey for: Full ML development in private cloud, Full ML development in public cloud, Develop in private and train in public, and vice versa
- build OKR (objectives and key results) for platforms
- Identify Mission statement for encompassing platform
- Build a sprint discovery plan (See Opus Sprint Discovery Plan)

# Key Pillars of success
When innovating, problem scopes

V1 of Platform:
1. Simple Data connectors to Source data
  - Assuming this is
2. A deep learning training framework (ex. Pytorch Lightning)
3. Hyperparameter tuning service
  - Hyperparamter tune in Pytorch Lightning with Ray Tune Python library?
  - Recipe for Success: Setup Automation via simple UI config (for *Developer Ease-of-Use*), Cross-tuning Metric Gathering,
    - Needs automatic loss function/independent metric hook injection into training framework (ex. PTL Lightning Module with callback to Tune)
  - Recipe for Success: Hadoop -> Cloudera




4. Large GPU cluster with job scheduling and management
5. Centralized model inference service
6. Full Experiment Management Service -

# For the Brain/Borealis (current state and future)
Experiment Management Service: Weights and Biases (already purchased by Borealis AI) https://wandb.ai/site, or MLFlow (used by CM but not there yet)

Hyperparameter tuning service: AirFlow (used in Public cloud by the Brain). Also does their end to end training, DAG and (soon enough) their notebook deployment automation. Currently deployed on-prem by (notably) CM Compute Fabric (*AIDiract)


Data Visualization: ROC Curve and AUC,

Data storage: Datalakes and S3 on prem (heavily used) vs. S3 at AWS (lesser usage). Portworx for in-cluster

Chargeback: Cloud Ability and native AWS chargeback help

Galileo is the feature storage, model registry, and dataset storage for the enterprise. Must integrate Here

Rachel says the platform Brain is building and Borealis is building is one in the same, Borealis is just faster and perhaps can get it done for the remainder of the enterprise

Will have to work with whoever rachel hires for Product manager



What ML Teams will need:

**Conception/Experimentation**:
  - Sandboxing:
    - Automatic provisioning of instance (Jupyter Notebooks, Pytorch)
**Development**
**Training**
**Inferencing**
**Path to Production**
**Lifecycle Management**
**Metric Gathering(job-based)**

What Business Stakeholders need:


What Engineering Owners need:
**De
**Metric Gathering(platform-based)**

## Vision of Platform:

Key Mantra's:

"I’m a strong believer in that repetitive routine work is your enemy. Why? Here is my list of personal concerns:

1. **Reproducibility of results.** Have you ever heard of a so-called human factor? We are very error-prone creatures and we are not good at memorizing something in great detail. The more human work some process involves the harder it will be to reproduce it in the future.
2. **Mental distractions.** Deep learning is an empirical endeavor and your progress in it relies deeply on your ability to iterate quickly and test as many hypotheses as you can. And due to that fact, anything that distracts you from your main task, — training and evaluating your models or analyzing the data, — negatively affects the success of an overall process.
3. **Effectiveness.** Computers do many things a lot faster than we, humans, do. When you have to repeat the same slow procedure over and over it all adds up.

Routine is your enemy" - Alexander Reshytko, Pytorch


**Vision Statement**:
The


## Glossary of Key Technologies (and their purpose)

**Openshift**: The grounding staple to all microservice deployments. All jobs, whether they be CPU or GPU driven must find fit their framework architecture to this platform. Luckily, it's hyper-flexible and enterprise-ready nature gives us a solid boilerplate architecture to mold success atop of.

**Run.AI**: A pivotal mutation of the Openshift boilerplate architecture, Run.AI adapts an Openshift cluster to

**Ansible**: Ansible is our wonderful base of automation. It allows us to  


## Must Complete Actions (and their purpose)

### Integrate Borealis with Helios

Streamlining the onboarding process is never simple. Luckily, we are not alone in that endeavor. The Helios internal-RBC product provides a full fledged user onboarding experience to RBC internal platforms - public and private cloud based. Openshift, of course, is among this list - and would serve as a vital step to removing repetitive work (see mantra).

*Functional Requirements*:



### Scale RH onto AWS (ROSA)

With Red Hat Openshift Service on AWS (ROSA), we can unify (and automate) development to deployment frameworks while still maintaining hybrid cloud capability. This would allow agnostic migration of existing OCP workloads to a public cloud frame on demand.

*Non-Functional Requirements*:  
  - Acceptable Data Gravity Complications: The platform must be able to move data from an S3 or Portworx storage context to a ROSA-compatible storage instance without unacceptable data costs or latency deemed detrimental to deployment or generic container operation
  - Hybrid-Cloud Storage Configuration:

## Quick Answers to Key Scenario Questions

### How would you organize your group of software engineers to optimize development?**

### What steps would you take to roll your team structure out and establish the best agile software development practices?

### Describe your process in going from version 1 of the Common Platform to version 2?


### Provide a vision of an ML platform that you think would help accelerate ML Development. Be specific on what ML Platform capabilities might be missing and what the developer's experience might look like based on the information from this case study and any external Knowledge.

### How will you attract customers? And how will you make the platform core to the ML Development lifecycle?

### Borealis AI partners with other ML Platform teams from Capital Markets and RBC Technology & Operations to help build a centralized ML Platform that can serve a broader range of Data scientists across the bank. Describe a stakeholder management strategy to help position our platform to provide value for the bank as a whole?


Features and Platform architecture
- Spring Discovery Planning
- Customer Journey, storyboarding
- Major Features (Platform Suite DAG)
  - Platform Reference Architecture
  - Brief Exploration of Platform Service Architecture
- Cross-Bank Strategy
- Migration between V1 -> V2
- Team Orchestration
- O
