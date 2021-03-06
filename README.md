# FPGA_AI_SRAM
Preliminary part of AI acceleration with FPGAs, interfacing external memory for greater capacity.

Memory chips I will use for the experiments are the [Cypress Semiconductor Corp. CY62157EV30LL-45ZXIT 1Mx8 SRAM (pdf)](https://www.cypress.com/file/43021/download) and the [Cypress Semiconductor Corp S29AL008J55TFNR10 1Mx8 Flash (pdf)](https://www.cypress.com/file/216396/download). 

Chose these for cost and simplicity. They have the same footprint. The Flash has the advantages of costing $0.60 in 10-quantity from Digi-Key, so being good for TSOP soldering practice, as well as being able to retain data while unpowered. The SRAM is pricier at $2.93 in single quantity, so not bad. (On edit: that's a fluke, because the chips don't have a warranty... do they work? I don't know. I just ordered 10 more in hopes that they do. I reckon sooner or later I will just need to use DRAM. **FOR LATER REFERENCE WRT DRAM** [Lattice has a project related to it](http://www.latticesemi.com/en/Products/DesignSoftwareAndIP/IntellectualProperty/ReferenceDesigns/ReferenceDesigns01/FastPageModeDRAMController) though that appears to be just with one kind. Find docs about it in general; writing an sdram controller might not be so scary and looks like a good intermediate project. Perhaps https://pdfs.semanticscholar.org/d960/f5cc9782719dcfa780b4f4aea51b8f791c62.pdf, and let's move this discussion to a new project or at least the wiki.)

Their interface is easy to understand and they're kind of OK for speed. Speed in actual wall time is not the point of this exercise so much as speed in terms of clock cycles; I'm looking more for savings of complexity which will translated to savings in time once it can run on "real" hardware.

# Objective

The initial goal is to try accelerating some data structures such as red/black trees and running some old AI techniques like A* to get a feel for how well programmable logic can tighten them up.

Ultimately, I want to implement modern methods such as RNNs, but since I'm still working on tiny cheap eval boards it's unlikely I can do much - but I will look into it, and I will learn some useful things in this endeavor that will transfer (transfer learning LOL) I imagine I'm also going to have to pick up DSP for best results there.

OK so now got this project cloned onto makevm4, let's try a push from it. Not on the VPN, so I expect it to work.

Copied over some initial stuff like osresearch's makefile for their serial project, need hack up to do what I want AND DO WHATEVER I NEED TO DO TO SATISFY THE TERMS OF THEIR LICENSE!!!!!!!!!!!!

# Notes

**Release / tag v0.1 should be a good skeleton for future icestorm projects** But [the repository VerilogSkeleton](https://github.com/SamWibatt/VerilogSkeleton) should also be that and I will maintain it as such.

I will be keeping my usual stream of consciousness [notes in the repo wiki, qv](https://github.com/SamWibatt/FPGA_AI_SRAM/wiki).

Makefile, Makefile.icestorm, and upduino_v2.pcf are copied and modified from osresearch's code at https://github.com/osresearch/up5k licensed under GPL3
