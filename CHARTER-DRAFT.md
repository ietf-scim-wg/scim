# SCIM Working Group Charter

## Charter

The System for Cross-domain Identity Management (SCIM) specifications define an HTTP-based protocol (RFC 7644) and schema (RFC 7643) for provisioning and managing identities across domains. Since their publication in 2015, SCIM has become the dominant mechanism for cross-domain identity provisioning and has seen broad adoption across enterprise, cloud, and consumer deployments.

The working group has since extended SCIM in three directions that shape the work ahead. RFC 9865 introduced cursor-based pagination to address retrieval of large result sets. RFC 9967 defined a profile for carrying SCIM provisioning changes as Security Event Tokens (SETs), establishing an event-driven alternative to polling. RFC 9944 defined device schema extensions, which demonstrated that the SCIM resource model can be applied to identities that are not people, and established a pattern for doing so. RFC 9865 and RFC 9967 update RFC 7643 and RFC 7644.

The working group will continue to maintain and evolve SCIM toward its core goal: managing identities across domains, reliably and interoperably, at scale.

A primary focus is improving the interoperability of SCIM implementations. Optional features and differing interpretations of the specifications often require custom integration work, a cost that is multiplied when one client provisions to many service providers. The working group will reduce this through clarifications, profiles, and better capability discovery.

SCIM was originally designed for human identities. Its scope includes non-human identities, such as devices, workloads, and software agents, managed using the same protocol and resource model wherever possible.

### Scope of work

The scope of work for the SCIM WG is:

* Maintenance and revision of the core SCIM specifications (schema, and protocol), incorporating implementation experience, errata, interoperability feedback, and current security best practices
* Improving interoperability between SCIM implementations, including:
    * Profiles that constrain optional features into a common, required baseline for particular deployment contexts
    * Clarifications to ambiguous or under-specified behavior in the core specifications
    * Improved discovery of service provider capabilities, schemas, and permitted attribute values
* Extensions to the SCIM protocol, including:
    * Retrieval of large result sets and large multi-valued attributes, such as group memberships, at scale
    * Asynchronous notification of resource changes and coordination of resources between domains
    * Handling of deletion, deactivation, and other account lifecycle states
* Schema extensions for identity types and attributes not covered by the core schema, including:
    * Non-human identities, such as devices, workloads, and agents
    * Roles, entitlements, and other authorization-related attributes
    * Organizational and multi-tenant structures
* Profiling the relationship between SCIM and other identity-related protocols and frameworks, such as OAuth 2.0, OpenID Connect, and the Shared Signals Framework, including how SCIM clients and service providers authenticate to each other

The following are out of scope for the working group:

* Authentication protocols, credential issuance, and authorization policy languages, except as needed to describe how SCIM interacts with them
* Defining new transport protocols other than HTTP

The working group will coordinate with other IETF working groups and external organizations working on related identity and provisioning efforts, such as the OAuth and SECEVENT working groups, the OpenID Foundation, and the FIDO Alliance, to avoid duplication and ensure compatibility.
