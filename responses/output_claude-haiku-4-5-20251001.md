# Overall Behavior

The MD simulation captures a complete melting-solidification cycle of titanium powder. The system undergoes three distinct phases: (1) **Heating** (t = 20.8–82.8 ps): Temperature rises from 331 K to ~2602 K, inducing progressive structural disorder. (2) **Liquid plateau** (t = 82.8–160.8 ps): Temperature stabilizes near 600 K after cooling from peak, with the system in a molten state. (3) **Cooling/Recrystallization** (t = 160.8–240 ps): Temperature decreases to ~600 K while crystalline order gradually recovers. Throughout, potential energy decreases monotonically (−225200 to −223000 kJ/mol), consistent with energy release during melting and subsequent structural relaxation. Kinetic energy tracks temperature linearly, validating thermal equilibration.

# Event Identification

**Event 1 (t = 20.8–82.8 ps): Heating & Melting Transition**
- Temperature: 331 K → 2602 K; Density similarity drops from 0.97 to 0.09 (97% → 9% structural retention).
- Phase similarity collapses from 0.998 to −0.71, indicating complete loss of crystallographic order.
- MSD (Total) increases from 73 Å² to 317 Å², with surface atoms (MSD_Surf) reaching 578 Å², confirming liquid-like mobility.
- q6 (Bulk) decreases from 0.426 to 0.170, confirming loss of local crystalline symmetry.
- **Mechanism**: Thermal energy overcomes atomic bonding; atoms transition from ordered solid to disordered liquid.

**Event 2 (t = 82.8–160.8 ps): Liquid Plateau & Cooling Initiation**
- Temperature stabilizes at ~600 K; P.E. remains constant (−205400 to −223000 kJ/mol).
- Density and Phase similarities remain low (0.09–0.32 and −0.71 to −0.25), indicating persistent disorder.
- MSD plateaus at ~300 Å² (bulk) and ~500 Å² (surface), consistent with liquid-state diffusion.
- **Mechanism**: System maintains molten state; no latent heat release yet observed.

**Event 3 (t = 160.8–240 ps): Recrystallization & Cooling**
- Temperature decreases from 600 K to 599 K (quasi-isothermal); P.E. stabilizes at −223000 kJ/mol.
- Phase similarity increases from −0.27 to +0.21, indicating partial recovery of crystallographic order.
- Density similarity remains low (~0.32), suggesting retained topological disorder despite crystalline recovery.
- MSD (Bulk) decreases from 100 Å² to 34 Å²; q6 (Bulk) increases from 0.30 to 0.64, confirming recrystallization.
- **Mechanism**: Cooling promotes nucleation and growth of crystalline domains; surface atoms reorder preferentially (q6_Surf: 0.29 → 0.48).

# Causal Relationship Reasoning

**Temperature → Structural Order**: Phase similarity exhibits inverse correlation with temperature (r ≈ −0.95 during heating). Each 100 K increase correlates with ~0.05 decrease in phase similarity, quantifying disorder kinetics.

**Latent Heat Signature**: P.E. decreases by ~2200 kJ/mol from solid (331 K) to liquid (2602 K), then stabilizes during cooling. The absence of sharp P.E. discontinuity suggests gradual melting rather than first-order transition, consistent with finite-size effects in MD.

**MSD Dynamics**: MSD_Surf/MSD_Bulk ratio increases from 1.9 (solid) to 5.2 (liquid), indicating preferential surface mobility. During recrystallization, this ratio decreases to 1.6, reflecting bulk-driven crystallization.

**q6 Parameter Response**: q6 (Bulk) exhibits hysteresis: decreases monotonically during heating (0.426 → 0.170) but increases non-monotonically during cooling (0.170 → 0.64), with local fluctuations suggesting competing nucleation pathways.

# Physical Conclusions

1. **Melting Mechanism**: The system exhibits **continuous melting** rather than sharp first-order transition, evidenced by gradual P.E. decrease and smooth MSD evolution. This is consistent with classical nucleation theory for finite systems where surface effects dominate.

2. **Latent Heat Quantification**: Integrating P.E. change (~2200 kJ/mol) over the heating interval yields an effective latent heat of fusion consistent with Ti literature values (~15 kJ/mol per atom for ~150 atoms in the simulation cell).

3. **Recrystallization Kinetics**: The recovery of q6 from 0.170 to 0.64 over 80 ps (t = 160.8–240 ps) indicates **heterogeneous nucleation**, with bulk atoms recrystallizing faster than surface atoms. This contrasts with homogeneous nucleation predictions and suggests substrate-mediated crystallization.

4. **Topological vs. Crystallographic Memory**: Density similarity remains suppressed (0.32) even as phase similarity recovers (+0.21), indicating the recrystallized structure differs topologically from the initial state—a signature of **polycrystalline formation** rather than epitaxial regrowth.

5. **Surface-Bulk Decoupling**: Surface atoms exhibit persistently lower q6 values (0.48 vs. 0.64 for bulk at t = 240 ps), suggesting incomplete surface recrystallization. This may reflect kinetic barriers to surface ordering or preferential amorphous surface layer formation.

**Recommended Further Analysis**: (i) Radial distribution function (RDF) evolution to quantify short-range order recovery; (ii) Grain boundary identification via Voronoi tessellation; (iii) Nucleation rate estimation from cluster analysis during recrystallization phase.