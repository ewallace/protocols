---
title: "RT-qPCR for RNA quantification with SYBR dye"
author: "Edward Wallace"
date: "14 May 2018"
nickname: RT-qPCR
tags: [RNA, qPCR]
output: html_document
html_typeset: pandoc RTqPCR_Agilent_Lightcycler_Protocol.md -f markdown -t html -o RTqPCR_Agilent_Lightcycler_Protocol.html -s
pdf_typeset: pandoc -V geometry:margin=0.5in RTqPCR_Agilent_Lightcycler_Protocol.md -f markdown -t latex -o RTqPCR_Agilent_Lightcycler_Protocol.pdf -s
fontsize: 12pt
papersize: a4
---

This protocol is for RT-qPCR for RNA quantification, using the Roche Transcriptor RT, the Agilent SYBR master mix and Roche Lightcycler instrument. The protocol originates with David Barrass from Jean Beggs' lab. It should work with minor tweaks with equivalent reagents and systems. 


## Notes ##

Reaction volumes depend on plate size and instrument. 10µl reactions work for 96-well plates, on Stratagene or Roche instruments. 5µl (electronic pipette) down to 2uL works in our hands for 384-well plates on the Lightcycler 480. 1µl works for 1536-well plates on the Lightcycler 1536. Loading a 1536-well plate with the Labcyte Echo Liquid handler has been tested by Labcyte to work down at 0.5uL or 0.25uL volume on the LC1536 (Application Note G101).

Perform +RT reactions in triplicate; -RT reactions can be single because usually a problem with -RT will show up in many sample/probe combinations.

For the qPCR plate, it is best to have each row contain a single probe (or sample), and each column a single sample (or probe), so you can load in parallel with an multichannel pipette. We use an Integra Voyager on repeat-dispense setting; fast dispensing just near the edge of the well gives nice reproducible results.

## Components ##

- Sample: RNA resuspended in ddH2O 
- Primers and primer mixes:
    - 4µM mix of *each* primer pair for qPCR
    - EITHER: 2.5µM mix of *all* reverse primers for RT (2.5µM each)
    - OR: 60µM Random Primer mix (35 µM hexamers, 25 µM dT23VN) for RT (e.g. NEB S1330)
- RNase-free H2O
- DNase (DNaseI RNase free 1U/µl, Promega),  10x DNase buffer
- RNase inhibitor (SuperAseIn, ThermoFisher)
- Reverse transcriptase (Transcriptor, Roche; *or* Superscript IV, Thermo), 5x RT buffer
- PCR master mix (Brilliant III Ultra-Fast SYBR® Green QPCR Master Mix, Agilent)
- PCR tube strips, 0.2ml each, with lids
- Aerosol resistant (filter) pipette tips


\newpage 


## DNase treatment ##  

1.	Make the Sample mix in a new centrifuge tube (0.2 or 0.5ml), add:-
    - 12.5µg of RNA (down to 5µg is fine too as long as its consistent)
    - H2O to 8µl
    - 1µl of 10x DNase Buffer 
    - 0.9µl of DNase
    - 0.1µl RNase inhibitor
2.	37°C 1hour
3.	75°C 10minutes to deactivate the DNaseI.

## Reverse Transcription ##

1.	Add 2.5µl RT primer mix 
2.	Transfer 5µl (5µg of RNA) of this to 2 new 0.2mL tubes. One for +RT, one for -RT.
3.	Denature the RNA at 70°C for 5 minutes, then in to iced water.
4.	Make RT master mix, per sample:
    - 2µl 5 x First strand synthesis buffer
    - 0.75µl 10mM dNTP mix
    - 1.5µl H2O
    - 0.25µl RNase inhibitor
    - 0.5µl Transcriptor, *or* H2O for a -RT control
5.	Add 5µl of RT master mix to the denatured RNA; this brings the volume up to 10 µl
6.	EITHER 55°C 1-2 hours if using Reverse Primers OR 25°C for 5 minutes followed by 55°C for 1 hour if using Random Primer Mix.
7.	Add 180µl of H2O to the first strand cDNA to dilute the buffer prior the qPCR.

## Quantitative PCR (4µL reaction for 384-well plate)##

1.	Make the qPCR mix for each primer pair, for each well:
    - 1.6µl   2x SyBr Green QPCR mix
    - 0.4µl primer pair mix (4µM each).
2.	Add 2µl of qPCR mix and 2µl of the diluted cDNA to each well of the 384 well plate.
3.	Spin down, mix by rattling plate, spin down again 
4.	Place in PCR machine and run amended Agilent 2-step PCR program:-
    - Taq activation:
        - 95°C  3min 
    - 40 cycles of amplification:
        - 95°C  5sec
        - 60°C  10sec with green fluorescence reading
    - Melt curve
        - Step up to 65°C
        - Ramp up to 95°C at 0.29°C/s
        - 2 readings per second.


