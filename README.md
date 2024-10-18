# fixing_uboot
<br>

# Fixing the terrible booting of RISC-V Boards.
<br>

**BPI-F3 Notes**
<br>
Banana Pi Dpcs <br>
echo 0 | sudo tee /sys/block/mmcblk2boot0/force_ro
sudo dd if=bootinfo_emmc.bin of=/dev/mmcblk2boot0
sudo dd if=FSBL.bin of=/dev/mmcblk2boot0 seek=512 bs=1
sync


**Lichee PI 4a** <br>

