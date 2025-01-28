# Voron-XT0
A couple of tweaks for Zruncho's Double Dragon and Tri-zero mods

This is a list of tweaks I had to make while working with [Zruncho](https://github.com/zruncho3d)'s [Double Dragon](https://github.com/zruncho3d/double-dragon) and [Tri-Zero](https://github.com/zruncho3d/tri-zero) mods. While both of them are really well made and documented, there are some issues I need to either fix or update:
* **Firmware**
  
The firmware is written for BTT Octopus Pro 1.1 with two BTT EBB 36 CANboards. More details in the Firmware.
The original firmware used relies on a V0.0 firmware which uses endstops for each axis and and older klipper IDEX config that didn't work in my case. This version uses virtual endstop for Y and Z axis. X axis also has a virtual endstop option, but is disabled by default due to toolhead position shifting when homing Y. Either use the endstops for the X axis or configure the G28 command to run in YXZ order.

* **New X axis endstops**

Because I've decided to use the [Dragon Burner](https://github.com/chirpy2605/voron/tree/main/V0/Dragon_Burner) I needed to use the V0.2 mount system. I've printed two MGN9C [mounts](https://github.com/chirpy2605/voron/blob/main/general/Alternative_Voron_Mounts/Modified_Mounts/v0.2/STLs/X_Carriage_MGN9C_Switch.stl) (You will need to mirror one part). This requires to print two endstop bumpers and use two flat head screws instead of the stock ones at the top of the gantry. Also there's a bumper with extra 6mm space for the left endstop in case you use [ZeroClick](https://github.com/zruncho3d/ZeroClick) probe that requires a bit of extra space on the side, otherwise the magnet mount will hit the rail on homing.

* **Longer front bed mounts**

Dragon Burner has a different offset from the gantry compared to the stock toolhead. As a result, the nozzle can't reach the 0 coordinate on the y axis. The front bed attachment parts were elongated by 6mm to fight this. This also guarantees the full 120mm of print space in the Y axis. There are two options for the parts: just the elongated part and a part with a side hole to add an extra flat head screw to reinforce the mount.

* **Skirt mount for a Touchscreen**

A simple front skirt mount for the BTT PiTFT screens. Uses the RasPi mount threads to mount. Requires 2 M3x40 screws with M3 nuts (Self locking nuts are recommended) and 4 M2.5x8 screws for the mount

* **Rear panels and panels elongations (coming soon)**

The cover between the AB motors was split into 3 parts. The midle part mounts the CANbus wires, the side ones mount the PTFE tubes. The filament is fed from the back side of the panel instead of V0's longer path from the skirt
