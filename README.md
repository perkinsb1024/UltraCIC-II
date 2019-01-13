# UltraCIC II
This code allows you to create a replacement CIC chip for N64 games that you own on an ATTiny25 Or ATTiny45. The original code was written by jesgdev and updated with multi-region support by saturnu. I simply modified it slightly for my purposes (no multi-region support, ATTiny45 instead of 25) and uploaded the code for posterity. 

# Instructions
- Select the version of CIC chip you wish to recreate by uncommenting one of the lines from 59-74 in UltraCIC_t45.asm.
- If you wish to use this on an ATTiny25 instead of an ATTiny45, comment line 122 and uncomment line 124.
- Install avra (`brew install avra` on MacOS)
- Assemble the code (`avra UltraCIC_t45.asm`)
- Flash the file to your ATTiny (IE: `avrdude -p t45 -c usbtiny -U flash:w:UltraCIC_t45.hex`)
- Update fuses (IE: `avrdude -p t45 -c usbtiny -U lfuse:w:0xc0:m -U hfuse:w:0xdf:m`)

# More Information
- [Original source code](https://assemblergames.com/threads/n64-cic-looking-for-710x-series-info.55237/)
- [Multi-region patch information](https://krikzz.com/forum/index.php?topic=3450.0)
- [Assembly guide](https://bitwise.bperki.com/2019/01/12/repairing-an-n64-cartridge-without-blowing-in-it/)