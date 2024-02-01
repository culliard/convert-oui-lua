# Introduction
<br>The purpose of this script was driven by the need to update the arp-scan OUI database on OpenWRT (get-oui was not available)
<br>The script converts OUI data in json format to text that can be used by arp-scan.
<br>Lua is available on OpenWRT 22.03 by default

## Setup

### Install dependencies
```
opkg update
opkg install dkjson
```

### Download this script
`
wget -4 https://raw.githubusercontent.com/culliard/convert-oui-lua/master/convert-oui.lua
`

### OUI Json data
`
wget -4 https://raw.githubusercontent.com/silverwind/oui-data/master/index.json
`

## Convert Data

### Change permissions
`
chmod 755 convert-oui.lua
`
### Run
The script will take a few minutes to complete depending on the hardware resources available
<br>
`./convert-oui.lua`

### Move file
If arp-scan-database is installed then update the file
<br>
`
mv ieee-oui.txt /usr/share/arp-scan/ieee-oui.txt
`
