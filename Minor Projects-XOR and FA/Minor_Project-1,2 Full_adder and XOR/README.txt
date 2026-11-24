LTspice starter project: Full Adder and XOR transistor-level comparisons
=========================================================================

IMPORTANT
---------
These are educational starter netlists using generic Level-1 MOSFET models.
They are useful for learning and for initial functional simulations.

Files
-----
FA_CMOS.cir  : 1-bit full adder, CMOS NAND/XOR implementation
FA_CMOS_PAVG.cir: full adder , pavg and timedelay
FA_CMOS_PAVG(text file): output log 
FA_PTL.cir   : full adder using NMOS pass-transistor muxes (logic-high degradation expected)
FA_PTL_PAVG.cir: full adder , pavg and timedelay
FA_PTL_PAVG(text file): output log
FA_TG.cir    : full adder using transmission-gate muxes
FA_TG_PAVG.cir: full adder , pavg and timedelay
FA_TG_PAVG(text file): output log
FA_GDI.cir   : mux-based educational proxy
FA_GDI_PAVG.cir: full adder , pavg and timedelay
FA_GDI_PAVG(text file): output log
XOR_CMOS.cir : CMOS XOR
XOR_CMOS_PAVG.cir: XOR pavg and timedelay
XOR_CMOS_PAVG(text file): output log 
XOR_PTL.cir  : pass-transistor XOR
XOR_PTL_PAVG.cir: XOR pavg and timedelay
XOR_PTL_PAVG(text file): output log
XOR_TG.cir   : transmission-gate XOR
XOR_TG_PAVG.cir: XOR pavg and timedelay
XOR_TG_PAVG(text file): output log
XOR_GDI.cir  : mux-based educational proxy
XOR_GDI_PAVG.cir: XOR pavg and timedelay
XOR_GDI_PAVG(text file): output log

How to run
----------
1. Open LTspice.
2. File > Open and choose one .cir file.
3. Run the simulation.
4. Open the waveform viewer and add traces: V(A), V(B), V(CIN), V(SUM), V(COUT)
   for full-adder files; V(A), V(B), V(Y) for XOR files.
5. Each transient test runs through all eight full-adder input combinations
   (or all four XOR combinations) using pulse sources.
6. Verify the truth table before taking measurements.

Generic test conditions used here
---------------------------------
VDD = 5 V; generic Level-1 models; 1 us input time slots; no external output load.
These values are only starter settings.

Measurements
------------
- Functional correctness: compare waveform levels with the truth table.
- Delay: measure from input 50% crossing to output 50% crossing. Measure SUM and
  COUT separately, and record the worst relevant delay.
- Average power: use the supply current and calculate average power over a steady
  representative interval. LTspice source current sign may be negative, so use
  -V(VDD)*I(V1) or the equivalent expression appropriate to the supply source.
- PDP = average power * propagation delay.
- Transistor count: count every MOSFET, including required inverters/buffers.

