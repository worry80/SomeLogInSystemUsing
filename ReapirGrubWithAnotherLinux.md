Firstly, mount all the partition we need.

----------------------------------------------------------
Next, mount the necessary part.

mount  --bind /proc /mnt/proc
mount  --bind /dev /mnt/dev
mount  --bind /sys /mnt/sys

----------------------------------------------------------
chroot /mnt

----------------------------------------------------------
grub-install --target=x86_64-efi --efi-directory={custom_dir} --bootloader-id={custom_name}

Sample:
    grub-install --target=x86_64-efi --efi-directory=/boot/efi --bootloader-id=Sakura-Manjaro

----------------------------------------------------------
If there is something wrong like this
        正在为 x86_64-efi 平台进行安装。
        EFI variables are not supported on this system.
        EFI variables are not supported on this system.
        grub-install：错误： efibootmgr failed to register the boot entry: 没有那个文件或目录.
        
mount --bind /sys/firmware/efi/efivars /mnt/sys/firmware/efi/efivars
