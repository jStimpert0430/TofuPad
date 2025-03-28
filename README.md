# TofuPad

`Tofupad` is a free diy symmetrical slim low-profile hitbox/leverless style rhythm game controller that uses a [YD-RP2040](https://www.amazon.com/RP2040-Board-Type-C-Raspberry-Micropython/dp/B0CG9FWDDC?crid=2Z33OKLFBHHP7) Raspberry Pi Pico clone with USB-C and the [GP2040-CE](https://gp2040-ce.info/) controller firmware.

Created primarily with DJMAX and Taiko No Tatsujin in mind, but should be compatable with a galaxy of other rhythm games.

![Preview](render.png?raw=true "Preview Screenshot")

# Build guide

## Parts required

`1x YD-RP2040`

`9x M4 x 8mm Hex Socket Countersunk Head Screw Bolts`

`12x low profile gatreon keyboard microswitches of your choice`

`a 3D printer with a 10 inch printbed or access to a 3D printing / CNC milling service(JLPCB, PCBWAY, etc)`

This case is sized exactly for this particular flavor of Pico clone and while others may fit, they will likely be loose in the socket leading to issues plugging in the USB. In addition, most low profile microswitches should work, but full sized will be too tall to fit without removing part or most of the legs.

You may also want to try microswitches that have a lower actuation point. Most low profile linears have a really high actuation point and can make pressing buttons feel a little akward, since they will activate as soon as you touch the button rather than when you're close to bottoming out like most traditional rhythm game microswitches do. Consider possibly a tactile switch to help with this.

## Firmware installation
Refer to the [GP2040 installation wiki](https://gp2040-ce.info/controller-build/wiring/) for more detailed instructions, but a quick step by step is --

1. Download most recent version of [GP2040-CE firmware](https://gp2040-ce.info/downloads)
2. Put RP2040 into bootsel mode by holding the boot button on the board while plugging in the device
3. Copy the .uf2 file into the flash memory of the RP2040 using your preffered file manager
4. reboot device and if everything went correctly, the firmware should be installed.

NOTE: 
  As GP2040 is primarily a competetive fighting game firmware for use across various tournament settings, SOCD cleaning is enabled by default and could cause some issues in rhythm games when left or right or up and down will need to be pressed at the same time. Once the project is assembled you can configure this option and others by holding start while plugging in the device and navigating to the configuration webUI in your browser. 

I wanted to use GP2040 in this project for it's extreme low latency, compatability with range of devices, the ability to edit debounce and remap pin values on a software level. I find it "just werks" for what I need it for and where I need it. It's a fantastic piece of software for homebrew controllers

## Wiring

To make this case as stable and as solid sounding as possible while it's being bashed on, it was required to design the case with as tight of a fit possible with a lot of solid space between the two halves, so planning wiring and laying everything out cleanly is important to success. I used cellotape to keep wires orderly as I was laying everything out and cutting to length as I soldered everything into the Pico pins.

Going forward, I'd like to design an actual PCB with hotswap sockets but as I had a working device already I thought it might be better to just release it and post revisions as I reach milestones with the project. Currently the pinouts are as follows

[GP2040 pinout image](https://gp2040-ce.info/assets/images/RaspberryPiPico_Pinout-4650ef12c24cc3cb5f8ff7ddbcbfafee.svg)

`ground -> ground of button 8 daisy chained from here to the rest of the buttons`

`GP02(Default up) - Button 3(Left side middle finger button)`

`GP03(Default down) - Button 9(Left side thumb button)`

`GP04(Default left) - Button 2(Left side ring finger button)`

`GP05(Default right) - Button 4(Left side index finger button)`

`GP06(Default A button) - Button 5(Right side index finger button)`

`GP07(Default B button) - Button 6(Right side middle finger button)`

`GP10(Default X button) - Button 7(Right side ring finger button)`

`GP11(Default Y button) - Button 10(Right side thumb button)`

`GP12(Default R1 button) - Button 8(Right side long button)`

`GP13(Default L1 button) - Button 1(Left side long button)`

`GP17(Default Start button) - Button 12(Right side square button)`

`GP18(Default Select button) - Button 11(Left side square button) `

### Important: Remember when you're soldering buttons on the faceplate with the face down, right and left will be switched, we've all made those mistakes.

## Assembly
1. Snap keyboard microswitches into plate sockets with pins facing south
2. Wire and fit halves together as outlined in the guide above
3. Once halves are flush together, start with middle screw and work your way from the outside corners in
4. Add keycaps to switches
5. Add some rubber electronics feet to the bottom of the case to prevent sliding, but keep height in mind so it doesn't sit too tall
6. Plug in and enjoy!

### Example 3D print - BambuLabs A1 with matte black filament
   ![Preview](ExamplePrint.jpg?raw=true "Preview Screenshot")
