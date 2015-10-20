---
title: "RNATagSeq Library Preparation Protocol"
author: "Edward Wallace"
date: "19 October 2015"
shortref: "Shishkin et al. Nature Methods 2015"
nickname: RNAtagseq
tags: [RNA, NGS, RNASeq, Library prep]
output: html_document
shell_typeset: pandoc RNAtagseq.md -f markdown -t html -o RNAtagseq.html -s
---

This protocol is for RNASeq library preparation using the RNATagSeq method of Shishkin et al., Nature Methods 2015 (Broad institute). The protocol is mildly adapted by Edward Wallace, mostly increasing some volumes to make SPRI bead handling easier. Applies to batches of 4 to 32 samples.

## Reagents {#prepare .unnumbered}

### Wet reagents

- Turbo DNase; Ambion/Applied Biosystems, Cat.# AM2239
- FastAP Thermosensitive Alkaline Phosphatase; Thermo Scientific, Cat.# EF0651
- RLT buffer (RNeasy Lysis Buffer); Qiagen, Cat.# 79216 (220mL)
- T4 RNA Ligase 1; 30,000U/mL (0.5mL) Cat.# MO437M and comes with the following:
	- ATP(100mM) (make 10uL aliquots and store at -80°C, always use fresh aliquot)
	- PEG8000,50% in water
	- DMSO (100%); Sigma, Cat.# D8418-50ML for Molecular Biology
- RNase Inhibitor, Murine (40U/uL); NEB, Cat.# M0314S (3,000 units)
- SUPERase-IN 20U/uL (Ambion; AM2694; 2500U)
- AffinityScript Multiple Temperature cDNA Synthesis Kit, 50 reaction; Agilent, Cat.# 200436. includes the 
	- dNTPs, 10x RT buffer, RNase Block Ribonuclease Inhibitor (40U/uL)
	- 10X AffinityScript RT buffer; Agilent, Cat.# 600100-52
	- RNA Clean & ConcentratorTM-5 columns; Zymo Research, Cat. #R1015 (50 preps)
- SPRI beads:
	- RNAClean XP beads; Agencourt/Beckman, Cat.# A63987 (40mL); (mix well, make 1.5mL and 0.5mL aliquots, store at 4 °C)
	- For steps 8 onwards can use non-RNA certified, AMPure XP beads Cat.# A63881.
- Ribo-Zero:
	- Bacteria:
	Ribo-ZeroTM Magnetic Gold Kit (Bacteria); Epicentre/Illumina, Cat.# MRZMB126
	- Human:
	Ribo-ZeroTM Magnetic Gold Kit (Human/Mouse/Rat); Epicentre/Illumina, Cat.# MRZG126
	- Yeast: 
	Ribo-ZeroTM Magnetic Gold Kit (Yeast); Epicentre/Illumina, Cat.# MRZY1306
- Sodium hydroxide solution (5M); Sigma-Aldrich, Cat.# 656046 
- Glacial acetic acid (17.4M); Sigma-Aldrich, Cat.# ARK2183
- Nuclease free water; Affymetrix Cat.#71786 100 ML or Ambion, Cat.# 4387936
- 1x low TE (10mM Tris pH 8.0, 0.1mM EDTA); Affymetrix Cat.# 75793
- PfuUltra II Fusion HS DNA Polymerase; Agilent Cat.# 600670
	 - 10X PfuUltra II Reaction Buffer 

### Plates/Tubes/Caps:

- Flat PCR 12-cap strips, Optically clear; USA Scientific, Cat.# 1400-3120
- TempPlate No-skirt PCR Plates, 96 wells, 10 plates; USA Scientific, Cat.# 1402-9608
- 0.2 ml TempAssure PCR tube, attached flat cap, natural; USA Scientific, Cat.# 1402-8100
- wide-orifice pipette tips for PEG-8000

### Instruments:

