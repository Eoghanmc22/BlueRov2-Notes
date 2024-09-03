See [[Deployment Check List]] for this in a more concise checklist format
## Preparing the ROV

1. Select and install a charged battery
	1. Make sure the battery is fully charged. This can be verified by checking the voltage of the battery is slightly above its nominal voltage rating
	2. Open the lower water tight enclosure on the BlueROV and slide in the battery
	3. Connect the polarized power connector from the battery into the opposite connector on the end cap. This will cause the ROV to begin powering up
	4. Close the battery enclosure by installing the end cap
		1. Make sure to open the pressure relief valve to allow the air a path to escape
	5. Pressure test the battery enclosure
		1. Follow the guidelines posted [here](https://bluerobotics.com/learn/using-the-vacuum-test-plug/)
2. **Verify that the pressure relief valves on both the electronics enclosure and the battery enclosure have been closed** Failure to do so could cause the enclosures to flood with water
3. Setup the Fathom-X Topside Interface (FXTI)
	1. Identify the Binder connector on the end of the ROV's tether and connect it to the receptacle labeled "TETHER" on the FXTI
	2. Connect the USB output of the FXTI to your computer
	3. Verify that the FXTI displays as an ethernet adapter in your computer's network settings
4. Setup the WaterLinked G2 Topside
	1. Verify its battery is sufficiently charged
	2. Verify the IP switch is in the "192.168.2.94" position
	3. Turn on the G2 box using the power button on the right hand side
	4. Use an ethernet cable to connect the WaterLinked G2 to your computer
	5. Place the GPS receiver in a position where it has an open view of the sky
	6. Connect and deploy the acoustic receiver antenna
5. Setup the WaterLinked U2 Locator
	1. Charge the U2 Locator before planning to operate the ROV
		1. Charging takes 7 hours for 6 hours of operation
	2. Take note of the channel setting on the rotary switch inside of the locator
	4. Power on the locator by tightening the plastic lid
		1. Avoid over tightening as this can lead to the lid being hard to unscrew
	5. Mount the locator to the 3D printed bracket located on the side of the ROV
	6. Verify that the Locator has received a time fix before deploying the ROV
		1. The led indicator should be either solid green or slow flashing
		2. Documentation on the LED Signals [here](https://waterlinked.github.io/underwater-gps/locators/locator-u1/#led-signals)
6. Network bridge
	1. Validate that the FXTI and the WaterLinked G2 ethernet interfaces are bridged and that the computer has been assigned the IP address of "192.168.2.1" on that interface
7. Verify that the Web UIs are reachable
	1. Attempt to connect to the ROV's web UI at "192.168.2.2"
		1. Verify that the ROV loaded the latest version of BlueOS
		2. Verify that the Autopilot is started
		3. Verify that the ROV can connect to the WaterLinked G2
	2. Attempt to connect to the WaterLinked's web UI at "192.168.2.94"
		1. Verify that the correct locator channel is set
		2. Configure the reference frame for the G2
			1. Ideally use a static reference frame
			2. **Make sure the configured/reported heading is consistent with the ROV's compass**
		3. Make sure the G2 reports it has a good GPS lock
		4. Once the ROV is deployed, validate the G2 is receiving data from the locator
8. QGroundControl (QGC)
	1. Once the ROV is accessible and QGC is open, the software should automatically connect to the ROV
	2. **Validate the ROV's heading reading is correct**
	3. Connect a compatible gamepad to pilot the ROV
	4. Calibrate sensors if necessary
	5. Once the ROV is deployed, The waterlinked position should be displayed on the map
		1. If this does not happen, check that the G2's status in its web ui, and that QGC is configured to connect to NEMA GPS devices at UDP port 14401 in QGC's application settings
	6. Create a test mission in QGC's plan mode and upload it to the ROV
		1. Be sure to check altitude values

