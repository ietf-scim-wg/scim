# SCIM Working Group Charter

## Charter

The System for Cross-domain Identity Management (SCIM) specifications define an HTTP-based protocol (RFC 7644) and schema (RFC 7643) for provisioning and managing identities across domains. Since their publication in 2015, SCIM has become the dominant mechanism for cross-domain identity provisioning and has seen broad adoption across enterprise, cloud, and consumer deployments.

The working group has since extended SCIM in three directions that shape the work ahead. RFC 9865 introduced cursor-based pagination to address retrieval of large result sets. RFC 9967 defined a profile for carrying SCIM provisioning changes as Security Event Tokens (SETs), establishing an event-driven alternative to polling. RFC 9944 defined device schema extensions, which demonstrated that the SCIM resource model can be applied to identities that are not people, and established a pattern for doing so. RFC 9865 and RFC 9967 update RFC 7643 and RFC 7644.

The working group will continue to maintain and evolve SCIM toward its core goal: managing identities across domains, reliably and interoperably, at scale.

A primary focus is improving the interoperability of SCIM implementations. Optional features, under-specified behavior, and differing interpretations of the specifications routinely require custom integration work, a cost that is multiplied when one client provisions to many service providers. The working group will reduce this through clarifications, profiles, registries, and better capability discovery.

SCIM was originally designed to manage human identities. The working group will determine how the existing resource model and protocol apply to non-human identities — including devices, workloads, service accounts, and software agents — building on the approach taken in RFC 9944, and will define schema extensions where the core model proves insufficient. The working group will reuse the existing protocol and resource model wherever possible rather than defining parallel mechanisms for each identity type.

Revisions of RFC 7643 and RFC 7644 will remain backward compatible with deployed SCIM 2.0 implementations. The working group will not define a new major protocol version. Changes that cannot be made compatibly are out of scope unless accompanied by a discovery and negotiation mechanism that allows existing clients and service providers to continue to interoperate.

### Scope of work

The scope of work for the SCIM WG is:

* **Maintenance and revision of the core SCIM specifications** (RFC 7643 and RFC 7644), incorporating implementation experience, errata, interoperability feedback, and current security and privacy best practices. The revisions will incorporate the updates made by RFC 9865 and RFC 9967, and are intended for consideration at the Internet Standard level of specification maturity. The working group will produce the implementation and interoperability reports required to support that advancement.
* **Revision of RFC 7642** (use cases, definitions, and requirements) to reflect current deployment patterns, including pull- and push-based provisioning, event- and signal-driven coordination, deletion and deactivation, and provisioning of non-human identities.
* **Improving interoperability between SCIM implementations**, including:
    * Profiles that constrain optional features into a common, required baseline for particular deployment contexts
    * Clarifications to ambiguous or under-specified behavior in the core specifications, including PATCH semantics, filter support, error types and error semantics, idempotency and retry behavior, rate limiting, and bulk operations
    * Improved discovery of service provider capabilities, supported schemas, permitted attribute values, and mutability constraints
* **Establishment of IANA registries** for SCIM schema and extension URIs, resource types, service provider capability and feature identifiers, and error types, so that independently developed extensions are discoverable and do not collide.
* **Extensions to the SCIM protocol**, including:
    * Retrieval of large result sets and large multi-valued attributes, such as group memberships, at scale, building on RFC 9865
    * Incremental and delta retrieval of changes since a prior synchronization point
    * Asynchronous notification of resource changes and coordination of resources between domains, building on RFC 9967 and RFC 8417
    * Handling of deletion, deactivation, suspension, restoration, supersession, and other lifecycle states, for all SCIM resource types
* **Schema extensions for identity types and attributes not covered by the core schema**, including:
    * Non-human identities, such as workloads, service accounts, and software agents, following the pattern established by RFC 9944 for devices
    * Roles, entitlements, and other authorization-related attributes
    * Organizational and multi-tenant structures
* Profiling the relationship between SCIM and other identity-related protocols and frameworks, such as OAuth 2.0, OpenID Connect, and the Shared Signals Framework, including how SCIM clients and service providers authenticate to each other

The following are out of scope for the working group:

* Authentication protocols, credential issuance, and authorization policy languages, except as needed to describe how SCIM interacts with them
* Defining new transport protocols other than HTTP

The working group will coordinate with other IETF working groups and external organizations working on related identity and provisioning efforts, such as the OAuth and SECEVENT working groups, the OpenID Foundation, and the FIDO Alliance, to avoid duplication and ensure compatibility.
