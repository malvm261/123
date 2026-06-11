root@malvm-Atlas-H256:/home/malvm/aic8800dc-linux-patched# chmod +x 
dkms.conf       fw/             .gitattributes  install.sh      README.md       tools/          update.sh       
drivers/        .git/           .gitignore      LICENSE         test.sh         uninstall.sh    
root@malvm-Atlas-H256:/home/malvm/aic8800dc-linux-patched# chmod +x install.sh 
root@malvm-Atlas-H256:/home/malvm/aic8800dc-linux-patched# ./install.sh 
##################################################
AIC8800DC Wi-Fi driver installer
Version: 6.4.3.0-patched.3
##################################################
[1/5] Installing firmware and udev rules...
[2/5] Preparing DKMS source tree...
[3/5] Registering with DKMS...
Creating symlink /var/lib/dkms/aic8800dc/6.4.3.0-patched.3/source -> /usr/src/aic8800dc-6.4.3.0-patched.3
[4/5] Building kernel modules (this may take a minute)...
Sign command: /usr/bin/kmodsign
Signing key: /var/lib/shim-signed/mok/MOK.priv
Public certificate (MOK): /var/lib/shim-signed/mok/MOK.der

Building module(s)...(bad exit status: 2)
Failed command:
make -j4 KERNELRELEASE=6.17.0-35-generic -C drivers/aic8800 KDIR=/lib/modules/6.17.0-35-generic/build
ERROR (dkms apport): binary package for aic8800dc: 6.4.3.0-patched.3 not found

Error! Bad return status for module build on kernel: 6.17.0-35-generic (x86_64)
Consult /var/lib/dkms/aic8800dc/6.4.3.0-patched.3/build/make.log for more information.
root@malvm-Atlas-H256:/home/malvm/aic8800dc-linux-patched# cat /var/lib/dkms/aic8800dc/6.4.3.0-patched.3/
build/  source/ 
root@malvm-Atlas-H256:/home/malvm/aic8800dc-linux-patched# cat /var/lib/dkms/aic8800dc/6.4.3.0-patched.3/build/make.log 
DKMS (dkms-3.2.0) make.log for aic8800dc/6.4.3.0-patched.3 for kernel 6.17.0-35-generic (x86_64)
Thu Jun 11 13:49:25 +04 2026

Building module(s)
# command: make -j4 KERNELRELEASE=6.17.0-35-generic -C drivers/aic8800 KDIR=/lib/modules/6.17.0-35-generic/build
make: вход в каталог «/var/lib/dkms/aic8800dc/6.4.3.0-patched.3/build/drivers/aic8800»
make -C /lib/modules/6.17.0-35-generic/build M=/var/lib/dkms/aic8800dc/6.4.3.0-patched.3/build/drivers/aic8800 ARCH=x86_64 CROSS_COMPILE= modules
make[1]: вход в каталог «/usr/src/linux-headers-6.17.0-35-generic»
make[2]: вход в каталог «/var/lib/dkms/aic8800dc/6.4.3.0-patched.3/build/drivers/aic8800»
warning: the compiler differs from the one used to build the kernel
  The kernel was built by: x86_64-linux-gnu-gcc (Ubuntu 15.2.0-4ubuntu4) 15.2.0
  You are using:           gcc (Ubuntu 15.2.0-4ubuntu4) 15.2.0
  CC [M]  aic8800_fdrv/rwnx_msg_tx.o
  CC [M]  aic8800_fdrv/rwnx_msg_rx.o
  CC [M]  aic_load_fw/aic_bluetooth_main.o
  CC [M]  aic8800_fdrv/rwnx_utils.o
In file included from <command-line>:
/usr/src/linux-headers-6.17.0-35-generic/include/linux/kconfig.h:5:10: fatal error: generated/autoconf.h: Нет такого файла или каталога
    5 | #include <generated/autoconf.h>
      |          ^~~~~~~~~~~~~~~~~~~~~~
In file included from <command-line>:
/usr/src/linux-headers-6.17.0-35-generic/include/linux/kconfig.h:5:10: fatal error: generated/autoconf.h: Нет такого файла или каталога
    5 | #include <generated/autoconf.h>
      |          ^~~~~~~~~~~~~~~~~~~~~~
In file included from <command-line>:
/usr/src/linux-headers-6.17.0-35-generic/include/linux/kconfig.h:5:10: fatal error: generated/autoconf.h: Нет такого файла или каталога
    5 | #include <generated/autoconf.h>
      |          ^~~~~~~~~~~~~~~~~~~~~~
compilation terminated.
compilation terminated.
compilation terminated.
In file included from <command-line>:
/usr/src/linux-headers-6.17.0-35-generic/include/linux/kconfig.h:5:10: fatal error: generated/autoconf.h: Нет такого файла или каталога
    5 | #include <generated/autoconf.h>
      |          ^~~~~~~~~~~~~~~~~~~~~~
compilation terminated.
make[5]: *** [/usr/src/linux-headers-6.17.0-35-generic/scripts/Makefile.build:287: aic8800_fdrv/rwnx_utils.o] Ошибка 1
make[5]: *** Ожидание завершения заданий…
make[5]: *** [/usr/src/linux-headers-6.17.0-35-generic/scripts/Makefile.build:287: aic8800_fdrv/rwnx_msg_tx.o] Ошибка 1
make[5]: *** [/usr/src/linux-headers-6.17.0-35-generic/scripts/Makefile.build:287: aic8800_fdrv/rwnx_msg_rx.o] Ошибка 1
make[4]: *** [/usr/src/linux-headers-6.17.0-35-generic/scripts/Makefile.build:544: aic8800_fdrv] Ошибка 2
make[4]: *** Ожидание завершения заданий…
make[5]: *** [/usr/src/linux-headers-6.17.0-35-generic/scripts/Makefile.build:287: aic_load_fw/aic_bluetooth_main.o] Ошибка 1
make[5]: *** Ожидание завершения заданий…
  CC [M]  aic_load_fw/aicbluetooth.o
In file included from <command-line>:
/usr/src/linux-headers-6.17.0-35-generic/include/linux/kconfig.h:5:10: fatal error: generated/autoconf.h: Нет такого файла или каталога
    5 | #include <generated/autoconf.h>
      |          ^~~~~~~~~~~~~~~~~~~~~~
compilation terminated.
make[5]: *** [/usr/src/linux-headers-6.17.0-35-generic/scripts/Makefile.build:287: aic_load_fw/aicbluetooth.o] Ошибка 1
make[4]: *** [/usr/src/linux-headers-6.17.0-35-generic/scripts/Makefile.build:544: aic_load_fw] Ошибка 2
make[3]: *** [/usr/src/linux-headers-6.17.0-35-generic/Makefile:2016: .] Ошибка 2
make[2]: *** [/usr/src/linux-headers-6.17.0-35-generic/Makefile:248: __sub-make] Ошибка 2
make[2]: выход из каталога «/var/lib/dkms/aic8800dc/6.4.3.0-patched.3/build/drivers/aic8800»
make[1]: *** [Makefile:248: __sub-make] Ошибка 2
make[1]: выход из каталога «/usr/src/linux-headers-6.17.0-35-generic»
make: *** [Makefile:56: modules] Ошибка 2
make: выход из каталога «/var/lib/dkms/aic8800dc/6.4.3.0-patched.3/build/drivers/aic8800»

# exit code: 2
# elapsed time: 20:00:01
----------------------------------------------------------------
root@malvm-Atlas-H256:/home/malvm/aic8800dc-linux-patched# 
