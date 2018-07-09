---
layout: default
---

# JSON-LD Working Group Guiding Principles
{: .no_toc}

This document sets down the current guiding principles in use by the JSON-LD 1.1 Working Group to assist in making decisions about specification features. These guidelines provide a framework in which to have productive discussions that quickly come to consensus, rather than ending up blocked in an unresolvable tug-of-war over opposing and equally valid points of view. The principles are not meant to be interpreted as strict or objective rules, but instead as informative of the overall direction of the group to promote consistency and usability of the resulting specifications. 

This document is a *Living Document* and as such will change. Members of the group are encouraged to edit (e.g. to update, correct, etc.) the information. Comments about this document are welcome via issues and pull request on the [group’s “admin” repository](https://github.com/w3c/json-ld-wg/) or via emails sent to the group’s [`public-json-ld-wg@w3.org`](mailto:public-json-ld-wg@w3.org) e-mail list, using a subject prefix of <code>[Principles] …</code>.

**Table of Content**
* TOC
{:toc}

---

## Stay on target!

We follow our overall mission of making production and consumption of the JSON serialized data as easy as possible for the widest variety of developers, with or without any experience of any underlying graph models.

**Notes**

* The target audience is software developers generally, not just those that build browser-based applications.
* There may be a need to priotize between production of the JSON or consumption of the JSON, as clarified further below, but the intent is that solutions should be balanced as both producers and consumers are required for the ecosystem to be successful.
* JSON-centric or RDF-graph-centric need to be balanced as well, to ensure both usability and technical functionality

## Require real use cases, with actual instance data.

Features are supported by real world use cases, with actual data that can be referenced. This helps reduce entirely theoretical features that might be implemented in libraries, but never used in practice by producers or consumers.

**Notes**

* Use cases should be supporting material to provide rationale for decisions, and a teaching tool for when features might be useful. They are not a design requirements gathering tool, and the group is not starting from an empty slate.
* These use cases are collected on a wiki page, with the option of publishing a Note or integrating in to the specifications.

## Require at least two supporters for each use case.

As the mission is interoperability, having at least two supporters for each use case is important. If only one supporter can be found, then any features that it would require are likely too specific for inclusion in the proposed form.

**Notes**

* Any independent organization, group or individual can be a supporter, regardless of whether they are part of the Working Group, or even members of the W3C. Consortia or other standards organizations that represent many participants can thus fulfill this principle via their members.
* This is orthogonal to implementations of the specifications, which are required to exit Candidate Recommendation phase.

## As simple as possible, but no simpler.

A simpler solution (to understand, implement and use) is better than a more complex solution that accomplishes the same result.

## Consistency is simpler than exceptions.

Simplicity is considered in aggregate for the set of features defined by a specification, not independently.  If the same set of features can be accomplished by a smaller number of more consistent patterns, then that method is (very likely) simpler. Memorizing exceptions is harder than memorizing and applying rules.


`The WG discussed up to this point on 2018-07-06.`
<!-- Is there a {: .note} or similar? -->

## Proposed: Simplicity is determined by end users, not library implementers.

Simplicity (or usability) is determined by the target audience (data producers and consumers) based on their experience of understanding and applying the specification via existing implementations, not by the experience of implementers of the specification text directly. If there is a feature that makes it harder for implementations, but easier/better for end users, then that is a worthwhile trade off.

## Proposed: Provide on-ramps.

A solution that can be implemented in incremental stages is better than a
solution that is all or nothing, as not everyone needs every feature but
many people need various parts.

## Proposed: Define success, not failure.

We should define things in terms of what it means to be conformant, rather
than what is not conformant.  The fewer constraints we require, the easier
to have non-breaking changes in the future and the easier it is to have
experimentation.

## Proposed: Follow existing standards and best practices, where possible and where they do not conflict with other principles.

Between invention and reuse, pick reuse... unless that reuse would
demonstrably harm adoption by being more complicated than necessary.

## Proposed: The underlying data model is RDF.

If a feature comes up that can't be modeled with RDF as the underlying abstract data model, then we refer the feature to a future RDF Working Group for potential inclusion at that time. Similarly, we should ensure that the features of RDF are expressed in JSON-LD, to ensure that data can be round-tripped with confidence through different serializations.

**Notes**

* Objections: There is a more generic data model in JSON-LD, and we have the flexibility to add to it if we want to as long as we're not breaking backwards compatibility with JSON-LD 1.0. We don't want to box ourselves into a corner that will prevent us from thinking creatively about solutions.
