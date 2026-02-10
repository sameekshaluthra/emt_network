
## Project: BRCA EMT network inference with CORNETO

### Aim
Infer a compact, signed and directed regulatory subnetwork associated with EMT in breast cancer (BRCA), and test whether the inferred network is consistent across two independent cohorts.

### Data
- TCGA BRCA (expression)
- GEO: GSE96058 (expression)

### Methods
1. **EMT scoring per sample**
   - KS score (epithelial vs mesenchymal gene sets)
   - 76GS score (correlation-weighted EMT signature)
2. **EMT contrast signature (M vs E)**
   - Samples were ranked by a consensus EMT rank.
   - Extreme groups (E vs M) were compared to compute gene-wise log fold change (logFC).
3. **Prior knowledge network (PKN)**
   - OmniPath interactions filtered to **directed** and **signed** edges (+1 stimulation, −1 inhibition).
4. **Network inference (CORNETO)**
   - CORNETO PCST-style inference on the full signed+directed OmniPath PKN using |logFC| as node weights.
   - Subnetworks were inferred independently for TCGA and GEO, then compared.

### Outputs
- `results/tcga_pcst_subnetwork.tsv`
- `results/geo_pcst_subnetwork.tsv`
- `results/network_overlap_summary.txt`

### Key result (cross-cohort agreement)
- TCGA subnetwork: 36 nodes (induced edges: 75)
- GEO subnetwork: 41 nodes (induced edges: 96)
- Shared nodes: 32 (**~71% overlap**)
- Shared edges: 65 (**~61% overlap**)
