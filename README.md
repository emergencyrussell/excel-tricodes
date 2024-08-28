# XLSX Trigram Codebook Generator

## *Output random pairings between two text files into two seperately alphabetized .XLSX files*

##### Based on NC Scout's book, *The Guerrilla's Guide to Baofeng Radio.*

#### *(Using the [OpenOTP32](https://github.com/emergencyrussell/OpenOTP32) just got a whole lot more efficient!)*

The script needs two text files with exact filenames (files included):

- First, **trigrams.txt**, consisting of all possible trigrams in the English alphabet, separated by line, reserving ZZZ to signify the end of a message.

- Second, **codedwords.txt**, consisting of the words presented in the sample codebook in *The Guerrilla's Guide,* , also separated by line.

Script uses the OpenPyXL library, which you may need to install:

```
pip install openpyxl
```

Utilizes Python's pseudo-random generation to randomize pairings and asks for a seed before shuffling. Refraining from entering a seed defaults it to zero. Hardware randomization can be entered in as the seed to increase security. For example, an ESP32 can be programmed to generate true random numbers into the Arduino IDE's Serial Monitor, which can then be copied and pasted into the seed prompt.

## Executing the Script

e.g. (in command prompt)

```
python excel-tricodes.py 10
```

Generates a spreadsheet consisting of ten encode/decode sheet pairs.

## Running the EXE

e.g. (in command prompt)

```
excel-tricodes 10
```

## Making a portable EXE file

Binary processed using PyInstaller. To make it yourself:

### Ensure pip is installed

Enter into command line:

```
python -m ensurepip
```

### Install PyInstaller

```
pip install pyinstaller
```

### Run PyInstaller on excel-tricodes.py

```
pyinstaller --onefile /path/to/excel-tricodes.py
```

Note that you will still need the two text files in the same directory or the binary will abort with an error.

## Usage

*Note: For secure usage, it is recommended to generate the seed, the pairings, and print the codebook pairs using air-gapped hardware.*

I run the script and paste a large random number into the seed, preferably with my hardware RNG. The script generates two .XLSX files. I open each in my spreadsheet software and export them as PDFs. I print the PDFs, four pages to a sheet, two copies. I then cut the sheets into fourths and staple the leaflets together into a four booklets, two encode booklets and two decode booklets. I deliver one encode/decode pair to my friend and we send secret messages. For extra security, we encrypt our messages using a pair of One Time Pad keys.