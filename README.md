# DataDiveOT2
Notes, observations, and data from 1992 video game "Oregon Trail 2"

The end goal of this project is to understand the custom archive format used to store the resources used in game. (Aka, the structure of files such as OregonII.Dat and OregonII.Fst).

# Files
## Store Inventories.csv
Retrieved from OregonII.Fst around offset 0xf7fa67. Appears to hold information on the probability of finding a specific item at a shop, along with information regarding the price inflation of items as you go further west on the trail. The base price of items do not seem to be recorded here. Interestingly, horses seem to increase in value until halfway through the trail, where their value starts to rapidly decrease.

# Misc Notes
* One of Fst1/OregonII.Fst, Fst2/OregonII.Fst, or Fst3/OregonII.Fst will be installed when the user chooses a Full/Normal/Compact install, respectively.
* The first two bytes of OregonII.Fst are (01 4A)<sub>16</sub>. This is a pointer to a chunk of data that appears shortly later in the archive, which appears to be a folder index. This is followed by two null bytes, then (BE 02)<sub>16</sub>, which appears to also be a pointer to another chunk of data (of unknown purpose).
* Offset 0x000A contains 63 instances of (50)<sub>16</sub>, followed by a null byte, followed by 254 instances of (49)<sub>16</sub>. May be a magic number?
