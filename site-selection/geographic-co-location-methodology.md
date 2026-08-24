---
schema: foundry-doc-v1
title: "Geographic co-location methodology"
slug: geographic-co-location-methodology
category: site-selection
index_group: scoring-and-clustering
type: topic
content_type: topic
quality: complete
short_description: "Five-degree cluster system scoring retail node proximity from Primary, Secondary, and Tertiary target co-occurrence to rank development sites by anchor strength."
status: stable
bcsc_class: current-fact
last_edited: 2026-07-11
editor: pointsav-engineering
language_protocol: PROSE-TOPIC
source_refs:
  - "bfe6fb6bbb557fd15bdb7ffd53bce60e527911eb7658c906df5b69813bdb8747"
paired_with: geographic-co-location-methodology.es.md
cites: []
---

The **Geographic Co-Location Methodology** is the spatial analysis discipline MCorp applies to identify and rank potential Development Sites across its three primary jurisdictions. The methodology scores retail nodes by the proximity and combination of anchor retailers operating in the geography, producing a ranked dataset of sites in which development investment is validated by the demonstrable commercial commitments of institutional retailers rather than by speculative demographic projections.

**Correction (2026-08-02):** "three primary jurisdictions" contradicts this
article's own "Required Site Count by Jurisdiction" table below (which lists only
Canada/US/Mexico, omitting Spain) and, more consequentially, contradicts the sibling
article [[power-centre-co-location-thesis]] (same `last_edited` date, 2026-07-11):
"The Power Centre co-location requirement applies consistently across all **four**
qualified jurisdictions: Canada, the United States, Spain, and Mexico." The
four-jurisdiction, Spain-inclusive version is also the one consistent with
[[location-intelligence-strategy]]'s detailed coverage plan and the JOURNAL working
paper's inclusion of Spain (MITMA data, 58 clusters). This article is the outlier.
**Flagged, not resolved.**

The methodology produces five cluster degrees, each representing a more refined level of anchor co-occurrence. Higher-degree clusters indicate that a geography has attracted multiple categories of institutional commercial investment — a compound validation of market conditions that exceeds the threshold any single anchor produces alone.

## The Five-Degree Cluster System

**Correction (2026-08-02):** this name collides with a differently-defined "Five-
Degree Framework" in the JOURNAL working paper
[[geometric-site-selection-national-tenancy]] §4.3, which defines its own 1st degree
as "Primary anchor only... maps approximately to T3" — no secondary anchor required
until the 2nd degree, unlike this article's First-Degree definition below (which
requires a secondary anchor at the very first rung). Same name, same "Degree"
vocabulary, same tertiary-proximity threshold, but genuinely different admission
rules at each rung — neither article acknowledges the other. **Flagged, not
resolved.**

The five cluster degrees are constructed from two radius thresholds: a tighter threshold applied to Primary and Secondary Target co-occurrence, and a wider threshold applied to Tertiary Target proximity. Each degree builds on the prior.

### First- and second-degree clusters

**First-Degree Cluster** — A [[co-location-target-hierarchy|Primary Target]] site (Walmart Supercentre) with either of the two Secondary Targets (Home Depot or Costco Wholesale) located within the Primary-Secondary proximity threshold of each other. This is the baseline Qualified Investment indicator: the co-presence of a volume grocery operator and a major home improvement or membership warehouse operator at that proximity confirms that the geography meets the site thresholds of two institutionally distinct retail operators.

**Second-Degree Cluster** — A First-Degree Cluster with either Tertiary Target (a post-secondary institution or a major medical centre) located within the wider Tertiary proximity threshold. The addition of a Tertiary Target introduces a demand source for professional services tenancy that is structurally independent of the retail node — a university or hospital draws professional staff, patient populations, and academic visitors who represent the primary target tenant base for Woodfine Professional Centres.

### Third- and fourth-degree clusters

**Third-Degree Cluster** — A Primary Target with both Secondary Targets (Home Depot and Costco) within the Primary-Secondary proximity threshold of each other. The requirement that both secondary operators be present at that same tight radius is a materially higher bar than the First-Degree standard. Home Depot and Costco independently validate a geography through their own site selection processes; their simultaneous presence confirms that multiple institutional operators have evaluated the same geography against their independent criteria and reached the same conclusion.

**Fourth-Degree Cluster** — A Third-Degree Cluster with either Tertiary Target within the wider Tertiary proximity threshold. The combination of both secondary operators plus an institutional tertiary demand source represents a geography in which retail, professional, and institutional activities have converged.

### Fifth-degree clusters as highest-conviction sites

**Fifth-Degree Cluster** — A Third-Degree Cluster with both Tertiary Targets within the wider Tertiary proximity threshold. Fifth-Degree Clusters are the highest-conviction sites in the dataset. The simultaneous presence of Walmart, Home Depot, Costco, a post-secondary institution, and a major medical centre within the respective radius thresholds marks a geography that has independently attracted five categories of institutional commercial commitment.

## Radius Calibration

The Primary-Secondary threshold reflects the operational reality of [[power-centres|power centre]] site design: retailers in the same commercial node or corridor are typically clustered close together, and proximity at that scale confirms shared site infrastructure rather than coincidental geographical proximity. The wider Tertiary threshold reflects the broader catchment pattern of institutional employers. A university or major hospital does not anchor a power centre — it anchors a geography, at a scale consistent with the drive-time tolerance of professional services tenants in a [[about-regional-markets-system|Regional Market]] context.

### Periodic recalibration

If Fifth-Degree Clusters come to represent an outsized share of all Primary Target entries in the full dataset, the thresholds are tightened — both the Tertiary and the Primary-Secondary proximity thresholds are reduced. This recalibration mechanism prevents the top cluster tier from becoming too large to be operationally useful as a site selection filter.

## Dataset Output Metrics

For each Primary Target entry, the geographic co-location output records: the city, town, or municipality of the Primary Target; the population of the surrounding community; the sales per square foot of the Primary Target; and the global ranking of that Primary Target by sales per square foot across all Primary Target entries in the dataset. No additional demographic categories are included in the geographic co-location output — demographic profiling is a separate analytical step addressed by the [[optimum-mosaic-demographic-profiling|Optimum Mosaic methodology]].

### Ranking and shortlist production

The output is then ranked to balance cluster degree, Primary-Secondary co-occurrence, and the absolute sales per square foot of the Primary Target. The ranking produces the site shortlist from which Woodfine engages real estate professionals in each identified market to assess land availability and development timeline.

## Required Site Count by Jurisdiction

The site shortlist requirements are calibrated to the planned capital raises and construction timelines of each Direct-Hold Solution, with a jurisdiction-specific required development count set for Canada, the United States, and Mexico across the equity and debt financings planned over the multi-year build-out.

### Shortlist ratio and land availability

Because not every high-ranked Primary Target will have available land adjacent to its site, and some available sites will carry rezoning or permitting timelines extending three to seven years, the site shortlist must exceed the required development count by a substantial margin. Enough shortlisted candidates are carried per required site to absorb land-availability and entitlement attrition.

Three separate datasets are maintained, one per jurisdiction, reflecting the distinct retail landscapes of Canada, the United States, and Mexico.
