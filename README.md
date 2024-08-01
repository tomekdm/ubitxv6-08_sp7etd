04_sp7etd firmware update manual:

NOTE 1: Firmware originated from v6.3.1 Arduino sketch. For use with original ILI9341 320x240 TFT display.

NOTE 2: Mind to rename unpacked directory eg. "ubitxv6-04_sp7etd-master" to the same name as *.ino file (eg. "ubitx_v6_1_code_04_sp7etd")

NOTE 3: MIND!!! Just found issue with CW mode when in USB - Rx is shifted +1kHz in relation to TX. No issue with LSB. Please switch to LSB when in CW mode above 10MHz. I will try to fix it in next revision.

NOTE 4: There are several clones of Arduino nano. Some of them are not working properly with ubitx v6. Sometimes touch screen is not working, sometimes there are issues with flashing.

NOTE 5: Remember to perform FULL calibration after flashing (Set Freq (eg. 182000), Set BFO (eg. 11056.5) and also Tuch screen calibration, as touch will not work if not calibrated. To enter Setup menu press encoder button until Setup menu will appear (~10s).

Hello, I have bought ubitx v6 couple weeks ago and at beginning I was a little disappointed with CW performance and some functionalities. Decided to adjust it to my needs with default ILI9341 320x240 TFT display and then I have discovered beauty of this open project.

I would like to take this opportunity to thank the creator of this project Ashhar Farhan VU2ESE, as well as all the people thanks to whom this wonderful project lives and becomes better.

Today, when I am writing this text I am after couple days (during my May's holidays) with this rig. During this couple days I was able to make more than 50 QSOs (SSB, CW and some intercontinent DX - with 30W PA on 15m) while adjusting the firmware. Still some HW mods are planned to be made based on data from ubitx websites (AGC, CW audio filter, S-meter etc.).

These are some points summarizing my firmware mods:

1. jog tuning (digit tuning - usdx tuning style) implemented instead of dynamic tuning

By default jog position is set to 0.1 digit. Short press of the knob shifts jog position to the right (eg. to 0.01), pressing little longer shifts jog to the left (e.g. to 1, 10 and 100 respectively). Actual jog position is displayed at the bottom right corner of TFT screen (.01, .1, 1, 10 and 100). So, this firmware allows for 0.01 kHz step tuning while original firmware allows for 0.05 kHz minimal step.

2.  Discovered that function checking TFT touch screen is sometimes causing audio noises (possible due to SPI). With this firmware You can toggle function for scanning TFT touch ON/OFF with ~5 seconds press and release of the knob. Status of touch sensing is indicated by "t" letter at the lower right corner of TFT screen (just after jog position indicator).

3.  CW keying is modified. Discovered that start of CW TX is delayed and cutting out e.g. first dot in "R" letter (.-.) - first dot was not transmitted. Some mods were made and CW TX seems to be OK. now. Couple CW QSOs made with straight key.

4.  Additionally discovered that CW TX frequency was shifted by sidetone +/- depending if USB or LSB was selected. This shift was commented out and CW TX occurs now on displayed/selected frequency.

5.  Some cosmetic and SW stability changes e.g. to display pop ups - some pop up messages where shifted to improve cosmetics. Some stability issues found (original firmware was not working stable with my usb-c type arduino nano). Seems to be OK. now.

So, now last line shows: Shortened CW status (wpm and tone frequency without units), version and origin of updated firmware, jog position and TFT touch status - presence of letter "t" indicates touch sensing ON (absence OFF). Please don't blame me for sp7etd sign. Feel free to enter Your or project creator call sign (ubitx_ui.cpp file, line 443).

Summarizing, button knob has 5 functions now (depends on pressing time):

1) Short press - jog position to the right.
2) Little longer press - jog position to the left (jog position is displayed on the right bottom corner).
3) Knob press up to 5s - do commands as in origin firmware - jump with cursor through the menu.
4) Knob press between ~5s and 10s - toggle TFT touch sensing ON/OFF - sometimes SPI noise can be heard - so toggling touch OFF can help in RX.
5) Long ~10s press until Setup window appear - as in origin firmware

See 04_sp7etd_screenshot.jpeg file for menu overview.

Best regards.

Tomasz 
sp7etd 
4th May 2024, Poland
