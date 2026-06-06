
# keychainserver

This is the code for a website running on an esp32-c3 accessible via a dedicated wlan. It is intended as a fun little gadget.

## features

The esp32 c3 creates own wlan according using ssid and passwort provided by config.txt. It hosts a static website (/) stored on the sd-card in the folder www, a static game can be hosted (/game/) and the highscore is stored globally on the sd-card and dditionally a guestbook can be hosted (wip).

## requirements

### electronics:

1x Xiao seeed esp32-c3
1x SPI microSd-card adapter
1x Li-Ion battery (optional)
1x switch (optional)
1x microSd card (4Gb+)

### case:

1x m4 hook
1x m4 locking nut
1x washer

### tools:

cables
soldering iron
3d printer (for case)
platformIO (to program esp32c3)

### soldering plan:

    SPI        ESP32
    3V3   ----   3V3
    CS    ----    D7
    MOSI  ----   D10
    CLK   ----    D8
    MISO  ----    D9
    GND   ----   GND                  BATTERY
               BAT + ---- SWITCH ----     red
               BAT - ---- ------ ----   black

Solder corresponding pins from SPI SD Card Module to ESP32 C3. Solder red battery wire to switch then solder switch to bat + on esp32. Solder black battery wire to bat - on esp32. Keep switch in off position to prevent accidental short circuiting.

Program esp32 with platformio, format microSD-Card to FAT32 or exFAT and copy at least config folder (config website handling) and www folder (location for static website).

Test assembly.

If everything works put it in case and fix it with your method of choice (i.e: hot glue).

### possible expansions

- add LED to show that server is running
- add voltag divider to adc PIN to read battery level to show level on website