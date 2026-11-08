# ARGOS Distribution

Public ARGOS binary releases and metadata-only feed-source catalogs.

- [Releases](https://github.com/ant0nX/argos-distribution/releases)
- [Existing Feed List Manager sources](catalog/feed-lists.v1.json) — 40 IP and 17 DNS source references (legacy catalog; unchanged)
- [Extended source candidates](catalog/extended-source-candidates.v1.json) — 39 additional metadata entries: 30 for GeoIP/ASN, TLS/JA3/JA4, malicious certificates, IPS rulesets, phishing/URL intelligence, hash lookup, and MISP/OTX exchange, plus **9 DNS ad/tracker blocking alternatives**.

## Ad / tracker source options (discovery only)

The extended catalog now includes HaGeZi Multi Light, Normal, PRO Mini and PRO; OISD Small and Big; 1Hosts Lite; AdAway mobile hosts; and Peter Lowe adservers. The existing AdGuard DNS filter is already in the legacy catalog, and the existing StevenBlack unified candidate embeds multiple upstream sources.

For a resource-conscious starting point, evaluate **HaGeZi PRO Mini**, **OISD Small**, or **1Hosts Lite** as alternatives. Choose only **one HaGeZi Multi tier**, and never stack OISD Small with its Big superset. These are broad ad/tracking lists, **not verified malware/C2 IoCs**. Overlap with AdGuard, StevenBlack, AdAway and Peter Lowe is substantial, and independently counting the same domain from aggregator sources would exaggerate reputation confidence.

No new DNS subscriptions were activated; the existing Feed List Manager UI does not yet read this extended catalog. Before any production import, validate exact DNS/Adblock exception semantics, false positives, provider attribution and source-license obligations (HaGeZi/OISD GPL-3.0, 1Hosts MPL-2.0, AdAway hosts CC BY 3.0; Peter Lowe provider terms require review). Provider domain-blocking cannot remove same-origin advertisements or cosmetic elements.

## Important distinctions

**Discovery is not activation.** Entries in the extended catalog are `discovery_only`, `activation_eligible=false` and `default_action=monitor`. A provider homepage, download URL or publicly available feed does **not** establish commercial/OEM rights, content authenticity, reliability, supported parser, or authorization to enable an IPS/TI Block. The extended file is **not yet loaded by the existing Pankratis IP/DNS-only Feed List Manager UI** and is **not a signed production feed manifest**.

Sources with `source_endpoint: null` have no verified stable direct automated download endpoint or use an account, API key, commercial grant, source index or separate adapter. Some entries represent documentation/source registries, not downloadable feeds.

The same source must not be treated as independent corroboration when mirrored by IPsum, FireHOL, Tor providers or different abuse.ch output formats. JA3/JA4 fingerprints, Tor exits, GeoIP country/ASN and generalized scanners are not independently sufficient malware indicators; rule families and certificate signals need a compatible detector and scoped policy.

Third-party IOC bodies, rule bundles and signatures are **not mirrored or repackaged** here. Fetching, parsing, rights verification, publication and enforcement must remain separate from displaying a candidate. See each provider's latest terms and attribution requirements.

For the future signed metadata registry, consult the Pankratis [public registry design](https://gitlab.com/antoni0s-group/argos-pankratis/-/blob/main/docs/specs/PUBLIC-THREAT-FEED-REGISTRY.md).
