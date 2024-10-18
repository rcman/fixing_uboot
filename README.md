# fixing_uboot
<br>

# Fixing the terrible booting of RISC-V Boards.
<br>

**BPI-F3 Notes**
<br>
Banana Pi Docs <br><br>
echo 0 | sudo tee /sys/block/mmcblk2boot0/force_ro<br>
sudo dd if=bootinfo_emmc.bin of=/dev/mmcblk2boot0<br>
sudo dd if=FSBL.bin of=/dev/mmcblk2boot0 seek=512 bs=1<br>
sync<br>
<br>
<br>

**Lichee PI 4a** <br>

Their crap mothod <br><br>

sudo fastboot flash ram u-boot-with-spl-plastic16g.bin<br>
sudo fastboot reboot<br>
sleep 5<br>
sudo fastboot flash uboot u-boot-with-spl-plastic16g.bin<br>
sudo fastboot flash boot boot-console-20240529_143041.ext4u<br>
sudo fastboot flash root root-console-20240601_180941.ext4<br>
<br>


<br>





