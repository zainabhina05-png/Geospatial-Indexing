# Geospatial-Indexing
This extends a real production fix — a Haversine-formula distance-radius venue filter I shipped in WorkSphere PR #1962. That filter works but scans every venue on every query (brute-force). This repo investigates whether a k-d tree index gets the same correct results faster at scale.
