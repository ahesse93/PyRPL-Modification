# pyrpl-freqmod

Modifies the RedPitaya FPGA of PyRPL, so that the built in lock in amplifier can output a sinusoidal frequency modulation

The output of IQ module 0 is added (after rescaling) to the phase step size of ASG module 0. If ASG 0 outputs a sine wave this will sinusoidally modulate its frequency with the frequency of the IQ module (useful eg for frequency modulating a microwave)
The modulation depth can be set by changing the output amplitude of IQ module 0 - currently it should be set to about 1-2 MHz at full amplitude.

The output of IQ module 1 modulates ASG 1 this way, and IQ 2 modulates ASG 0 and ASG 1 at the same time.

Also, IQ2 now outputs the sum (IQ2) and the difference (IQ2_2) of the output of IQ 0 and IQ 1.

The Verilog source code for the modified modules as well as the bitstream file are provided - all other files are identical to the ones provided on the PyRPL github repository (version 0.9.4.0)


To just use this modification replace red_pitaya.bin in your pyrpl folder with the file provided here - after this ASG 0 and IQ module 0 will automatically be wired together when you connect to a RedPitaya.  
If you do not know the location of your pyrpl installation run `pip show pyrpl`
