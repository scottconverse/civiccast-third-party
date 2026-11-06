# CivicCast third-party assets

Exact copies of third-party files that [CivicCast](https://github.com/scottconverse/civiccast-native) builds depend on, kept here so a build never breaks when an upstream site moves or deletes a file.

**Rules for this repository:**

- Files are byte-for-byte copies of the upstream originals. Nothing here is modified or rebuilt.
- Each set is a GitHub release with its own tag, holding the files, a `SHA256SUMS.txt`, and the upstream license.
- A release is never edited or deleted once CivicCast code points at it. A new upstream version gets a new release with a new tag.
- CivicCast verifies every file against the size and SHA-256 pinned in its own source before using it. A copy here that doesn't match is refused.

## Sets

| Release | What | Upstream source | License |
|---|---|---|---|
| [`whistle-3.1.0`](https://github.com/scottconverse/civiccast-third-party/releases/tag/whistle-3.1.0) | Whistle live-caption model (`whistle.cact`) and the cactus-needle 3.1.0 Windows wheel that carries its engine library (`needle/libneedle3.dll`) | Hugging Face `Cactus-Compute/whistle` @ `ad73f1468dd5203791e0cc81d31544c553563645`; `Cactus-Compute/needle3` @ `d6c7d6a2e9655505e0f8e23339356dd1705900eb` | Apache-2.0 (Cactus Compute) |

### whistle-3.1.0

| File | Bytes | SHA-256 |
|---|---|---|
| `whistle.cact` | 16,919,407 | `b6e02f048568ac5d01a2042556c658061e699acbc0aa2a1439f52f3d461dffeb` |
| `cactus_needle-3.1.0-py3-none-win_amd64.whl` | 683,889 | `4f5fc86abfc50d551cdb237a34b501f36d82d4b6f5911ee7bec4e9532d44dd95` |
| `LICENSE-whistle.txt`, `LICENSE-needle3.txt` | 11,358 each | `cfc7749b96f63bd31c3c42b5c471bf756814053e847c10f3eb003417bc523d30` |

Why it exists: on 2026-11-05 upstream removed the `python/` folder from `Cactus-Compute/needle3`'s `main` branch, and CivicCast builds that fetched `resolve/main/…` failed with HTTP 404. These copies were taken from the upstream revisions above and checked against CivicCast's pinned checksums before upload.

The files are © Cactus Compute and licensed under the Apache License 2.0; see the license files in each release. This repository's own text is also Apache-2.0.
