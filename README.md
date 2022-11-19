# qrencode-examples
Quick examples to create QR Codes from terminal using `qrencode`.
```
brew install qrencode
```
___
## WiFi connection string-
```bash
## Special characters escaped by `\` for example if SSID for your wifi is `HomeWifi`, authentication type is `WPA` 
## and password is `s3cure@thome`, you'd run folllwing to generate the image with pixel size 10 (default is 3)
# qrencode -o ~/wifi.png 'WIFI:S:HomeWifi;T:WPA;P:s3cure\@thome;;' -s 10
## Options for authentication type "T"- WEP, WPA, WPA2-EAP, or nopass
qrencode -o ~/wifi.png 'WIFI:S:{{SSID}};T:{{Auth-type}};P:{{Password}};;' -s {{PixelSize}}
```
___
## vCard-
```bash
cat <<EOF | qrencode -o "vcard.png" -s 10
BEGIN:VCARD
VERSION:2.1
N:Singh;Janpreet;;;
FN:Janpreet Singh
TITLE:DevOps Engineer
EMAIL:example@example.com
ADR;HOME:;;123, Street Address;City;State;Zip;Country
TEL;TYPE=cell:+1 0123456789
URL:https://janpreet.com
END:VCARD
EOF
```