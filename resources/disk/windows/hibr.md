## Structure

* [Hiberfil.sys](https://forensicswiki.xyz/wiki/index.php?title=Hiberfil.sys)

## Analysis (for further analysis check “Memory -> Windows” section)

### [Hibernation Recon](https://arsenalrecon.com/downloads/)

### Volatility
* [hibinfo - reveals additional information stored in the hibernation file](https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#hibinfo)
* [imagecopy - allows you to convert any hibernation file to a raw memory image](https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#imagecopy)
```
1. $ vol.py -f hiberfil-eq.sys imageinfo
2. $ vol.py -f hiberfil-eq.sys --profile=Win7SPlx64 imagecopy -O eq.img
```
