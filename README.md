#Eeprom Tests
Test suites for EepromCorruption.  All these tests are of this form:

    * Do Some Action
    * Pull The EEPROM
    * Commit the Eeprom
    * Repeat as necessary

If there is no corruption, there should be no change log.  If there is, we should be able to track the .hex file's commit history and see what value shave changed.

#Write Tests
Writes a specific batch of information to the Eeprom.  Every tenth entry, we write a value to the eeprom.  That value is the index we are at mod 256.

#Power Cycle Tests
We power cycle the bot.  Uses a power tail with an arduino.
