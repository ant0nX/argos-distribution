# ARGOS Distribution

Official public distribution repository for ARGOS signatures and feeds.

## Packages

- **argos-signatures** — Versioned DNS, OUI and port-service signature databases.
- **argos-feeds** — Versioned security and threat-intelligence feeds.

## Feed source catalog

- [Feed List Manager catalog (JSON v1)](catalog/feed-lists.v1.json) — current metadata inventory of 40 built-in IP/CIDR sources and 13 built-in DNS/domain sources.
- Each built-in IP/DNS feed has a **default category** and a concise purpose. DNS category assignments use stable **`category_id` values from the packaged ARGOS Site Rating DNS/Web taxonomy**, rather than unrelated display labels. The `category_options.dns` array lists canonical IDs and labels; local overrides take precedence unless a consumer-specific override already exists.
- Sources for which the current taxonomy lacks a corresponding category, including Fake News and Piracy, explicitly default to `unknown` (their original `source_topic` remains visible); they are **not** silently mapped into News or another unrelated category. IP source categories remain distinct threat-intelligence metadata, not per-category enforcement.
- Catalog entries describe provider links, intended use and provider-terms notes; **they do not include or redistribute third-party list contents**.
- The Pankratis UI exposes this catalog under **Signatures → Feed List Manager**. On-router UCI selections and the installed firmware remain authoritative; the public JSON is not an automatically applied policy, updater feed or signed package.
- Provider permissions, commercial/OEM licensing, availability and rate limits must be verified before downloading or redistributing any source data.

## Releases

Validated distribution artifacts are published under [GitHub Releases](https://github.com/ant0nX/argos-distribution/releases).

Each release may include version information, a manifest and SHA-256 checksums.

## Source

Development and validation are maintained separately.
