## Writing configuration data to the I2C EEPROM

Write the following bytes to the I2C EEPROM in the system (a 24LC00) starting at address 0:

    C0 vv VV pp PP dd DD 00

Where:
- vv VV is USB vendor ID (`vv` is low byte, `VV` is high byte)
- pp PP is USB product ID (`pp` is low byte, `PP` is high byte)
- dd DD is USB device version (`dd` is low byte, `DD` is high byte)
