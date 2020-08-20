# crypto_field_stats_tests
Empirical analysis of uniformity/randomness/whatever of all fields

## Scope

Every field in a transaction falls into one of four buckets:
1. Signer-selected, expected to be non-uniform across transactions (e.g. unlock time)
2. Descriptive, expected to be non-uniform acrosss all transactions (e.g. transaction version)
3. Signer-selected, expected to be uniform across transactions (e.g. MLSAG/CLSAG scalars)
4. Function output, expected to be uniform across all transactions (e.g. public keys)

**In this repository, we will analyze the on-chain data for non-uniformity in types #3 and #4.** This repository is _not_ exploring non-uniformity in types #1 and #2 (see [Noncesense](https://github.com/noncesense-research-lab/) for those studies)

## Notes
Things to look for:
- Unexpectedly frequent collisions
- Nonuniformity
- Low entropy
- (what else ??)

## Example

