<h1 align="center"> DHCP server tutorial</h1>

<img src="img/funcionamiento.png" align="center">

El DHCP (Dynamic Host Configuration Protocol) es un protocolo de red que asigna automáticamente direcciones IP y otros parámetros de configuración a los dispositivos en una red. Esto simplifica la administración de la red, ya que evita la configuración manual de las IPs en cada dispositivo.

#### Funcionamiento del Protocolo DHCP:
- Descubrimiento (Discover): Cuando un dispositivo (cliente) se conecta a la red, envía un mensaje broadcast solicitando una dirección IP.
- Oferta (Offer): Un servidor DHCP recibe la solicitud y responde ofreciendo una dirección IP disponible, junto con otros parámetros como la puerta de enlace (gateway) y el DNS.
- Solicitud (Request): El cliente responde aceptando la oferta de IP propuesta por el servidor.
- Confirmación (ACK): El servidor confirma la asignación, reservando la IP para ese cliente por un tiempo determinado (lease).
#### Funcionamiento del Servidor DHCP:
- El servidor DHCP almacena un rango de direcciones IP disponibles para la asignación. Cuando recibe una solicitud de un cliente, selecciona una IP libre y la envía al cliente junto con otros parámetros de red
- El servidor también controla el tiempo durante el cual cada dirección IP está asignada (lease), lo que garantiza que las IPs se liberen cuando ya no se utilizan.



----------------------------------------------------------------------------------------------------------

## Tutorial de como hacer un servidor dhcp con relay y failover

Utilizaremos una red con 2 subredes una con la net 192.168.1.0/24 y otra con la net 192.168.2.0/24

![topologiaRed](img/esquema_de_red.png)

- [Configuracion DHCP](doc/configuracion-dhcp.md)

- [Configuracion relay](doc/configuracion-relay.md)

## Licencia
<p xmlns:cc="http://creativecommons.org/ns#" >Esta obra está licenciada bajo <a href="https://creativecommons.org/licenses/by-nc/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">CC BY-NC 4.0<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" <img style="altura: 22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/nc.svg?ref=chooser-v1" alt=""><img style="altura: 22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/nc.svg?ref=chooser-v1" alt=""></a></p>
