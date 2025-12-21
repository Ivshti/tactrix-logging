## Summary
For reverse-engineering OEM UDS DIDs, you need this setup

- a windows machine
- SavvyCAN
- Tactrix Openport 2.0 drivers installed; make sure they're for x64 too as SavvyCAN is built for x64
- OBD Y cable

Connect the OBD Y cable to the car, the diagnostics tool of your choice to one of the ends, and Tactrix to the other.
Connect the Tactrix to a laptop with SavvyCAN, and observe the CAN traffic.
Now start a diagnostic session to read the exact specific parameter you want to reverse engineer. You'll observe UDS traffic
that will include the DID and response.

Note: 
- Tactrix uses a leading 0 for all UDS paramids, SavvyCAN does not

TODO 
- test SavvyCAN on macOS

### OBD-WWH / DoIP

For newer cars that use diagnostics over IP (eg BMW G87), the setup is different, as Ethernet is not a peer-to-peer communication protocol like CANBus.

You'll need an OBD -> RJ45 cable, an Ethernet switch, and the diagnostic tool connected to the switch, as well as a device that will run Wireshark to observe the traffic.

If the diagnostic tool is ran on a laptop, you can observe the traffic on that device directly. 