- 2100 Electrophoresis Bioanalyzer Instrument; Agilent, Cat.# G2939AA (at functional genomics core)
- Agilent RNA 6000 Pico Kit; Agilent, Cat.# 5067-1513
- Agilent DNA HS Kit; Agilent, Cat.# 5067-4626
- QIAvac 24 Plus Vacuum manifold (1-24 spin columns; Qiagen cat# 19413)
- Thermocycler
- 10uL, 100uL, 200uL pipettes.
- 96R Ring Magnet Plate. Agencourt Cat#. A29164 or Alpaqua Cat.# A001219
- 96-well Aluminum Cooler Blocks, Light Labs USA Cat#. A-7079

## Notes
- Label everything and lay out tubes neurotically to avoid pipette error.
- Observe RNase-free sample prep, for steps 1-8, also neurotically. Clean your workspace and pipettes with 50% Ethanol and RNAse-Zap, use reserved RNase-free pipettes, ensure all tubes and reagents (including water) are RNase-free. 
- Avoid DNA contamination, _especially from other sequencing libraries_, for steps 8+. Use filter tips for PCR reactions.
- Points where the in-process libraries may be frozen at -80 C while you pause, are indicated as _PAUSE POINT_.
- SPRI/XP beads take a bit of skill. "SPRI (2x)" or "SPRI (1.5x)" refers to the ratio of beads to aqueous solution containing nucleic acids (NA); this ratio controls the size of NA retained (see http://core-genomics.blogspot.com/2012/04/how-do-spri-beads-work.html). Be patient; wait for binding and for magnetisation. Prepare fresh 80% ethanol solution every day or two; the concentration drifts over time due to evaporation (manufacturer recommends 70% EtOH). Some reactions (2nd ligation step 9) happen on-bead so change the elution step. Manufacturer's protocol with tweaks is below; practice SPRI extraction on a DNA ladder or RNA ladder and ensure full recovery.
	- Add appropriate ratio of beads to sample in PCR tube, pipette up and down 10x gently.
	- Incubate beads and sample at room temperature  for 15min to bind NA.
	- Place on 96R plate magnet for 5min, until solution is clear
	- Pipette out and discard clear solution (save this for troubleshooting)
	- Wash: Add 200uL fresh 80% EtOH without removing from magnet, incubate for 30sec, Pipette off clear solution.
	- Repeat 80% EtOH wash, use additional 10uL pipette to remove residual EtOH if necessary.
	- Let air dry for 2min. Apparently, drying too short is bad because residual ethanol interferes with downstream reactions, and too long is bad because beads may crack and/or bind hydrophobically, overly strongly, to your NA.
	- Elute: remove from magnet, pipette 40uL water or low TE buffer onto beads, pipette up and down 10X, replace on magnet and wait 5min (this is easiest with at least 40uL, hellish with 10uL).
	- Unless otherwise specified, take clear liquid to new tube, carefully not disturbing beads. 
- for First Ligation, set up RNA/barcoded adaptor in single tube or use the TempPlate No-skirt PCR Plates for batched samples (these rigid plates are easy to handle and can mix well by flicking by hand) – with a razor, cut a column (for 8 samples) or row (for 12 samples) and use as strip and cover with the Flat PCR 12-cap strips (these strips fit tightly on these plates and will not leak).
- TempPlate No-skirt PCR Plates, and strips cut from them, are flexible and may spring up when caps are put on or off, flicking your sample across the bench. Avoid this by firmly seating plates/strips in a tube rack before manipulating  the caps.

- Barcoded adaptors should be chosen carefully: plan a spreadsheet listing the sample name, cconditions, and which RNAtag adaptor (step 3) and P7 adaptor (step, after pooling) will be used. In each set of sequencing libraries combined on an Illumina sequencing run, there must be at least 3 distinct nt in all of the initial 4 nt of the sequenced adaptor for the sequencing machine to recognize clusters properly. (e.g. ATTA, GCAC, CAGT work, ATTA, GTAC, CTGT don't.)


## Procedure:

1. Control quality and quantity of RNA with Agilent Bioanalyzer
- Check RNA quality by running on the Agilent Bioanalyzer
- Place 0.5-5 ug of total RNA in a tube. For large numbers of samples, the input per sample could be reduced as to not exceed the maximum input of RiboZero (5ug) at step 5. Since about 25% of the input remains prior to adaptor ligation, less than 20ug total RNA per pool (end of step 4) is recommended. For smaller number of samples, higher input is recommended to ensure sufficient material remains after rRNA depletion.
- Increase the volume to 30uL with Nuclease free water
- Add 2uL of SUPERase-IN (20U/uL)
- Final total volume = 32uL (25ng/uL)
- Continue to next step or freeze at -80C until ready to process samples

	_PAUSE POINT_

2. Fragmentation and DNase-FastAP combination step

	2.1. Fragmentation using 2x FastAP buffer
	- Add 8 uL of 10X FastAP buffer to 32 uL RNA from step 1 (up to 1 ug) and mix well.
	- Incubate on _preheated_ thermal cycler for 3 min at 94°C
	- If RNA is partially degraded (RIN<7), fragment 3 min at 92°C, prevents over-fragmenting samples.
	- Place on cold block on ice
	
	2.2. DNase and FastAP treatment
	- Make a FastAP master mix, 40uL per sample:
	
		| Reagent (for 2X FastAP master)   | Amount | Final |
		|----------------------------------|--------|-------|
		| RNase Inhibitor, Murine (40U/uL) |   2 uL |   20U |
		| TURBO DNase (2U/uL)              |   8 uL |   16U |
		| FastAP (1U/uL)                   |  20 uL |   20U |
		| nuclease-free water              |  10 uL |       |
		|----------------------------------|--------|-------|
		| total                            |  40 uL |    2X |
	
	
	- Make FastAP master mix and mix well
	- Aliquot 40 uL into each tube/well with the 40uL of fragmented RNA from step 1.
	- Mix well
	- Incubate on preheated thermal cycler for 30 min at 37°C

	
	2.3. SPRI (2x) to remove enzymes and reaction buffer
	
	- Add 2.0x reaction volume of Agencourt RNAClean XP beads (160 uL) and  capture RNA on beads:
		- Incubate at room temperature for 15min to bind RNA
		- Place on magnet for 5min, until solution is clear
		- Pipette out and discard clear solution
		- Add 200uL fresh 80% EtOH without removing from magnet, incubate for 30sec, Pipette off supernatant.
		- Repeat 80% EtOH wash. Let air dry for 2min
	- Elute off beads with 24 uL nuclease free water
	- Take 5 uL of each sample and proceed to 1st ligation
	- QC: Save 1.2 uL from remaining RNA before addition of SUPERase-IN
	- Run 11 random samplings on Agilent RNA pico chip to check the fragmentation profile of each batch of 32
	- Add 1uL SUPERase-IN (20U/uL) to the remaining material and store at -80°C.
		- this can be used as backup if it is necessary to repeat process

	_PAUSE POINT_

3. FIRST LIGATION (RNA/DNA) 3’ Linker Ligation

- Add 1 uL of barcoded P7 adaptor (100 pmole= 1 uL of 100 uM) to 5 uL of dephosphorylated RNA
- Heat at 70°C for 2 min, place in cold block on ice
- Set up Ligation master mix below
	NOTE:
	- All reagents except enzymes (-20°C ) should be stored at -80°C in single use aliquots and brought to room temp just before use
	- Make up mix *at room temp* so the reagents don’t start precipitating when combined (if DMSO is added directly into cold buffer it will precipitate)
	- Pipette very slowly with wide-opening/cut tips for accurate aspiration of PEG (very viscous)
	- When setting up mix for multiple reactions include 25% extra to account for pipetting error due to the viscosity
	
		| Reagent (for Ligation master)    |  1 rxn  | 40 rxns |
		|----------------------------------|---------|---------|
		| 10× T4 RNA Ligase Buffer         |    2 uL |   80 uL |
		| DMSO (100%)                      |  1.8 uL |   72 uL |
		| ATP (100 mM)                     |  0.2 uL |    8 uL |
		| PEG 8000 (50%)                   |    8 uL |  320 uL |
		| RNase inhibitor, Murine (40U/uL) |  0.3 uL |   12 uL |
		|----------------------------------|---------|---------|
		|Total                             | 12.3 uL |         |
	
	
	- Mix really well by extensive vortexing tube since the solution is very viscous, then spin down briefly in microfuge
- Add 12.3 uL of ligation master mix to each tube/well containing 6 uL denatured RNA + adaptor.
- Add 1.8 uL of T4 RNA Ligase 1 (30,000U/mL) to each tube/well. 20.1 uL reaction volume total.
- Mix well *many* times; mix by flicking since the solution is very viscous
- Incubate at 22°C (room temp) for 1 hour 30 minutes.


4. Pooling step: RLT buffer + Zymo column
NOTE: At this point, multiple samples with distinct RNAtag adaptors will be pooled on the same spin column. Do not exceed 5ug RNA per pool, the maximum binding capacity of columns. Attempt to normalize the amounts (using your QC in step3, or even 1) based on the amount of non-ribosomal RNA in each pool, or your other needs.
- Add 60 uL of RLT buffer to each sample to inhibit ligase and mix well (80 uL total)
- Pooling and clean up using Zymo Clean & ConcentratorTM-5 column - follow manufacturer’s *200nt* cut off protocol:
	- Add 2x reaction vol (160 uL=2x 80 uL) of 1:1 binding buffer: EtOH (100%) / reaction
	- Carefully add reactions to be pooled to a single Zymo column.
		NOTE: When pooling >700 uL onto Zymo column use a vacuum manifold then proceed to centrifugation steps according to the manual
	- Wash and spin 1 min 12,000 g, then discard flow-through, once with 400 uL RNA Prep buffer, once with 800 uL RNA Wash buffer, once with 400uL Wash buffer, spin another 1min with no buffer.
- Elute 2 times with 16 uL nuclease free water for a total volume of 32 uL 
	NOTE: 2 elutions help improve recovery/yield of RNA
- Save 2 uL for QC-Run on Agilent RNA pico chip to check quantity and fragmentation profile

	_PAUSE POINT_

5. Quick Protocol for Ribo-ZeroTM
- See Manufacturer's instructions

6. First Strand cDNA
- Take 12 uL rRNA depleted RNA (use all the material from Ribo-Zero)
- Add 2 uL (50 pmoles) of AR2 primer (25 μM)
	 5’TACACGACGCTCTTCCGAT3’—AR2–53%GC,19bp,
- Mix well
- Heat the mixture to 70°C for 2 min and immediately place on cold block on ice
- Make RT master mix below: add in order on ice:

		| Reagent (for RT master)          |  1 rxn  | 2.5 rxns |
		|----------------------------------|---------|----------|
		| 10× AffinityScript RT Buffer     |  2   uL |   5   uL |
	    | DTT (0.1M)                       |  2   uL |   5   uL |
		| 25mM dNTP Mix (25mM each)        |  0.8 uL |   2   uL |
		| RNase inhibitor, murine (40U/uL) |  0.4 uL |   1   uL |
		|----------------------------------|---------|----------|
		|Total                             |  5.2 uL |  13   uL |
	
- Add 5.2 uL of RT mix to the 14 uL rRNA depleted RNA + AR2 RTprimer on ice
- Add 0.8 uL of AffinityScript RT Enzyme
- Mix well and spin for 5 sec
- Place in _preheated_ (55 °C) incubator or thermocycler. Incubate at 55 °C for 55 minutes.

7. RNA degradation after Reverse Transcription
	NOTE: make fresh working stock solutions of NaOH and Acetic Acid
- Add 10% reaction vol. of 1M NaOH (2 uL) to each reaction
- Incubate at 70 °C for 12 minutes
- Neutralize with 4 uL of 0.5M Acetic Acid; mix well
- Total volume = 26 uL

8. Reverse Transcription primer cleanup (2x SPRI) to remove enzyme and reaction buffer

- Add 14 uL of sterile water to each reaction for a final volume of 40 uL
- Transfer to new tubes (NaOH will start degrading tubes)
- Add 2x reaction volume SPRI beads (80uL) to the sample in new tubes, and mix up/down 10x
- Incubate at room temperature for 15min
- Place on magnet for 5 min or until solution is clear
- Pipette out and discard clear solution
- Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off discard the EtOH. 
- Repeat 80% EtOH wash, and let air dry for 3min
- Add 5 uL RNase/DNase free water to beads -- _KEEP BEADS AND TUBES, do not transfer_

9. Second LIGATION (ssDNA/ssDNA): 3’ Linker Ligation with beads
	NOTE: 3Tr3 adaptor: 5’ AGATCGGAAGAGCACACGTCTG 3’ = 55% GC, 22bp; Needs: 5’-P and 3’ ddC (or 3’-C3
spacer)
- Add 2 uL of 3Tr3 adaptor to cDNA
- Heat at 75°C for 3 min; Place on cold block on ice
- Make ligation reaction master mix (can be prepared ahead of time, on ice):
￼￼
- 2nd Ligation Master Mix: mix in order:

		| Reagent (for Ligation 2 master)  |  1 rxn  | 2.5 rxns |
		|----------------------------------|---------|----------|
		| 10× T4 RNA Ligase Buffer         |    2 uL |   5   uL |
		| DMSO (100%)                      |  0.8 uL |   2   uL |
		| ATP (100 mM)                     |  0.2 uL |   0.5 uL |
		| PEG 8000 (50%)                   |  8.5 uL |  21.3 uL |
		| T4 RNA Ligase 1 (30,000U/mL)     |  1.5 uL |   3.8 uL |
		|----------------------------------|---------|----------|
		|Total                             | 13.0 uL |  32.6 uL |
	
	
	- Mix really well by extensive vortexing tube since the solution is very viscous, then spin down briefly in microfuge

- Swirl the 7uL cDNA/beads/water with pipet tip, THEN add 13 uL ligation 2 master mix.
- Mix well by pipetting up and down 20x or cap tubes and flick several times; solution is viscous
- Quick spin (low speed centrifuge, to get everything to bottom of tube)
- Incubate overnight at 22 °C

10. SPRI clean up (2x) to remove adaptors
- Add 2x reaction volume SPRI beads (80uL) to the sample in new tubes, and mix up/down 10x
- Incubate at room temperature for 15min
- Place on magnet for 5 min or until solution is clear
- Pipette out and discard clear solution
- Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off discard the EtOH. 
- Repeat 80% EtOH wash, and let air dry for 3min
- Elute DNA by adding 30 uL RNase/DNase free water, transfer to new tube.

11. 2nd SPRI clean up (1.5x) to remove the remaining adaptors
- Add 1.5x reaction volume SPRI beads (45 uL) to the sample in new tubes, and mix up/down 10x
- Incubate at room temperature for 15min
- Place on magnet for 5 min or until solution is clear
- Pipette out and discard clear solution
- Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off and discard the EtOH. 
- Repeat 80% EtOH wash, and let air dry for 3min
- Elute DNA by adding 25 uL RNase/DNase free water, transfer to new tube.

	_PAUSE POINT_

12. PCR Amplification TEST to determine final cycle number

- Set up a test PCR using 5 uL of ss cDNA sample and 9-12 cycles of PCR (based on experience with pool of 16 reactions, each starting with ~400ng total RNA)
- Include a negative control (water) for each primer set
- Make PCR Master Mix:

		| Reagent (for PCR master mix)    |  1 rxn  | 
		|---------------------------------|---------|
		| Water, PCR-clean                | 14.3 uL |
		| 10X Pfu Ultra II Buffer         |  2.5 uL |
		| dNTP mix (10mM each)            |  0.7 uL |
		| P5 primer (P5_RNATag, 12.5 uM)  |  1   uL |
		|---------------------------------|---------|
		|Total                            | 18.5 uL |

	- Mix well
	- Aliquot 18.5 uL / sample into PCR tubes
	- Add 1 uL of appropriate P7 index primer to each well
	- Add 5 uL of ss cDNA from step 11, or water (for negative control)
	- Add 0.5 uL of Pfu Ultra II Polymerase.

- Mix well and aliquot 8 ul into each of 3 tubes
- Place each in a thermal cycler with the following conditions
Cycling conditions:
	start: 98°C, 3min
	cycle: 9, 12, 15 cycles (for test PCR)
		98°C, 30sec; 55°C, 30sec; 70°C, 30sec
	end: 70°C, 2min; 4°C, hold

13. SPRI clean up (1.5x) to remove reaction buffer and PCR primers:
- increase reaction to 30uL with sterile water
- Add 1.5x reaction volume SPRI beads (45 uL) to the sample in new tubes, and mix up/down 10x
- Incubate at room temperature for 15min
- Place on magnet for 5 min or until solution is clear
- Pipette out and discard clear solution
- Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off and discard the EtOH. 
- Repeat 80% EtOH wash, and let air dry for 3min
- Elute off beads with 10 uL 1x low TE (10 mM Tris, 0.1M EDTA)

14. QC test PCR amplification on Agilent DNA HS chip
- Based on test results change the cycle number, if necessary, and set up more reactions to provide enough material to send for sequencing
- UChicago functional genomics core asks for ~15 uL of 10 nM library; aim for at least 25 uL = 0.25 pmol = 60 ng of 400nt dsDNA (~250 kDa).
- To pass QC, library should should smooth profile 200-500nt long; visible single bands indicate PCR artefacts.

	_PAUSE POINT_
	
15. PCR for Sequencing library
- Choose the optimal PCR cycle # based on Bioanalyzer QC and amplify

- Set up a test PCR using 5 uL of ss cDNA sample and 9-12 cycles of PCR (based on experience with pool of 16 reactions, each starting with ~400ng total RNA)
- Include a negative control (water) for each primer set
- Make PCR Master Mix:
		| Reagent (for PCR master mix)    |  1 rxn  | 
		|---------------------------------|---------|
		| Water, PCR-clean                | 28.6 uL |
		| 10X Pfu Ultra II Buffer         |  5   uL |
		| dNTP mix (10mM each)            |  1.4 uL |
		| P5 primer (P5_RNATag, 12.5 uM)  |  2   uL |
		|---------------------------------|---------|
		|Total                            | 39   uL |

	- Mix well
	- Aliquot 39 uL / sample into PCR tubes
	- Add 2 uL of appropriate P7 index primer to each well
	- Add 10 uL of ss cDNA from step 11, or water (for negative control)
	- Add 1 uL of Pfu Ultra II Polymerase.

- Mix well and aliquot 10 ul into each of 5 wells of a 96-well plate (amplification is apparently more robust in smaller volumes), cap.
- Place each in a thermal cycler with the following conditions
Cycling conditions:
	start: 98°C, 3min
	cycle: # determined from test PCR
		98°C, 30sec; 55°C, 30sec; 70°C, 30sec
	end: 70°C, 2min; 4°C, hold

16. SPRI clean up (1.5x) to remove reaction buffer and PCR primers:
- increase reaction to 30uL with sterile water
- Add 1.5x reaction volume SPRI beads (45 uL) to the sample in new tubes, and mix up/down 10x
- Incubate at room temperature for 15min
- Place on magnet for 5 min or until solution is clear
- Pipette out and discard clear solution
- Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off and discard the EtOH. 
- Repeat 80% EtOH wash, and let air dry for 3min
- Elute off beads with 30 uL water and transfer to new tubes.

16. SPRI clean up (0.7x) to remove reaction buffer and PCR primers:
- Add 0.7x reaction volume SPRI beads (21 uL) to the sample in new tubes, and mix up/down 10x
- Incubate at room temperature for 15min
- Place on magnet for 5 min or until solution is clear
- Pipette out and discard clear solution
- Wash: Add 200 uL fresh 80% EtOH without removing from magnet and incubate for 30 sec. Pipette off and discard the EtOH. 
- Repeat 80% EtOH wash, and let air dry for 3min
- Elute off beads with 25 uL 1x low TE (10 mM Tris, 0.1M EDTA)

17. Proceed to sequence
- Check quantity/quality on Bioanalyzer with Agilent DNA HS chip
- Submit to genomics core for sequencing.
- If desired to combine multiple libraries PCR'd separately, they must have different barcoded P7 primers. Amounts of sequenceable material must be carefully measured to ensure even coverage across libraries, e.g. with the KAPA biosystems kit (Cat. # KK4824). The genomics core can do this for a small fee.
