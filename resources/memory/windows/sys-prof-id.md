### Volatility
   * [Identify System using Volatility](https://andreafortuna.org/2017/06/25/volatility-my-own-cheatsheet-part-1-image-identification/)
### Strings & Regex
   * `strings -e l memory.dmp | grep -E "[0-9.]+ Build [0-9]+"`
   * `strings memory.dmp | grep -E "Microsoft Windows [0-9]+ [A-Za-z]+"`
   * `strings -e l memory.dmp | grep -E "Microsoft Windows \[Version [0-9.]+\]"`
   * `strings memory.dmp | grep -E "PROCESSOR_ARCHITECTURE=[A-Za-z0-9]+"`
