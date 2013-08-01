# OpenLogic Micro

* [Build diagram](#build-diagram)
* [Renders](#board-renders)
* [Bill of Materials](#bill-of-materials)
* [EEPROM programming](#eeprom-programming)
* [License](#license)

##Summary

An open-source and open-hardware **Logic** analyzer based on the [Cypress CY7C68013A](http://www.digikey.com/product-detail/en/CY7C68013A-56PVXC/428-1627-ND/701273) chip.
At just over one square inch, this is one of the tiniest logic analyzers available.  At under about **$20 / unit** for parts (in small quantities), it's also
inexpensive, and it's fully compatible with popular logic analyzer software designed for the CY7C68013A chip.

New: [Order one from OSHPark!](http://oshpark.com/shared_projects/5RQmFbLg)

## Build diagram
[![Build diagram (pdf)](https://github.com/kuym/OpenLogicMicro/raw/master/BuildDocs/OpenLogicMicro-build-small.png "build diagram")](https://github.com/kuym/OpenLogicMicro/raw/master/BuildDocs/OpenLogicMicro-top.pdf)

OpenLogic Micro features components loaded on the top side only.  SSOP, SOT23, SOT223, 0805, 0603 and 0402 parts are used, along with a surface-mount USB connector and crystal.

## Board renders
![Front render](https://github.com/kuym/OpenLogicMicro/raw/master/BuildDocs/OpenLogicMicro-render-front.png "Front render")

![Rear render](https://github.com/kuym/OpenLogicMicro/raw/master/BuildDocs/OpenLogicMicro-render-rear.png "Rear render")

## Bill of Materials

OpenLogic Micro has a pretty simple BOM featuring all surface-mount parts.  The total cost for the BOM is under **$18** in small quantities.
If you acquire the Cypress FX2LP chip, the right crystal and micro-USB connector, the rest can virtually be built from junk-box SMD compoennts.

	C1       100nF 10V 0402                       CAP-0402-MIN                           0402-MIN                       
	C2       1uF 10V 0603                         CAP-0603-MIN                           0603-MIN                       
	C3       10pF 50V 0402                        CAP-0402-MIN                           0402-MIN                       
	C4       10pF 50V 0402                        CAP-0402-MIN                           0402-MIN                       
	C5       1uF 10V 0603                         CAP-0603-MIN                           0603-MIN                       
	C7       10uF 6.3V 0805                       CAP-0805-WIDE                          0805-WIDE                      
	C8       100nF 10V 0402                       CAP-0402-MIN                           0402-MIN                       
	C9       100nF 10V 0402                       CAP-0402-MIN                           0402-MIN                       
	C10      100nF 10V 0402                       CAP-0402-MIN                           0402-MIN                       
	C11      100nF 10V 0402                       CAP-0402-MIN                           0402-MIN                       
	C12      100nF 10V 0402                       CAP-0402-MIN                           0402-MIN                       
	C13      100nF 10V 0402                       CAP-0402-MIN                           0402-MIN                       
	C14      100nF 10V 0402                       CAP-0402-MIN                           0402-MIN                       
	C15      100nF 10V 0402                       CAP-0402-MIN                           0402-MIN                       
	F1       400mA PTC 0805                       PTC-0805-EXTRAWIDE                     0805-EXTRAWIDE                 
	IC1      CYPRESS-FX2LP-USB-HS-8051-CONTROLLER CYPRESS-FX2LP-USB-HS-8051-CONTROLLER   TSSOP56                        
	IC2      Microchip 24C00                      EEPROM-I2C-MCP-24AAXX/24LCXX           SOT23-5                        
	IC3      LM1117-3.3V SOT223                   LDO-REGULATOR-FIXED-NCP1117            SOT223-3                       
	IC4      ESD clamp chip (TBD)   		      TBD 									 SOT23-6                        
	IC5      ESD clamp chip (TBD)		          TBD                                    SOT23-6                        
	K1       FCI 10118193 MicroUSB                USB-5-PIN-MICROB-FCI-10118193-NARROW   USB-MICROB-FCI-10118193-NARROW 
	L1       3A 100R@100MHz Ferrite 0603          FERRITE-BEAD-0603-MIN                  0603-MIN                       
	L2       3A 100R@100MHz Ferrite 0603          FERRITE-BEAD-0603-MIN                  0603-MIN                       
	R1       2.2kΩ 0402                           RESISTOR-0402-MIN                      0402-MIN                       
	R2       2.2kΩ 0402                           RESISTOR-0402-MIN                      0402-MIN                       
	R3       10kΩ 0402                            RESISTOR-0402-MIN                      0402-MIN                       
	R4       10kΩ 0402                            RESISTOR-0402-MIN                      0402-MIN                       
	R5       47Ω 1% 0402                          RESISTOR-0402-MIN                      0402-MIN                       
	R6       47Ω 1% 0402                          RESISTOR-0402-MIN                      0402-MIN                       
	R7       47Ω 1% 0402                          RESISTOR-0402-MIN                      0402-MIN                       
	R8       47Ω 1% 0402                          RESISTOR-0402-MIN                      0402-MIN                       
	R9       47Ω 1% 0402                          RESISTOR-0402-MIN                      0402-MIN                       
	R10      47Ω 1% 0402                          RESISTOR-0402-MIN                      0402-MIN                       
	R11      47Ω 1% 0402                          RESISTOR-0402-MIN                      0402-MIN                       
	R12      47Ω 1% 0402                          RESISTOR-0402-MIN                      0402-MIN                       
	X1       NDK NX3225GA 24MHz                   CRYSTAL-4-PIN-NDK-NX3225GA             CRYSTAL-NDK-NX3225GA-3X2.5MM   

## EEPROM programming

The 24LC00 EEPROM on the board must be programmed per the [CY7C68013A datasheet](http://www.cypress.com/?docID=34060) with an appropriate USB identifier.
Use your own USB vendorID/productID pair or use a pair that's supported by the logic analyzer software you wish to use
(at your own risk, of course!)  The **!reset**, **vdd**, **gnd**, **scl** and **sda** test points on the bottom of the
board facilitate programming of the EEPROM - simply power the board through **vdd** and **gnd**, hold **!reset** low and
write configuration/USB ID bytes to the EEPROM with **sda** and **scl**.

## License

Licensed under [Creative Commons CC-BY-SA-3.0](http://creativecommons.org/licenses/by-sa/3.0/) unless otherwise specified.
