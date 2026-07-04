# Kenwood codeplug guide for simplex hotspot

## WARNING

- There may (or may not) be passwords and codes related to the Kenwood Nexedge radio product.  It is your sole responsibility to maintain those in safe keeping.  I am not responsible for any damage to your radio or violation of rights of your doings.

## Steps

### Step 1: Prepare the software

1. Open your copy of Kenwood CPS.

2. Plug in the radio to your PC.

3. Load the current radio programme (optional).

### Step 2: Configure NXDN

1. Navigate to _Edit_ > _NXDN_.  The _NXDN_ window appears.

![That's CPS toolbar _Edit_, then _NXDN_ inside the _Edit_ menu.](/images/KCPS_Edit_NXDN.png)

2. Under _General 1_ tab, enter _Unit ID (Own)_ with the obtained NXDN ID from RadioID, and _Unit ID Name (Own)_ with your callsign (of course it is the one you get your ID with).

![Example populated NXDN ID and callsign of my own.](/images/KCPS_NXDN_General1.png)

3. Under _Conventional_ tab, change _Premable Length_ to a desired value, maximum is 254.  This setting affects how the hotspot can detect the NXDN radio frame, so I leave at 254 for now.

![_Preamble Length_ at 254 for example configuration, and also works best](/images/KCPS_NXDN_Preamble.png)

4. For _Unit ID List_, just fill in the NXDN ID of people you know.  It allows you to identify the incoming caller on the display, or allow you to make private call to that person later.

![Standard populated entry for _Unit ID List_](/images/KCPS_NXDN_idlist.png)

5. Fill the _Group ID List_ with any NXDN reflectors you want to connect.  You can find a number of public refectors under [DVRef.com](https://dvref.com/nxdn/) or [PiStar.uk](https://www.pistar.uk/nxdn_reflectors.php).  You should also add Group IDs `10` (parrot) and `9999` (unlink), as it allows you to test your NXDN radio without messing with others and unlink from reflectors from your radio.  As for Group ID `20`, it is for NXDN2DMR service, which will be covered under a separate guide.

![Example list of Group IDs filled](/images/KCPS_NXDN_groups.png)

6. Close the _NXDN_ window.

### Step 3: Key mapping

This step allows you to later access those reflector IDs aforementioned.  Now it is not strictly what key you selected, as long as you remember it to navigate from your Kenwood radio, that's all.

1. Navigate to _Edit_ > _Key Assignment_, and _Key Assignment_ window appears.

![That's _Edit_ menu of Kenwood CPS, and select _Key Assignment_ from the drop down.](/images/KCPS_Edit_Keys.png)

2. Under _Panel_ tab, set the _Function_ for desired keys with `Group (NXDN)`, `Individual (NXDN)`, `CH/GID Up`, `CH/GID Down`, `Zone Up` and `Zone Down`.  For me, I ommitted the `Individual (NXDN)` , because I don't need it.

![One configuration of _Key Assignment_](/images/KCPS_Keys_Panel.png)

3. Close the _Key Assignment_ window.

Further, you can add whatever functions to whatever keys you want.  You can even configure the _Mic Key_, if you have a keypad mic SKU.  As for handheld versions, it may be entirely different.  As I've said, your mileage may vary.

### Step 4: Zones and Channels

1. There should be _Zone Information_ window already there.  If not, navigate to
_Edit_ > _Zone Information_.

![Zone Information window with populated channel](/images/KCPS_ZoneInfo.png)

2. Under _Zone Infomation_ window, press _Zone Edit_.

3. Ensure that _Audio Control (NXDN)_ is set to `RAN`.  When you done, press _Close_.

![Zone Edit window with configured Audio Control](/images/KCPS_Zone.png)

4. Now press _Channel Edit_ under _Zone Information_ window.

5. For simplex, enter the same frequency that you configured with Pi-Star into both _TX Frequency_ and _RX Frequency_ (beware the decimal places and your radio frequency resolution, you may have to adjust Pi-Star to match your radio frequency).  Set _RAN Decode_ and _RAN Encode_ to the NXDN RAN that you configured with Pi-Star (this is similar to color code on DMR).  Double check to see that _Selcall on PTT (NXDN)_ is set to off.  Name your channel, adjust the power then press _Close_.

![An example simplex channel setup.](/images/KCPS_Channel.png)

To add more channels, repeat steps 4 and 5, but change the channel number before doing step 5.  As far as I can see, adding more channels only make sense if you intend to connect to multiple NXDN repeaters in your area and your hotspot; or that you have many hotspots.  Most of the time, to change talkgroup (aka reflectors), you would normally operate that with the `Group (NXDN)` key you preprogrammed earlier.

Under _Channel Edit_, you may adjust _Channel Spacing (NXDN)_, _Busy Channel Lockout (NXDN)_ and _Optional Signalling (NXDN)_

### Step 5: Plug it in!

Everything now completed for the plugging those codes onto your Kenwood radio.  Press that write button (the one with the PC with arrow going out), and follow the codeplug writing instruction of the software.

![The PC with arrow going out icon.](/images/KCPS_Write.png)

### Step 6: Test it out!

The radio should be on by now, so navigate to the zone of your choice (if you only have one zone when you codeplug the radio, no need).  Now navigate to the NXDN channel of choice (that's the `CH/GID Up` and `Down` keys previously assigned), then press your assigned `Group (NXDN)` key.  Choose the talkgroup/reflector with the assigned `Zone Up`/`Zone Down` key (please let me know if that's not the case), and press the PTT button for approximately 2 seconds (depending on how you set the _Preamble_ by the bye).  If success, there would be an announcement by `UID 9999` on your radio saying `Linked to <digits of the talkgroup>` and you should be hearing the traffic from that talkgroup/reflector.

Please be mindful when joining a talkgroup or reflector.  This is an excellent guide on ettiquette made PAPA Systems that I found useful: [The **_PAPA Smooth Operator Guide_** featured on their main page, along with other great guides](https://papasys.com/).

## Troubleshooting

Your hotspot not hearing you?  That's a problem many will encounter one way or another when operating with Digital voice, and NXDN is no exception.

BUT FIRST, ask yourself two questions:

- Have I tried setting the radio premable to its maximum yet?
- And, are the frequencies the same between my radio and my hotspot?

If not yet, then get to it, see if it makes any difference.

If not, then it is a case of frequency drifting, that can easily be adjusted from the hotspot.  I would recommend searching the Internet for guides and select which one is the best for you.  For me, from a guide that I would love to recall where, I would select the average frequency between the highest and lowest point where the hotspot can no longer decode the radio stream (all of this was done using `pistar-mmdvmcal` or `wpsd-modemcalibrate`, which is prominently featured in all of the Internet guides).

Hopefully, these resolutions should help you get started on Kenwood NXDN over hotspot.  Otherwise, we will have to go down the rabbit hole, then...

