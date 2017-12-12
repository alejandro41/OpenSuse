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


Lo primero que debemos hacer, es ingresar como root desde la consola de Linux. Para hacer esto, una vez abierta la consola, tecleamos el siguiente comando:  
 $ su 
y nos pedirá nuestra contraseña para ingresar. Una vez activados los privilegios de root, procedemos a crear una nueva cuenta de usuario. Para hacerlo, escribimos el siguiente comando desde el terminal de Linux:
# useradd andres

El nombre del usuario será Andres, al cual le estamos creando la cuenta. Una vez creado el nombre de usuario, su cuenta estará activa, el siguiente paso es crearle una contraseña, para hacerlo sólo debemos teclear el comando:
# passwd andres


 -----------------------------
<img src="https://github.com/alejandro41/OpenSuse/blob/master/imagenes/imagen7.jpg">

---------------------------------

The password will be 334599 and must be entered twice to verify it. If the procedure was successful, the new user account and password have already been created and are active.

# 4	Configuración de la red (que asignar Ip automáticamente al iniciar). 

Primero se comprueba la Ip del equipo con el que cuenta mediante el siguiente comando.
Ip addr


 -----------------------------
<img src="https://github.com/alejandro41/OpenSuse/blob/master/imagenes/imagen8.jpg">

---------------------------------


The ip corresponds to the digit of 127.0.0.1/8
Once we have identified our ip, we edit the interfaces file located in the following folder.
/ etc / sysconfig / network

# 5	Instalación y habilitación (al iniciar) de un servidor web 


Para la instalación del servidor web ocuparemos el apache por consola con el siguiente comando:
apt-get install apache2

El cual débenos de ejecutarlo como root del sistema y ingresando nuestra contraseña para continuar.


-----------------------------
<img src="https://github.com/alejandro41/OpenSuse/blob/master/imagenes/imagen9.jpg">

---------------------------------

The server installation is finished,

For the graphical installation of the apache server we go to the control panel / yas. Once logged in we must check that the patterns tab and select web server and lamp.


-----------------------------
<img src="https://github.com/alejandro41/OpenSuse/blob/master/imagenes/imagen10.jpg">

---------------------------------


Which will start the download and installation automatically. Once finished with the installation.


# 5.1	Habilitación del DNS

Antes de comenzar con la instalación del apache comenzamos con la configuración del dns en nuestro open susen, para ello debemos de tener habilitado nuestra segunda conexión con nuestra maquina anfitriona.


-----------------------------
<img src="https://github.com/alejandro41/OpenSuse/blob/master/imagenes/imagen11.jpg">

---------------------------------

Once our second local network has been created, proceed with the configuration. We go to the control panel to the system administration option (YasT), enter our password and go to network services, select DNS server. It should be noted that for this we must enable the bridge adapter of our host machine.


-----------------------------
<img src="https://github.com/alejandro41/OpenSuse/blob/master/imagenes/imagen12.jpg">

---------------------------------

We enter the control panel to install software and download the dns and yast2-dns-server plugins that are necessary for the configuration of our dns, since these add-ons are installed, we proceed with the configuration of the network.
We go to network settings, in global options the wicked service is selected.


-----------------------------
<img src="https://github.com/alejandro41/OpenSuse/blob/master/imagenes/imagen13.jpg">

---------------------------------

Then we select the summary view option and edit, placing statically assined IP address 10.19.0.100 with subnet mask 255.255.0.0 and the host name as tes1, after that we give the following which ends up applying the changes.


-----------------------------
<img src="https://github.com/alejandro41/OpenSuse/blob/master/imagenes/imagen14.jpg">

---------------------------------


Once the previous step is finished, we go back to the dns server configurator, enter dns zones and assign the zone that will be luis12.com corresponding to the master type we will add.

-----------------------------
<img src="https://github.com/alejandro41/OpenSuse/blob/master/imagenes/imagen15.jpg">

---------------------------------


We have already added it, selecting the option of Records (Records) NS and adding the above mentioned address which will be opens.luis12.com and we will add it.
In the SOA option we select the minimum for 3 hours.


