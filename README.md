# BRCA EMT Network (TCGA + GEO) using CORNETO

## Phase 1 goal
Download and format two BRCA expression datasets:
- TCGA-BRCA expression matrix (genes x samples)
- GEO BRCA expression matrix (genes x samples)

Outputs (not committed if large):
- data/processed/tcga_brca_expression.tsv
- data/processed/geo_brca_expression.tsv

## Planned pipeline (high level)
1) Phase 1: Data acquisition + formatting (TCGA + GEO)
2) Phase 2: EMT scoring (KS + 76GS) + rank-average consensus
3) Phase 3: E / Hybrid / M groups
4) Phase 4: OmniPath directed + signed PKN
5) Phase 5: CORNETO inference + stability + cross-cohort replication
