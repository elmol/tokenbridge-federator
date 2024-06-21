# Basic Federator Node Availability Monitoring and Alert System <!-- [short title of solved problem and solution] -->

* Status: draft  <!--[draft | proposed | rejected | accepted | deprecated | … | superseded by [ADR-0005](0005-example.md)] -->
* Date: YYYY-MM-DD <!-- [YYYY-MM-DD when the decision was last updated] -->

Technical Story: Implementing a basic system for monitoring the availability of the Federator node and setting up alerts to notify in case of downtime.  <!-- [description | ticket/issue URL] -->

## Context and Problem Statement

<!-- [Describe the context and problem statement, e.g., in free form using two to three sentences. You may want to articulate the problem in form of a question.] -->

Currently, there is no monitoring system in place to check the federator node's availability, and issues are only identified reactively. This lack of proactive monitoring results in delayed responses to downtime, impacting the quality and reliability of the service provided. How can be implemented a cost-effective and efficient system to monitor node availability and alert stakeholders promptly when issues arise?

### Technical Details

The Federator node is implemented using `Node.js` and relies on `RPC` for blockchain communication. Core logic is implemented in Typescript, enabling communication with the blockchain through JSON-RPC. The application is containerized using Docker and use docker-compose to integrate the application with a database, providing an isolated environment for deployment. Additionally, it includes endpoints for various functionalities, such as checking the status of the node as details below. 

* **<DOMAIN:PORT>/isAlive**
* **Method:**
  `GET`
* **Success Response:**
  * **Code:** 200 <br />
    **Content:** `{ "status" : "ok" }`

This status endpoint will be used to implement the health check system. The monitoring tool will periodically query this endpoint to ensure the node is available. 

## Decision Drivers 
<!-- [driver 1, e.g., a force, facing concern, …] -->
* The requirement to implement a `cost-effective` monitoring solution due to the project's non-priority status and the limited budget available.
* Prioritizing cost over the highest quality of monitoring is essential.
* The current lack of technical expertise with AWS necessitating a straightforward and easy-to-manage solution.

## Considered Options

* [option 1]
* [option 2]
* [option 3]
* … <!-- numbers of options can vary -->

## Decision Outcome

Chosen option: "[option 1]", because [justification. e.g., only option, which meets k.o. criterion decision driver | which resolves force force | … | comes out best (see below)].

### Positive Consequences <!-- optional -->

* [e.g., improvement of quality attribute satisfaction, follow-up decisions required, …]
* …

### Negative Consequences <!-- optional -->

* [e.g., compromising quality attribute, follow-up decisions required, …]
* …

## Pros and Cons of the Options <!-- optional -->

### [option 1]

[example | description | pointer to more information | …] <!-- optional -->

* Good, because [argument a]
* Good, because [argument b]
* Bad, because [argument c]
* … <!-- numbers of pros and cons can vary -->

### [option 2]

[example | description | pointer to more information | …] <!-- optional -->

* Good, because [argument a]
* Good, because [argument b]
* Bad, because [argument c]
* … <!-- numbers of pros and cons can vary -->

### [option 3]

[example | description | pointer to more information | …] <!-- optional -->

* Good, because [argument a]
* Good, because [argument b]
* Bad, because [argument c]
* … <!-- numbers of pros and cons can vary -->

## Links <!-- optional -->

* [Link type] [Link to ADR] <!-- example: Refined by [ADR-0005](0005-example.md) -->
* … <!-- numbers of links can vary -->

## Notes
Template from [the-madr-project](https://github.com/joelparkerhenderson/architecture-decision-record/blob/main/locales/en/templates/decision-record-template-of-the-madr-project/index.md)