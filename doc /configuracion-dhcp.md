### Coniguracion de servidor DHCP

Para Configurar este servidor utilizare un debian 12 en virtualbox y utilizaremos dos redes interna para hacer esta estructura de red. Pero primero tendremos que tener internet para descargar lo necesario para levantar el dhcp siendo este.
 - isc-dhcp-server ''' apt install isc-dhcp-server '''
![isc-dhcp-server](img/isc-dhcp-server.png)

*OMITIR EN CASOS REAL* Despues de instalar el paquete necesario para el servidor pondremos la red en modo red interna desde virtualbox.
![red-interna](img/poner_red_en_interna.png)

Configuaremos el archivo "/etc/network/interface" para darle una ip statica y importante un enrutado hacia la red que necesitamos en mi caso 192.168.2.0/24

![net-dhcp-server](img/conf-adpatador.png)

Reiniciamos la red para que nos actualize nuetra configuracion. 
- ''' $systemctl restart networking.service '''

Este servicio de por si solo no iniciara dara fallo por que hay que idicarle algunos parametros en dos archivos de coniguracion que son 

 - "/etc/default/isc-dhcp-server" En este archivo lo dejaremos con las lineas descomentadas igual que en la imagen y a;adiremos nuestro nombre de adaptador de red en la liena que pone "INTERFACESv4=". Os dejo el archivo -[a qui]()
   
      ![conf1](img/conf1.png)
   
 - "/etc/dhcp/dhcpd.conf" En este archivo es lo mas importante ya que en este pondremos como el servidor dhcp trabajara a si como las conseciones de ip que realizara os dejare como configuro el elachivo -[a qui]() y en la imagen.
   
    ![conf2](img/conf2.png)

Luego reiniciamos el servicio de dhcp con el comando.

 - ''' $systemctl restart isc-dhcp-server.service '''
   
Y ya deveria estar funcionado ahora mismo este servidor si le llegara una peticion discover ofreceria una ip.
