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

Their crap mothod <br>>

sudo fastboot flash ram u-boot-with-spl-plastic16g.bin
sudo fastboot reboot
sleep 5
sudo fastboot flash uboot u-boot-with-spl-plastic16g.bin
sudo fastboot flash boot boot-console-20240529_143041.ext4u
sudo fastboot flash root root-console-20240601_180941.ext4
<br>





