# role 'console'

This role enables the serial console on the managed system.

NOTE: this supports only debian-7 (inittab)
      and ubuntu 9.10 to 14.04 (upstart)

      see https://help.ubuntu.com/community/SerialConsoleHowto
      for more information for earlier ubuntu variants


For centos7, serial console appears to work fine as-is if
you have /etc/default/grub containing the following:

'''
    GRUB_TIMEOUT=5
    GRUB_DISTRIBUTOR="$(sed 's, release .*$,,g' /etc/system-release)"
    GRUB_DEFAULT=saved
    GRUB_DISABLE_SUBMENU=true
    GRUB_TERMINAL="serial console"
    GRUB_SERIAL_COMMAND="serial --speed=115200"
    GRUB_CMDLINE_LINUX="vconsole.keymap=us rd.lvm.lv=centos_kvmtest/root rd.lvm.lv=centos_kvmtest/swap vconsole.font=latarcyrheb-sun16 crashkernel=auto  console=ttyS0,115200"
    GRUB_DISABLE_RECOVERY="true"
'''

If you edit this file, you need to generate the resulting /boot/grub2/grub.cfg
file by running:

'''
   grub2-mkconfig -o /boot/grub2/grub.cfg
'''


