See [[ROV Setup Detailed]] for more detailed instructions
### Preparing the ROV
- [ ] **Install Battery**
  - Verify battery is fully charged (voltage slightly above nominal)
  - Insert battery into the lower enclosure
  - Connect the polarized power connector
  - Close and seal the battery enclosure (open pressure relief valve during sealing)
  - Pressure test the battery enclosure [guidelines](https://bluerobotics.com/learn/using-the-vacuum-test-plug/)

- [ ] **Check Enclosures**
  - Ensure pressure relief valves on both electronics and battery enclosures are closed

### Setup Equipment
- [ ] **Fathom-X Topside Interface (FXTI)**
  - Connect ROV tether to "TETHER" receptacle
  - Connect FXTI USB to computer
  - Confirm FXTI is recognized as an ethernet adapter

- [ ] **WaterLinked G2 Topside**
  - Check battery charge
  - Set IP switch to "192.168.2.94"
  - Power on G2 box
  - Connect G2 to computer via ethernet
  - Place GPS receiver with a clear view of the sky
  - Deploy acoustic receiver antenna

- [ ] **WaterLinked U2 Locator**
  - Charge U2 Locator (7 hours of charging for 6 hours of use)
  - Note the rotary switch channel setting
  - Power on by tightening the lid (avoid over-tightening)
  - Mount to ROV bracket
  - Ensure Locator has a time fix (LED solid green or slow flashing)

### Network Setup
- [ ] **Network Bridge**
  - Confirm FXTI and G2 ethernet interfaces are bridged
  - Verify computer IP address is "192.168.2.1"

### Verify Web UIs
- [ ] **ROV Web UI**
  - Connect to "192.168.2.2"
  - Check BlueOS version and Autopilot status
  - Confirm connection to WaterLinked G2

- [ ] **WaterLinked Web UI**
  - Connect to "192.168.2.94"
  - Check locator channel setting
  - Configure reference frame (ensure consistency with ROV compass)
  - Confirm GPS lock
  - Validate G2 is receiving data from Locator after deployment

### QGroundControl (QGC)
- [ ] **Connect and Configure**
  - Ensure QGC connects to ROV automatically
  - Verify ROV heading reading is correct
  - Connect a compatible gamepad
  - Calibrate sensors if needed
  - Check WaterLinked position on map (ensure QGC is set to NEMA GPS devices at UDP port 14401)
  - Create and upload a test mission in QGC (check altitude values)