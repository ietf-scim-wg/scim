# SCIM Working Group Charter

## Charter

The System for Cross-domain Identity Management (SCIM) specifications define an
HTTP-based protocol (RFC 7644) and schema (RFC 7643) for provisioning and
managing identities across domains. Since their publication in 2015, SCIM has
become the dominant mechanism for cross-domain identity provisioning and has
seen broad adoption across enterprise, cloud, and consumer deployments.

The working group has since extended SCIM in three directions that shape the
work ahead. RFC 9865 introduced cursor-based pagination to address retrieval of
large result sets. RFC 9967 defined a profile for carrying SCIM provisioning
changes as Security Event Tokens (SETs), establishing an event-driven
alternative to polling. RFC 9944 defined device schema extensions, which
demonstrated that the SCIM resource model can be applied to identities that are
not people, and established a pattern for doing so. RFC 9865 and RFC 9967 update
RFC 7643 and RFC 7644.

The working group will continue to maintain and evolve SCIM toward its core
goal: managing identities across domains, reliably and interoperably, at scale.

A primary focus is improving the interoperability of SCIM implementations.
Optional features, under-specified behavior, and differing interpretations of
the specifications routinely require custom integration work, a cost that is
multiplied when one client provisions to many service providers. The working
group will reduce this through clarifications, profiles, registries, and better
capability discovery.

SCIM was originally designed to manage human identities. The working group will
determine how the existing resource model and protocol apply to non-human
identities — including devices, workloads, service accounts, and software agents
— building on the approach taken in RFC 9944, and will define schema extensions
where the core model proves insufficient. The working group will reuse the
existing protocol and resource model wherever possible rather than defining
parallel mechanisms for each identity type.

Revisions of RFC 7643 and RFC 7644 will remain backward compatible with deployed
SCIM 2.0 implementations. The working group will not define a new major protocol
version. Changes that cannot be made compatibly are out of scope unless
accompanied by a discovery and negotiation mechanism that allows existing
clients and service providers to continue to interoperate.

### Scope of work

The scope of work for the SCIM WG is:

* **Maintenance and revision of the core SCIM specifications** (RFC 7643 and
  RFC 7644), incorporating implementation experience, errata, interoperability
  feedback, and current security and privacy best practices. The revisions will
  incorporate the updates made by RFC 9865 and RFC 9967, and are intended for
  consideration at the Internet Standard level of specification maturity. The
  working group will produce the implementation and interoperability reports
  required to support that advancement.

* **Revision of RFC 7642** (use cases, definitions, and requirements) to reflect
  current deployment patterns, including pull- and push-based provisioning,
  event- and signal-driven coordination, deletion and deactivation, and
  provisioning of non-human identities.

* **Improving interoperability between SCIM implementations**, including:
  * Profiles that constrain optional features into a common, required baseline
    for particular deployment contexts
  * Clarifications to ambiguous or under-specified behavior in the core
    specifications, including PATCH semantics, filter support, error types and
    error semantics, idempotency and retry behavior, rate limiting, and bulk
    operations
  * Improved discovery of service provider capabilities, supported schemas,
    permitted attribute values, and mutability constraints

* **Establishment of IANA registries** for SCIM schema and extension URIs,
  resource types, service provider capability and feature identifiers, and error
  types, so that independently developed extensions are discoverable and do not
  collide.

* **Extensions to the SCIM protocol**, including:
  * Retrieval of large result sets and large multi-valued attributes, such as
    group memberships, at scale, building on RFC 9865
  * Incremental and delta retrieval of changes since a prior synchronization
    point
  * Asynchronous notification of resource changes and coordination of resources
    between domains, building on RFC 9967 and RFC 8417
  * Handling of deletion, deactivation, suspension, restoration, supersession,
    and other lifecycle states, for all SCIM resource types

* **Schema extensions for identity types and attributes not covered by the core
  schema**, including:
  * Non-human identities, such as workloads, service accounts, and software
    agents, following the pattern established by RFC 9944 for devices
  * Roles, entitlements, and other authorization-related attributes
  * Organizational and multi-tenant structures

* **Security and privacy considerations for cross-domain provisioning**,
  including authentication and authorization between SCIM clients and service
  providers, scoped and least-privilege access, tenant isolation, data
  minimization in schema design, handling of sensitive and regulated attributes,
  protection against bulk extraction of directory data through SCIM interfaces,
  and auditability of provisioning operations.

* **Profiling the relationship between SCIM and other identity-related protocols
  and frameworks**, such as OAuth 2.0, OpenID Connect, and the Shared Signals
  Framework, including how SCIM clients and service providers authenticate to
  each other and how SCIM provisioning state relates to session and credential
  lifecycle.

### Adoption criteria

Interest in extending SCIM substantially exceeds the working group's capacity.
The working group will adopt extension work only where there is a demonstrated
deployment need, documented implementation experience or committed implementers,
and no existing SCIM mechanism that already addresses the requirement.
Extensions must use the SCIM extension model and must not require incompatible
changes to the core protocol. Work that primarily serves a single vendor or a
single deployment is better pursued outside the working group.

### Out of scope

The following are out of scope for the working group:

* Authentication protocols, credential issuance, and authorization policy
  languages or decision protocols, except as needed to describe how SCIM
  interacts with them
* Identity proofing, verification, and assurance
* Defining new transport protocols other than HTTP, or new serializations other
  than JSON
* A replacement or general-purpose successor to LDAP or other directory access
  protocols
* A canonical human-resources or organizational data ontology beyond what
  provisioning interoperability requires
* Agent-to-agent communication, tool invocation, and agent capability
  description protocols; only the representation and lifecycle management of
  such identities is in scope

### Coordination

The working group will coordinate with other IETF working groups and external
organizations working on related identity and provisioning efforts to avoid
duplication and ensure compatibility. Within the IETF this includes the OAUTH,
SECEVENT, WIMSE, and HTTPAPI working groups. Externally this includes the
OpenID Foundation — in particular its Shared Signals and IPSIE working groups —
and the FIDO Alliance.

The working group also draws on implementation and interoperability feedback
from the independent SCIM implementer community, including interoperability
testing events and the materials at scim.cloud. All working group consensus is
determined on the scim@ietf.org mailing list.

### Working practices

Working group documents are developed on GitHub under
https://github.com/ietf-scim-wg. GitHub is used for issue tracking and editorial
collaboration; consensus is determined on the working group mailing list. The
working group will recharter or close once the chartered deliverables are
complete.
