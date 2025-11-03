# wled-apple-remote
### JSON for my Apple v1 Remote for WLED

Please ensure you change the 24-bit hex encoded integer (e.g. 0x77E11046) to the ones that work with your remote,
you can get that information by connecting the ESP32 to your computer and viewing the serial monitor (baud 115200)

Play/ pause cycles the presets 1 to 4, please change for your own use e.g. '{"ps":"1~5~r"}' '{"ps":"1~9~r"}'

If you want to have different values for brightness or other single or double clicks, you need to get the hex integer(s) (there are often multiple for a single or double click).

An examples is here, double is +30 and single is +10
```
 "0x77E1D047": { "label": "increase", "cmnt": "Brightness +30", "cmd": "A=~+30" },
 "0xFEA6EDF3": { "label": "up", "cmnt": "Brightness +10", "cmd": {"bri":"~+10"} },
```
The reason for the two different commands is that I was trying them out. Both work, so I left them as they were.

I don't use the left and right button as the project I did was for someone else and they only had a single colour LED.
Here are the left and right button effect changers, but please note, this are so many because my left and right buttons output several codes.
You will probably only need 1 or 2 hex codes for left/ right.
```
"0x77E11047": { "label": "left", "cmnt": "Effect -", "cmd": {"seg":{"fx":"~-"}} },
"0xA9303CAB": { "label": "left", "cmnt": "Effect -", "cmd": {"seg":{"fx":"~-"}} },
"0x3C9BEBD1": { "label": "left", "cmnt": "Effect -", "cmd": {"seg":{"fx":"~-"}} },
"0x75803297": { "label": "left", "cmnt": "Effect -", "cmd": {"seg":{"fx":"~-"}} },
"0x77E1E047": { "label": "right", "cmnt": "Effect +", "cmd": {"seg":{"fx":"~+"}} },
"0xDC2B74AC": { "label": "right", "cmnt": "Effect +", "cmd": {"seg":{"fx":"~+"}} },
"0x41B16E2D": { "label": "right", "cmnt": "Effect +", "cmd": {"seg":{"fx":"~+"}} },
"0x442B67D5": { "label": "right", "cmnt": "Effect +", "cmd": {"seg":{"fx":"~+"}} },
"0x4797D31B": { "label": "right", "cmnt": "Effect +", "cmd": {"seg":{"fx":"~+"}} },
```


**Don't forget, you MUST get your own 24-bit hex codes e.g. '0x4797D31B'
This JSON won't work for you as-is.**

If you want to view the codes on a seperate ESP32, you can use this code: https://github.com/sway/arduino-apple-remote
