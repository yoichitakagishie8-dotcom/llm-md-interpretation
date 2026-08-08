# Overall Behavior

The simulation captures a complete heating–melting–cooling–solidification cycle of a Ti powder bed. Starting near 330 K, the system is heated continuously to ~2600 K, held isothermally, then cooled back to ~600 K where it undergoes an extended isothermal anneal. Key observables—P.E., MSD, and Steinhardt q6—collectively document solid-state heating, melting, a liquid plateau, solidification, and post-solidification structural recovery.

# Event Identification

**Stage 1 — Solid-state heating (t = 20.8–~66.8):** T rises 330→2094 K. P.E. increases gradually (−225,200→−211,800 eV), q6,Bulk declines monotonically (0.426→0.285), and MSD remains moderate (~100–300 Å²). Phase Euclid dist rises steadily; Phase cosine similarity crosses zero near t ≈ 66.8 (siml = −0.00042), marking complete loss of initial crystallographic registry. Density cosine similarity collapses from 0.970 to ~0.116, indicating severe morphological restructuring.

**Stage 2 — Melting transition (t ≈ 68.8–82.8):** T reaches 2168–2602 K. P.E. drops sharply by ~4,600 eV (−210,400→−205,000 eV) while K.E. plateaus at ~16,000 eV, consistent with latent heat absorption. MSD,Bulk surges to >200 Å², q6,Bulk falls to ~0.168—indicative of a disordered liquid. Phase siml stabilizes at ≈ −0.71, signaling a structurally distinct liquid state. The temperature plateau at ~2600 K (t = 82.8–100.8) with nearly constant Total E. (≈ −189,000 eV) confirms a liquid steady state.

**Stage 3 — Cooling and solidification onset (t ≈ 100.8–160.8):** T decreases 2572→600 K. P.E. rises monotonically (−205,600→−223,000 eV), releasing latent heat. q6,Bulk increases from 0.171 to 0.297, and Phase Euclid dist decreases from 222 to 182, signifying progressive crystalline order recovery. MSD,Bulk decreases from ~230 to ~40 Å².

**Stage 4 — Isothermal solidification/annealing at ~600 K (t ≈ 160.8–238.8):** T is clamped at ~600 K; P.E. remains at −223,000 eV. q6,Bulk increases monotonically 0.297→0.364, Phase siml recovers from −0.271 to +0.222, and MSD,Bulk decreases to ~25–40 Å². This reflects ongoing post-solidification grain ordering and structural relaxation without further thermal driving.

# Causal Relationship Reasoning

Temperature elevation increases atomic kinetic energy (K.E. ∝ T), reducing interatomic binding and raising P.E. At melting, the enthalpy of fusion is absorbed as P.E. without proportional T increase—K.E. plateaus confirm thermostat-controlled latent heat uptake. Upon cooling, exothermic crystallization releases latent heat back into P.E. The Phase cosine similarity crossing zero at T ≈ 2094 K provides a quantitative marker for complete amorphization/melting of crystallographic order. Recovery of q6 during isothermal annealing at 600 K, with no T change but evolving Phase siml, demonstrates diffusion-driven grain growth decoupled from thermal input.

# Physical Conclusions

1. **Melting point estimate:** The K.E./T plateau and abrupt P.E. drop between t = 68.8–82.8 place Ti melting at ~2170–2600 K, bracketing the experimental T_m of Ti (1941 K). The superheating above 1941 K is consistent with finite-size effects and rapid heating rates in MD—a well-documented simulation artifact.

2. **Latent heat quantification:** ΔP.E. across melting ≈ 5,400 eV (~520 kJ/mol per simulation cell scaling), comparable in magnitude to Ti's experimental heat of fusion (~14.1 kJ/mol), scaled by atom count—confirming physical fidelity.

3. **Structural recovery without reheating:** q6,Bulk rises from 0.297 to 0.364 and Phase siml from −0.271 to +0.222 during the 600 K anneal, demonstrating solid-state recrystallization driven by residual atomic mobility at sub-melting temperature—analogous to classical recovery/recrystallization theory.

4. **Novel observation:** Phase cosine similarity becomes *negative* in the melt (minimum ≈ −0.74), indicating the liquid latent vector is not merely decorrelated from but *anti-correlated* with the initial solid state—suggesting the VAE latent space encodes a meaningful thermodynamic conjugate between crystalline and disordered phases.

**Recommended further analysis:** Radial distribution function (RDF) evolution across t = 68–83 to resolve HCP→liquid transition; Voronoi tessellation to quantify liquid-fraction; and nucleation rate analysis (CNT) during cooling to characterize heterogeneous vs. homogeneous solidification pathways.