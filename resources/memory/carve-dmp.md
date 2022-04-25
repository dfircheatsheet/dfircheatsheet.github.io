## Strings & grep

* Default: strings memory.dmp &#124; grep -i pattern -A "# of line to show after the match"
* Little endian unicode: strings -e l memory.dmp &#124; grep -i pattern -B "# of line to show before the match"
* big endian unicode: strings -e b memory.dmp &#124; grep -i pattern -C "# of line to show after and before the match"
* specify length of characters: strings -n memory.dmp &#124; grep -i pattern
* Print offset in file in hex: strings -tx memory.dmp &#124; grep -i pattern

## Extract Event logs -> Refer to "Disk > Windows > Event logs" for further analysis.

* [EVTXtract](https://github.com/williballenthin/EVTXtract)

## Data-Stream Carve (Extract Emails, Files, packets, .etc)

* [bulk-extractor](https://github.com/simsong/bulk_extractor)
* [bulk-extractor Manual](https://digitalcorpora.s3.amazonaws.com/downloads/bulk_extractor/BEUsersManual.pdf)
* [bulk-extractor GUI](https://github.com/simsong/BEViewer)
