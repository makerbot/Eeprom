#Write Test Results
This was a stress test to determine if writing to the EEPROM would cause corruption.

I wrote to the EEPROM 400 separate times, with each write consisting of a single byte who's value was its location on the EEPROM % 256.  After each set of writes, I pulled the EEPROM with AVRDUDE, then added that .hex file to git.  I then tried to commit my staged files.  It there were any deltas between files, git would have accepted the staged files. 

I started this test at 1800 hours on 2012-11-1 and left it running until 0900 on 2012-11-2.  While I had the git commit message report the iteration that caused the file difference, I forgot to output the iteration number at the start of the main For loop (a back-of the envelope calcuation gives us 7200 iterations: 7.5 seconds an iteration running for 15 hours) But, after I stopped this experiment there were no git commits, so no file differences were present.

While this isnt conclusive, it gives us a good indication that writing to the EEPROM does not cause corruption.
