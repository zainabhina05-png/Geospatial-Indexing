# Geospatial Indexing: From Brute-Force Haversine to K-D Tree

**Status:** 🚧 In progress — Week of Aug 7, 2026

## Why this exists

This extends a real production fix — a Haversine-formula distance-radius venue
filter I shipped in [WorkSphere PR #1962](https://github.com/SatyamPandey-07/WorkSphere/pull/1962).
That filter works but scans every venue on every query (brute-force). This repo
investigates whether a k-d tree index gets the same correct results faster at scale.

## The paper

**"Approximate K-Nearest Neighbour Based Spatial Clustering Using K-D Tree"**
(arXiv:1303.1951) — [link](https://arxiv.org/pdf/1303.1951)

Background reference: Bentley, J.L. (1975), *"Multidimensional Binary Search
Trees Used for Associative Searching"* — the original k-d tree paper.

## Summary (fill in after reading — 5 bullets, plain English)

- **Problem:** _[what's slow/broken about brute-force nearest-neighbor search on spatial data?]_
- **Approach:** _[how does a k-d tree partition space to avoid checking every point?]_
- **Why it matters:** _[what's the practical win — for you, specifically: query time on WorkSphere's venue list as it grows]_
- **Key mechanism:** _[how does the tree get built + how does a range/nearest query walk it? one sentence each]_
- **Expected result:** _[what does the paper claim/show — big-O or benchmark numbers]_

## Plan

- [-] Day 1-2: Read paper, fill in summary above
- [ ] Day 3-5: Implement a minimal k-d tree in TypeScript (`src/kdtree.ts`), reuse Haversine for actual distance calc at leaf level
- [ ] Day 5-6: Benchmark k-d tree vs brute-force on synthetic venue data (`src/benchmark.ts`)
- [ ] Day 6-7: Write up results below + short dev.to post

## Benchmark results

_[table goes here once Day 5-6 is done]_

## What I'd do next

_[one paragraph — where would this go in a real production system]_
