# 1	Introducción
En el presente trabajo tiene como finalidad la creación de una guía para la administración del sistema operativo de Linux es este caso correspondería a la versión de 	OpenSuse 42.3, en el cual se mostrarán los comandos necesarios para realizar las modificaciones desde el terminal.
Se comenzara desde la instalación del sistema operativo en el disco duro, tomando nota de las particiones que este tendrán. Luego de la instalación se procederá a la creación de un usuario sudo (post-instalación), en el cual se realizara por comandos en el terminal, que estará debida mente documentado en el informe. A su vez, se procederá con la configuración de la red del equipo en el cual se le asignara una IP al equipo cada vez que se inicie de forma automática, también se configurará la red local del el equipo anfitrión con el SO huésped (maquina virtual). Luego se procederá con la instalación y habilitación (al iniciar) de un servidor web para el equipo. Ya terminado la habilitación del servidor web se procederá con la Instalación, configuración y habilitación del firewall del sistema operativo para el servidor web pueda funcionar sin problemas. 
Cabe de indicar ya realizado todos los pasos anteriores se procederá con la instalación, habilitación y configuración del reloj del sistema operativo mediante un programa externo. 
Una vez hecho el paso anterior se procederá a explicar para hacer modificaciones y como funciona en el sistema de arranque en el sistema operativo de Linux ( grub , lilo).
Para el presente trabajo se instalara el programa Putty, en el cual utilizaremos para probar el servicio del SSH del sistema. También se instalara el programa Filezila para probar el servicio de FTP del equipo. 

# 2	Instalación del Sistema operativo.

Para la instalación del OpenSuse de arquitectura de 64 bit, en primer lugar se debe de tener habilitado la vitalización el procesador del equipo anfitrión de la máquina virtual.
Para la instalación se ocupará el virtual box para la creación y gestión de la maquina virtuales, para la creación de una nueva máquina se selecciona el botón de nuevo, después se le asigna unos 2 gb de memoria Ram para la máquina, después se crea un nuevo disco duro virtual para la maquina seleccionando el formato de VDI (virtualbox disk imagen).
La cantidad de espacio asignado al equipo será de 10 Gb con el entorno grafico (escritorio). Una vez terminado ello se procede a configurar el procesador para la habilitación de las características del PAE/NX.
# OpenSuse