-----------------------------
<img src="https://github.com/alejandro41/OpenSuse/blob/master/imagenes/imagen16.jpg">

---------------------------------

And we go to registries, in registry key we added with the ip 10.16.18.6, we repeat the above with the name of fedora with the ip 10.16.18.7. Then we add the router cone type CNAME: alias for the domain name with name ipcop and we add it.
Repeat the previous step with ftp with the value wsk3 and add it, ns1 with value w2k8, mail with the value should, www with fedora value. Now we add an MX record with priority 1 with the value of must and accept.


-----------------------------
<img src="https://github.com/alejandro41/OpenSuse/blob/master/imagenes/imagen17.jpg">

---------------------------------

Then we create a new network that is reverse with the following syntax with the one we are going to work with but the other way around. 18.16.10.in-addr.arpa of the master type and we add it. After we edit it, we go to registers Ns and add opens.luis12.com and we add it.


-----------------------------
<img src="https://github.com/alejandro41/OpenSuse/blob/master/imagenes/imagen18.jpg">

---------------------------------


Then we go to SOA and place at least 3 hours, then we go to records and

We assign the name of lius.com as address and add as master type.


-----------------------------
<img src="https://github.com/alejandro41/OpenSuse/blob/master/imagenes/imagen19.jpg">

---------------------------------


# 6 Installation, enabling and configuration of the firewall

Since Open suse account already has an already installed firewall called SuSEfirewall2, which will be shown below the basic options that can be done by command.
Deactivate the firewall manually and from the console: $ su
                                                                                          Parsword:
                                                                                         / sbin / SuSEfirewall2 stop

An example would be to Enable ports 4662 (TCP) and 4672 (UDP). For this we must open the following file as super user.

/ etc / sysconfig / SuSEfirewall2

Now we look for the phrase FW_SERVICES_EXT_TCP and FW_SERVICES_EXT_UDP Now we open the ports, writing the following:
FW_SERVICES_EXT_TCP = "4662"
FW_SERVICES_EXT_UDP = "4665 4672"

To enable SuSEFirewall2, use sudo systemctl enable SuSEfirewall2 or use the YaST Services Manager module.

FW_DEV_EXT (firewall, masked)

The device linked to the Internet. For a modem connection, enter ppp0. DSL connections use dsl0. Specify auto to use the interface that corresponds to the default route.

FW_DEV_INT (firewall, masked)

    The device linked to the internal and private network (such as eth0). Leave this blank if there is no internal network and the firewall protects only the host on which it is running.

FW_ROUTE (firewall, masked)


For an unmasked security server, set this to itself if you want to allow access to the internal network. Your internal hosts need to use officially registered IP addresses in this case. Normally, however, you should not allow access to your internal network from the outside.
FW_MASQUERADE (masked)

 Set this to yes if you need the masking function. This provides a virtually direct connection to the Internet for internal hosts. It is safer to have a proxy server between the hosts of the internal network and the Internet. Masking is not necessary for the services provided by a proxy server.

FW_MASQ_NETS (masked)

 Specify the hosts or networks to be masked, leaving a space between the individual entries. For example:

 FW_MASQ_NETS = "192.168.0.0/24 192.168.10.1"

FW_PROTECT_FROM_INT (firewall)

 Set this to yes to protect your firewall server from attacks originating from your internal network. Services are only available for the internal network if they are explicitly enabled. Also see
FW_SERVICES_INT_TCP and FW_SERVICES_INT_UDP.
FW_SERVICES_EXT_TCP (firewall)

 Enter the TCP ports that should be available. Leave this blank for a normal work station in the home that should not offer any service.

FW_SERVICES_EXT_UDP (firewall)

Leave this blank unless you are running a UDP service and want it to be available for the outside. Services that use UDP include DNS servers, IPsec, TFTP, DHCP and others. In that case, enter the UDP ports to use.

