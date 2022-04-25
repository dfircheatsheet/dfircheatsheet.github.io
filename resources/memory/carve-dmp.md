## Strings & grep

* Default: strings memory.dmp | grep -i pattern -A "# of line to show after the match"
* Little endian unicode: strings -e l memory.dmp | grep -i pattern -B "# of line to show before the match"
* big endian unicode: strings -e b memory.dmp | grep -i pattern -C "# of line to show after and before the match"
* specify length of characters: strings -n memory.dmp | grep -i pattern
* Print offset in file in hex: strings -tx memory.dmp | grep -i pattern

## Extract Event logs -> Refer to "Disk > Windows > Event logs" for further analysis.

* [EVTXtract](https://github.com/williballenthin/EVTXtract)
