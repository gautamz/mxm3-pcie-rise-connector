# mxm3-pcie-rise-connector
A connector to bridge a MXM port and a standard PCIe port

# Motivation - 
Extend the life of my laptop by 1-2years and delay a system upgrade so that I can avoid CPUs with potential Meltdown/Spectre vulnerabilities.

# Plan -
1) Work out what pins on the MXM connector are needed to connect to a PCIe riser to make a GPU run at x16 PCIe speeds
  a) [optional side goals] 
      ( i) Work out the correspondence between the pinout of a Displayport to eDP converter so that I can route the GPU video 
           output back to laptop screen. This may save on PCIe bandwidth in trying to get the video back through PCIe
      (ii) Work out how to shield PCIe extender ribbon cables. Shielded cables can be quite expensive
3) Build a PCB design
4) Print PCB and test
5) Repeat 3 & 4 till success, revisit 1 if needed

# Challenges
1) Limited electrical/electronics engineering background
2) High frequency PCB trace routing is more than tough. Though this endeavor maybe simpler

# Progress
29 Jan 2018 - Have worked out solutions to mapping PWR_GOOD, PEX_STD_SW and PEX_RST pins for MXM. 
- PWR_GOOD to connect to 3.3V source through a 10K_04 resistor. 
- PEX_STD_SW to connect to ground. 
- PEX_RST on MXM to connect to PERST on PCIe.

Also I think I can map the DP port pins for MXM to a DP female port. Then I can just take a Display Port cable out from the eGPU and plug it into the connector to feed the signal back to the laptop. The same can also be done for HDMI.
Now on to making the PCB layout...

28 Jan 2018 - Have managed to get MXM v3.0 pinout and PCIe pinouts. Reading GPU manuals and public guide notes have worked out most(?) of the MXM-PCIe connections that should work. Need more clarifications for MXM pins PWR_GOOD, PEX_STD_SW# & PEX_RST# and PCIe pin PERST#. Uploaded spreadsheet with the pinout tables and the potential pin mappings.
