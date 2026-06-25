Linux systems change the index number the esp32 is mounted after reboot, because the JTAG interface is integrated into the esp32 and gets restarted too when restarting the esp32. To aide platformIO to choose the correct device I've created an udev rule.

Simply put the udev rule file into your /etc/udev/rules.d/ directory, now the esp32 should always appear as /dev/ttyXIAO in platform.io