# Phoenix Evergreen — verification and continuity protocol (v0.3.1)

This is a PUBLIC, READ-ONLY proof-of-concept record. This document is not evidence of asset ownership, wallet control, quantum hardware, or production uptime.

## Source of truth
- Public source: `phoenix-rebirth-v0.3/index.html`
- Prior version: `phoenix-rebirth-v0.2/index.html` (preserved)
- Blockchain links: third-party explorer leads, not independently authenticated consensus proof.
- Balance: **PENDING** until a public address is selected, a timestamped mainnet observation is recorded, and a separate source corroborates the same chain tip and UTXO set.
- Full ancestry: **PENDING** until transaction pagination, outspends, block anchors, deduplication, and completeness checks are performed.
- Ownership and rewards: **NOT ESTABLISHED** from public transaction visibility.

## Evergreen recovery sequence
1. Preserve original bytes and Git commit IDs. Never overwrite an earlier version.
2. Record a UTC timestamp, SHA-256, source URL, and retrieval status for each observation.
3. Use independent public mainnet-only sources for external verification. Never connect testnet or request private keys.
4. Test negative cases (malformed address, unavailable API, conflicting balances, chain reorganization, stale data).
5. Keep a bounded append-only evidence log; mark failures and pending checks explicitly.
6. Verify browser behavior, accessibility, hosting, and archival recovery before calling a release production-ready.
7. Maintain multiple independently retrievable copies, each periodically checked against known hashes; no claim of perpetual availability.

## Acceptance status
- Versioned public GitHub source: PASS (committed and fetched).
- Automated live transaction feed: PENDING.
- Verified wallet balance: PENDING.
- Independent security review: PENDING.
- Public hosted site: PENDING.
- Automated backups/recovery test: PENDING.

## Guardian policy
DEFAULT DENY. No signing, transfers, broadcasts, testnet, private key collection, unauthorized ownership claims, or unauthorized publishing of sensitive material.

**For Those Who Are Lost — Power for Imagination, Never Destruction.**
