- Normally the challenges will provde us a pcap file and tell us to decode the keystroke

- First, we need to filter the pcap file with only usb packet by using tshark command "tshark -r usb.pcap -Y "usb.transfer_type == 0x01" -Tfields -e usb.capdata > usbdata.txt"

- If done correctly, the usbdata.txt should be only contains Leftover Capture Data

- Lastly, we will use usb_keyboard_parser.py to parse the Leftover Capture Data into the input enter by the user

- Enter this command "python usb_keyboard_parser.py usbdata.txt"

### Extract Leftover Capture Data from pcap
```bash
$ tshark -r usb.pcap -Y "usb.transfer_type == 0x01" -Tfields -e usb.capdata > usbdata.txt"
```

### Usage of Python Script to parse the Leftover Capture Data
```bash
$ python usbkeyboard.py usbdata.txt
```
