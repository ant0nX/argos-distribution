# ARGOS Distribution

Public ARGOS binary releases and metadata-only feed-source catalogs.

- [Releases](https://github.com/ant0nX/argos-distribution/releases)
- [Single canonical Feed List Manager registry](catalog/feed-lists.v1.json) — 40 supported IP references, 17 published DNS references, 45 discovery-only candidates and 87 domain taxonomy options. The Pankratis firmware's current preinstalled UCI defaults include 13 of the published DNS feeds; registry presence alone never installs the other 4.
- The old [extended list](catalog/extended-source-candidates.v1.json) is **deprecated** and only points to the canonical catalog; it is not a second feed registry.

## Ad / tracker source options (discovery only)

The canonical catalog's read-only source candidates include HaGeZi Multi Light, Normal, PRO Mini and PRO; OISD Small and Big; 1Hosts Lite; AdAway mobile hosts; and Peter Lowe adservers. The existing AdGuard DNS filter is already in the supported DNS catalog, and the existing StevenBlack unified candidate embeds multiple upstream sources.

For a resource-conscious starting point, evaluate **HaGeZi PRO Mini**, **OISD Small**, or **1Hosts Lite** as alternatives. Choose only **one HaGeZi Multi tier**, and never stack OISD Small with its Big superset. These are broad ad/tracking lists, **not verified malware/C2 IoCs**. Overlap with AdGuard, StevenBlack, AdAway and Peter Lowe is substantial, and independently counting the same domain from aggregator sources would exaggerate reputation confidence.

No new DNS subscriptions were activated. The Pankratis Feed List Manager source revision 19058e9 now displays all 45 candidates as **read-only, not installed**, with family/provider/format filters. Only source-specific adapter qualification and operator approval can make them usable. Before any production import, validate exact DNS/Adblock exception semantics, false positives, provider attribution and source-license obligations (HaGeZi/OISD GPL-3.0, 1Hosts MPL-2.0, AdAway hosts CC BY 3.0; Peter Lowe provider terms require review). Provider domain-blocking cannot remove same-origin advertisements or cosmetic elements.

## Domain categories — offline enrichment, not DNS blocking

- [Domain-category source inventory](catalog/domain-category-enrichment.v1.json) — current and proposed sources, topic versus risk evidence roles, taxonomy mapping and source-rights gates. Six sources are already used by the separate site-rating-app for discovery/evidence (including UT1, Block List Project, Wikidata, domain-list-community, and ranking-only Cloudflare Radar/Tranco); do **not** count them as six new independent sources.
- Newly listed candidates: **Curlie** human-curated TSV site-topic directory (CC BY 3.0 with attribution), **ROR** verified research institution websites (CC0), **OpenAlex** institutions (CC0, often dependent on ROR), **Cloudflare domain categories** (API/rights need review), **IAB Content Taxonomy 3.1** (vocabulary only; not domain labels) and **OpenStreetMap** website/business tags (ODbL review).

These are **candidate inputs to the offline domain rating pipeline**, not live DNS downloads, signed ARGDOM3 updates, or automatic TI/IPS Block policies. Current catalog integration is metadata-only; existing categories are not overwritten. Map to the Pankratis's stable category taxonomy after domain/host-path validation, independent evidence checks, origin/provenance, license compliance and calibration. Ad/tracker or malware blocklists generally express a specific *function or risk*, **not necessarily the primary business/content category of the website**. Ranking lists (Cloudflare/Tranco) prioritize investigation but never establish a category.

## Important distinctions

**Discovery is not activation.** Entries in the canonical registry's source_candidates field are `discovery_only`, `activation_eligible=false` and `default_action=monitor`. A provider homepage, download URL or publicly available feed does **not** establish commercial/OEM rights, content authenticity, reliability, supported parser, or authorization to enable an IPS/TI Block. The Feed List Manager shows candidate metadata offline, but it cannot download or activate those candidates. The GitHub file is **not a signed production feed manifest**.

Sources with `source_endpoint: null` have no verified stable direct automated download endpoint or use an account, API key, commercial grant, source index or separate adapter. Some entries represent documentation/source registries, not downloadable feeds.

The same source must not be treated as independent corroboration when mirrored by IPsum, FireHOL, Tor providers or different abuse.ch output formats. JA3/JA4 fingerprints, Tor exits, GeoIP country/ASN and generalized scanners are not independently sufficient malware indicators; rule families and certificate signals need a compatible detector and scoped policy.

Third-party IOC bodies, rule bundles and signatures are **not mirrored or repackaged** here. Fetching, parsing, rights verification, publication and enforcement must remain separate from displaying a candidate. See each provider's latest terms and attribution requirements.

For the future signed metadata registry, consult the Pankratis [public registry design](https://gitlab.com/antoni0s-group/argos-pankratis/-/blob/main/docs/specs/PUBLIC-THREAT-FEED-REGISTRY.md).
