# Configuracion de relay

Para configuarar relay utilizaremos otra maquina debia y descargaremos el paquete.

- isc-dhcp-relay `$apt install isc-dhcp-relay`.
  
![instalar-raly](../img/instalar-relay.png)

*OMITIR EN CASO REAL* haremos cambiaremos el adaptardor red interna y en este caso apagaremos la maquina para añadir otro adaptadro pero esta vez con otra red para el lado 
del cliente que esta red tendra la net 192.168.2.0/24, importante que el adpatador del cliente este en modo promiscuo.

![adaptadores-relay](../img/adpatadores-relay.png)

- Luego procedemos a configurar la red desde el archivo "/etc/network/interface" en mi caso pongo como un enrutamiento para que todo vaya a la red de servidores 192.168.1.0/24.

![configuracion-red-relay](../img/configuracion-red-relay.png)

- Tambien tenemos que habilitar el renvio de paquetes de nuestra maquina debian, hay que cambiar un 0 por un 1 en "/proc/sys/net/ipv4/ip_forward" con `$echo "1" > /proc/sys/net/ipv4/ip_forward`
esto se aplicara temporalmente, una vez se reinicie la maquina estos cambios se borraran, para que no suceda modifica el archivo "/etc/sysctl.conf" y descomentaremos la linea "net.ipv4.ip_forward".

![ip_forward](../img/sysctl_conf.png)

- Reiniciamos la red para que se aplique con `$systemctl restar networking.service`.

- Una vez configurado las dos interfaces del relay con sus respectivas redes toca configurara el archivo "/etc/default/isc-dhcp-relay", donde tendremos que poner la ip de los servidores que escuchara nuestro realy, que seran los dos dhcp uno de ellos sinedo el de respaldo "Failover".

![configuracion-relay](../img/configuracion-raly.png)

y ya estaria listo nuestor servidor relay.
