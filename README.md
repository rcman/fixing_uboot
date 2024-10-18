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
![image_play-6231803274eeb49587419621fa4e4f6f](https://github.com/user-attachments/assets/78be26f5-3525-45ee-8279-933993d6d3b0)

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
<br>

## Testing the build <br>
<br>

make qemu-riscv64_smode_defconfig

<br>
make menuconfig<br>
	CONFIG_ENV_IS_IN_FAT=y<br>
	CONFIG_ENV_FAT_INTERFACE="virtio"<br>
	CONFIG_ENV_FAT_DEVICE_AND_PART="0:1"<br>
 <br>
 Starting from Scratch - things to know  <br>
U-Boot<br>
 make qemu-riscv64_smode_defconfig
 <br>
 Start it<br>
 qemu-system-riscv64 -m 2G \<br>
-nographic \<br>
-machine virt \<br>
-smp 8 \<br>
-kernel u-boot/u-boot.bin<br>
Make the default kernel
<br>
make defconfig
<br>
make menuconfig
<br>
Now boot it. <br>
qemu-system-riscv64 -m 2G \<br>
-nographic \<br>
-machine virt \<br>
-smp 8 \<br>
-kernel linux/arch/riscv/boot/Image \<br>
-append "console=ttyS0" \<br>
<br>
Let’s create a 128 MB disk image:<br>
dd if=/dev/zero of=disk.img bs=1M count=128<br>
Size it<br>
cfdisk disk.img

 
 




