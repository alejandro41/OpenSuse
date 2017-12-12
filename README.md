# . Introduction
In this work has the purpose of creating a guide for the administration of the Linux operating system in this case would correspond to the version of OpenSuse 42.3, which will show the commands necessary to make the changes from the terminal.
It will start from the installation of the operating system on the hard disk, taking note of the partitions it will have. After the installation, a sudo user will be created (post-installation), in which it will be performed by commands in the terminal, which will be duly documented in the report. In turn, we will proceed with the configuration of the computer network in which an IP will be assigned to the computer each time it is started automatically, the local network of the host computer will also be configured with the guest OS (virtual machine ). Then proceed with the installation and enabling (when starting) a web server for the team. Once the web server has been enabled, the installation, configuration and activation of the operating system firewall for the web server will work without problems.
It is necessary to indicate that once all the previous steps have been carried out, the installation, enabling and configuration of the operating system clock will be carried out by means of an external program.
Once the previous step is done, it will proceed to explain to make modifications and how it works in the boot system in the Linux operating system (grub, lilo).
For the present work, the Putty program will be installed, in which we will use to test the SSH service of the system. The Filezila program will also be installed to test the FTP service of the equipment.

# 2 Installation of the operating system.

For the installation of the 64 bit architecture OpenSuse, the processor of the host computer of the virtual machine must be enabled in the first place.
For the installation the virtual box for the creation and management of the virtual machine will be occupied, for the creation of a new machine the button is selected again, after it is assigned about 2 gb of RAM memory for the machine, then a new virtual hard disk for the machine by selecting the VDI format (virtualbox disk image).
The amount of space allocated to the equipment will be 10 Gb with the graphic environment (desktop). Once this is done, the processor is configured to enable PAE / NX characteristics.


-----------------------------
<img src="https://github.com/alejandro41/OpenSuse/blob/master/imagenes/imagen1.jpg">

---------------------------------

Once finished, we proceed with the installation of So, selecting the Spanish language for it.

-----------------------------
<img src="https://github.com/alejandro41/OpenSuse/blob/master/imagenes/imagen2.jpg">

---------------------------------

Once the OS is loaded, we proceed with the configuration of the keyboard language selected in the Spanish language, given that it does not have the option of the Latin American keyboard and the option is given to continue arriving at the option of partitioning the local unit, which we select the advanced option for configuration of the installation.


-----------------------------
<img src="https://github.com/alejandro41/OpenSuse/blob/master/imagenes/imagen3.jpg">

---------------------------------

Once entered into the configuration of the installation, we observe the different partitions that by default the operating system delivers which are in the following image.


-----------------------------
<img src="https://github.com/alejandro41/OpenSuse/blob/master/imagenes/imagen4.jpg">

---------------------------------

The / dev / sda partition is the whole unit which is recognized by the operating system.
The unit will be divided into two logical units, the first unit which will have 2gb of agitated space which will be of Swap format, which will comply with the function of virtual memory of exchange.


Then we move forward with the installation, we request the corresponding time zone that in this case would correspond to the continental chile, after that we give in advance, the installation program will ask us to select the graphic environment to work which gives us two options which are the desktop with KDE Plasma and desktop with gnome, we select the first option for the installation and we give it to next. Which we must create the local user of the machine with the user name, in this case we will assign the name of Luis with the following password 334030 which we give you the option to use this password for the system administrator plus the option of automatic login and we start with the execution n of the installation.


-----------------------------
<img src="https://github.com/alejandro41/OpenSuse/blob/master/imagenes/imagen5.jpg">

---------------------------------

# Instalación de usuario sudo post instalación

 Una vez terminado con la instalación del sistema operativo, procederemos con la instalación de un usuario sudo por comandos primero abrimos la consola de comando del OpenSuse.
 
 -----------------------------
<img src="https://github.com/alejandro41/OpenSuse/blob/master/imagenes/imagen6.jpg">

---------------------------------



