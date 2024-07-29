# XLSX Trigram Codebook Generator

### *Based on NC Scout's book, The Guerrilla's Guide to Baofeng Radio*

#### Using the [OpenOTP32](https://github.com/emergencyrussell/OpenOTP32) just got a whole lot more efficient! :)

The script needs two text files with exact naming (files included):

- First, **trigrams.txt**, consisting of all possible trigrams in the English alphabet, separated by line, reserving ZZZ to signify the end of a message.

- Second, **codedwords.txt**, consisting of the words presented in the sample codebook in *The Guerrilla's Guide,* , also separated by line.

Utilizes Python's pseudo-random generation to randomize pairings and asks for a seed before shuffling. Refraining from entering a seed defaults it to zero. Hardware randomization can be pasted as the seed to increase security. For example, an ESP32 can be programmed to generate true random numbers into the Arduino IDE's Serial Monitor, which can then be copied and pasted into the seed field.

For secure usage, it is recommended to generate the seed, the pairings, and print the codebook pairs using air-gapped hardware.
