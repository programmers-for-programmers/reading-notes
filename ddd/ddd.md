# Domain Driven Design

## Key Objectives

- Centering the project's focus on the business domain and it's logic
- Employing a domain model to facilitate creating complex designs
- Establishing a collaborative effort between technical and domain experts to iteratively refine a conceptual model that addresses specific domain problems

## Primary advantages of domain driven design

- Eases Communication
  - Helps the team to create a common model. The business and developer teams can then use this model to communicate the business requirements, data entities and process models
 
- Provides flexibility
  - Everything in the domain model is based on an object and therefore will be modular and encapsulated, enabling the system to be changed and improved regularly and continously
  - It encourages the Separation of Concerns and the isolation of different arts of the domain that represent knowledge from the business side
 
- Improved patterns



## Domain driven design building blocks

- Ubiquitous Language
  - The language that technical team will develop in collaboration with domain experts to share the common understanding

- Bounded context/Context Map
  - This isolates specific areas of business from each other
 
- Domain
  - This is the sphere of knowledge (ontology), influence, or activity
  - This is the subject area of the particular domain
    
- Model
  - A system of abstractions that describes selected aspects of a domain and can be used to solve the problem for that domain
 
## Ubiquitous Language

- This calls for the cultivation of a shared, business oriented language.
- This language should resemble the business domain and its terms, entities and processes.
- For example, if the accounting department needs some functionality implemented, everyone (including business and technical team) must have the same understanding of accounting concepts.



## Bounded Context / Context Maps

- This concept isolates specific areas of business from each other, all together constituting what is called a domain
- This bounded context is like a isolated sandbox that will contain specific parts of the domain knowledge and that will not interfere with other sandboxes
- Within this sandbox, language specific to that particular business area is defined - a specific ubiquitous language
- Context maps are basically a way of describing how informations are exchanged between two sandboxes, example Accounting and Sales both refer to the specific customer
  - Context maps serve to create some adapters on both sides of Sales and Accounting while keeping the customer concept unchanged on both sandboxes
- Upstream context will influence the Downstream, but not the opposite.
- In order to maintain its conceptual integrity against changes in the upstream, DDD proposes a pattern called 'Anti-Corruption-Layer (ACL)'.
  - It is basically the downstream will have a ACL layer, which will consume the data from upstream, converts the data and pushes to downstream context


## Domain

- This is the business problem space, where the software is tying to understand and solve
- For example if we are solving the problem for a retailer, the domain is 'Retail'
  - Inside that domain 'Retail' we have multiple business areas such as below. These are called as '**subdomains**'
    - Sales
    - Customer Management
    - Accounting
    - Inventory
    - Receiving
    - Fulfillment
- DDD classifies subdomains into three types
  - core domain - where the business differentiates itself and where you usually want your strongest modeling effort.
  - Supporting subdomain — necessary to support the core business, but not usually a key differentiator.
  - Generic subdomain — common capabilities that many businesses need, such as authentication or payroll.

## Model

- The model of a DDD is the solution to the specific problem
- The model usually represents an aspect of reality or something of interest
- The model is focused on the knowledge around a specific problem that is simplified and structured to provide a solution
- It is the simplified representation of the business concepts, rules and relationships that matter inside a particular domain or bounded context
- For example in Sales Context, the model might be (mportant part is the rules around them)
  - An Order must have at least one OrderLine.
  - A cancelled Order cannot be shipped.
  - A discount can only be applied when eligibility rules are satisfied.
  - An Order total is derived from its lines, taxes, and discounts.
 
## Building Blocks

- Entity : an object that is not defined by its attributes, but rather by its identity. Its state can change over time
