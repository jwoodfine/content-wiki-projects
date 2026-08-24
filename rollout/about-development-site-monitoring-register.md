---
schema: foundry-doc-v1
title: "Development site monitoring register"
slug: about-development-site-monitoring-register
category: rollout
index_group: regions-and-tracking
type: topic
content_type: topic
quality: complete
short_description: "Passive tracking register holding qualified co-location sites removed from the active pipeline for adjacent land unavailability, kept scored with documented re-entry criteria."
status: stable
bcsc_class: current-fact
last_edited: 2026-08-24
editor: pointsav-engineering
language_protocol: PROSE-TOPIC
source_refs:
  - "bfe6fb6bbb557fd15bdb7ffd53bce60e527911eb7658c906df5b69813bdb8747"
paired_with: about-development-site-monitoring-register.es.md
cites: []
---

The **Development Site Monitoring Register** holds Primary Target locations that achieve a qualified co-location cluster score but cannot enter the active Development Site pipeline because adjacent land is not currently available for acquisition. The register is a scored inventory — not an inactive or archived list — updated on the same annual or biennial cadence as Primary Target sales per square foot data. Sites in the register retain their cluster score and demographic profile. They re-enter the active pipeline when adjacent land availability is confirmed through the real estate professional assessment process.

## Why land availability is a separate gate

A Primary Target that clears a qualifying tier — Local, District, or Regional, per the [[geographic-co-location-methodology|current tier system]] — has demonstrated the co-location and catchment conditions that Woodfine requires. A Fringe cluster does not qualify. The tier verifies that the commercial environment is correct for a Woodfine Building.

**Correction (2026-08-02), resolved (2026-08-24):** this section previously cited
a fabricated "T1 Valid ≥ 150" scoring threshold from a deprecated points-based
system (retired platform-wide 2026-05-16; see [[gis-cluster-scoring-glossary]]).
The register's actual re-entry test — a site must remain above the disqualifying
floor — is now stated directly against the current tier system: any tier other
than Fringe qualifies. This restates the register's original intent (a site
qualifies once it clears the lowest bar the tier system sets, not a specific
score) without asserting a score-to-tier mapping that does not exist in the
current pipeline.

Adjacent land availability is a separate condition. A site can have the correct co-location configuration and the correct demographic profile, but lack a parcel adjacent to the Primary Target that is available for acquisition at the time of assessment. This is particularly common in [[about-regional-markets-system|Regional Markets]] where the [[power-centres|Power Centre]] footprint has been fully developed and surrounding parcels are occupied by existing buildings whose owners are not current sellers.

The Monitoring Register preserves the investment made in scoring and profiling these sites rather than discarding them from the dataset. The site's qualifying cluster characteristics are not expected to change — the Primary Target is typically a large-format retailer with a long-term lease and substantial capital invested in the site. The probability that adjacent land will eventually become available is a function of normal commercial real estate turnover in the surrounding area.

## Update cadence and scoring maintenance

Monitoring Register sites are reviewed on the same schedule as the active pipeline: annually or biennially when Primary Target sales per square foot data is refreshed. At each update cycle, the real estate professionals engaged by Woodfine in the relevant market assess land availability for each Monitoring Register site in their area. A site where adjacent land has become available is escalated from the Monitoring Register to the active pipeline and advances to the [[transaction-summary-report-protocol|Transaction Summary Report]] stage.

The cluster tier for each Monitoring Register site is also reassessed at each update cycle, using the same methodology applied to the full Primary Target population. A site that was [[gis-cluster-scoring-glossary|District]] at initial assessment may be upgraded to Regional if a new anchor opens nearby and changes the cluster's composition, if updated catchment population data shifts its national percentile rank, or if a hospital within its civic ring is reclassified.

## Re-entry criteria

A Monitoring Register site re-enters the active Development Site pipeline when two conditions are satisfied:

1. **Land availability confirmed.** The real estate professional engaged in the market identifies a parcel adjacent to the Primary Target — defined as contiguous or immediately accessible to the Power Centre site — that is available for acquisition or ground lease at terms consistent with the applicable Direct-Hold Solution's underwriting parameters.

2. **Cluster tier maintained or improved.** The site's cluster tier at the time of the re-entry assessment must be Local, District, or Regional — not Fringe. A site that has fallen to Fringe — for example, because an anchor has closed and the cluster's composition no longer clears any tier's gates — does not re-enter the active pipeline until the qualifying co-location conditions are restored.

Sites that satisfy both conditions proceed to the Transaction Summary Report preparation and Independent Directors review process. The monitoring period has no defined maximum length: a site remains in the register until it meets both conditions, or until the co-location conditions deteriorate permanently (for example, permanent closure of the Primary Target), at which point the site is removed from the dataset entirely.

## Relationship to pipeline counts

Required development counts for each Direct-Hold Solution — 26 sites for Canada, 52 for the United States, 26 for Mexico — are based on active pipeline sites only. Monitoring Register sites are not counted toward the required development total. The 2:1 minimum shortlist ratio applies to active pipeline sites; the Monitoring Register is a reserve of future pipeline candidates, not a component of the current shortlist calculation.
