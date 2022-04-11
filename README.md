# mk3s-barebones-klipper-config

 A bare-minimum Klipper config to get a stock Prusa MK3S(+) running on Klipper firmware.

 ### Prerequisites

  * A roughly Prusa-MK3(S)(+)-shaped printer with an Einsy Rambo MCU board (the stock board included with Prusa MK3 printers).
  * Your Einsy's 32u2 usb-to-serial chip flashed with [faster firmware](https://github.com/PrusaOwners/prusaowners/wiki/hoodloader2).
  * Klipper already up and running on your choice of host. I use [Mainsail](https://docs.mainsail.xyz/) running on a Raspberry Pi 4.

 ### Printer Setup and Initialization

 * In [`printer.cfg`](/printer.cfg), make the following changes:
   * Under `[mcu]`, verify `serial:` matches your Einsy's serial id so the Klipper host can talk to it.
 * Run through all of the Klipper [configuration checks](https://www.klipper3d.org/Config_checks.html) to ensure your printer is ready to print safely. This page references Octoprint, which can be ignored - everything can be done the same in Mainsail.  
   * Pay particular attention to the [verify stepper motors](https://www.klipper3d.org/Config_checks.html#verify-stepper-motors) section, where you check the steppers are moving in the right directions. Remember that when the y axis (the bed) is moving in a positive direction, that means the *nozzle* is moving in a positive direction *relative to the bed*.
 * **IMPORTANT:** Use [`PROBE_CALIBRATE`](https://www.klipper3d.org/Probe_Calibrate.html#calibrating-probe-z-offset) to calibrate your base probe offset (the z-offset from the probe trigger point to the actual tip of the nozzle) so you don't crash your nozzle/damage the bed. Do not assume the current value in this config matches your printer.
 * Check and calibrate [`rotation_distance`](https://www.klipper3d.org/Rotation_Distance.html) if you want, but I found it to be close enough for my stock MK3S+ Bondtech drive gears that I didn't bother.


 ### Klipper Config Reference

 [Klipper Configuration Reference Docs](https://www.klipper3d.org/Config_Reference.html)