FW_SERVICES_ACCEPT_EXT (firewall)

 List of services to allow from the Internet. This is a more generic form of the FW_SERVICES_EXT_TCP and FW_SERVICES_EXT_UDP configurations, and more specific than FW_TRUSTED_NETS. The notation is a list separated by NET slots, PROTOCOL [, DPORT] [, SPORT], for example 0/0, tcp, 22 or 0/0, tcp, 22, hitcount = 3, block seconds = 60, recent name = ssh, which means: allows a maximum of three SSH connections per minute from an IP address.
 
 FW_SERVICES_INT_TCP (firewall)

With this variable, define the services available for the internal network. The notation is the same as for FW_SERVICES_EXT_TCP, but the configuration is applied to the internal network. The variable only needs to be set if FW_PROTECT_FROM_INT is set to yes.

FW_SERVICES_INT_UDP (firewall)

FW_SERVICES_INT_TCP.
FW_SERVICES_ACCEPT_INT (firewall)

    List of services to allow from internal hosts. See FW_SERVICES_ACCEPT_EXT.
FW_SERVICES_ACCEPT_RELATED_ * (firewall)

This is how the implementation of SuSEFirewall2 considers the packages RELATED by netfilter.

 For example, to allow finer granulation filtering of the Samba broadcast packets, the related packets are not unconditionally accepted. The variables that start with FW_SERVICES_ACCEPT_RELATED_ allow to restrict the handling of RELATED packets to certain networks, protocols and ports.

This means that adding conntrack modules to FW_LOAD_MODULES does not automatically result in accepting packets tagged by those modules.
 In addition, you must set variables that begin with:
FW_SERVICES_ACCEPT_RELATED_ to an appropriate value.
FW_CUSTOMRULES (firewall)

this variable to install custom rules. Find examples in
/ etc / sysconfig / scripts / SuSEfirewall2-custom.

Firewall rule sets are created by entering systemctl start SuSEfirewall2 as root.

# 7 Synchronization setting of the system clock.

For the configuration and synchronization of the system clock, we will work with time crony. It must be installed for the OpenSuse version corresponding to 42.2 per command following the following syntax.

zypper addrepo https://download.opensuse.org/repositories/network:time/openSUSE_Leap_42.3/network:time.repo
zypper refresh
zypper install chrony

To enable and start it, the following command is used:
// systemctl start chonyd and systemctl status chronyd.

To check that the system is used to synchronize, the following syntax is used:
# timedatectl | grep''NTP synchronized''

To enable it is:
 
# timedatectl set-ntp yes
To select the corresponding time zone, it is
 Timedatectl list-timezones

Occupying grep to find the capital of chile, once found, the following syntax is applied:
Timedatectl set-timezome "Time zone".

# 8 Modifications to the operating system boot system.

To make changes in the start of open suse the grud will be taken care of. To select one as the default, and how to make the initial wait shorter. It can be done by modifying the corresponding file from a text editor. But since open SUSE has Yast, we will use this to do it graphically. The following screenshots show how to follow these simple steps.
or first open Yast, select System and Boot loader, in this screen we will see the different options of the different Kernels that we have installed. To select one as default when booting, select it and check the box Set by default, and we will see how it is marked to be the initial when starting by default. From this screen we can also reorder the entries, raising or lowering them, or even eliminating them.


 
 -----------------------------
<img src="https://github.com/alejandro41/OpenSuse/blob/master/imagenes/imagen21.jpg">

---------------------------------
 
 
 To reduce the waiting time before selecting the boot we can do it by clicking on the Installation tab of the boot loader, there we select Boot Loader Options and find where to modify the initial waiting time.
 
 
-----------------------------
<img src="https://github.com/alejandro41/OpenSuse/blob/master/imagenes/imagen22.jpg">

---------------------------------


-----------------------------
<img src="https://github.com/alejandro41/OpenSuse/blob/master/imagenes/imagen23.jpg">

---------------------------------


With this we can modify the start of our open susen in a total graphic mint.


# 9 Install and test SSH service

For the test of the SSH service, PuTTY will be installed, since it is only necessary to download the execution file from the following page: https://software.opensuse.org/download.html?project=openSUSE%3AFactory&package=putty
Or execute the following syntax as super administrator.
Sudo su
Enter password




