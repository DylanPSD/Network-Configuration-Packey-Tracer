# Conceptos necesarios para la configuración de una red en Packet Tracer

Estos son los conceptos básicos que debes conocer para configurar una red con esta guía.

---

## Tipos de memoria de un router  

- **RAM**: Esta es la memoria volátil de un router. En esta memoria se almacenan la configuración que se está produciendo en tiepo real, así como las tablas de enrutamiento, caché de ARP. Esta memoria no se guarda al reiniciar el dispositivo y se pierden los cambios realizados. A esta memoria se le llama **Running-config**

- **NVRAM**: Es una memoria no volátil que conserva los datos incluso después de un reinicio. Esta memoria almacena la configuración inicial de un dispositivo **Startup-config** que se utiliza en el proceso de arranque para cargar la configuración basica de un router.  

- **Flash**: Esta memoria es la que utiliza el router para almacenar el sistema operativo del router, (el IOS en dispositivos router Cisco) y otros archivos como imegenes de configuración.

---

## Paquetes de Red  
Formato en el que se manda la información en la **capa de red (capa 3)** del modelo OSI.

---

## Topología Física y Lógica  

- **Física**: Esquema de la distribución en el entorno físico de los PCs, servidores, armarios de racks, etc.  
- **Lógica**: Esquema lógico de la distribución de los routers, los tipos de medios y los servicios de los servidores.

---

## Medios  
Vías que utilizan los paquetes de red para viajar entre dispositivos intermedios hasta llegar a los dispositivos finales.

---  

## Routers  
Dsipositivos intermedios que separan y comunican redes, tamnbien enrutan paquetes y son los dispositivos en los que principalmente se va a basar la configuración de una red  

---

## Dispositivos Finales  

- **PC**: Cliente de servicios en la red.  
- **Servidor**: Proveedor de servicios como DHCP, DNS o TFTP.  

---  

## Modo EXEC privilegiado  
Este modo permite realiazar configuraciones y administra el sistema de manera completa, proporciona un conjunto amplio de comandos. A diferencia del modo EXEC básico o de usuario.  
>se indica con un "#" al final del nombre del dispositivo en la linea de comandos
---  

## Modo de configuración global  
En este modo se permite hacer configuraciones que afectan al dispositivo en su totalidad. Desde este modo se puede acceder a submodos para: configurar interfaces, protocolos...  
>Se identifica con un "(config)#" en la linea de comandos

---

## Direcciones y Protocolos  

- **Protocolo de Internet (IP)**: Dirección única que identifica un dispositivo final en una red.  
- **Máscara de Subred**: Número de 32 o 128 bits que identifica la parte de red y la parte de host en una IP.  
- **Máscara Wildcard**: Cadena de 32 bits utilizada por el router para determinar las partes de red y host, principalmente en protocolos como OSPF.  

---

## Puerta de enlace predeterminada (Default Gateway)
Esto se refiere a dispositivos o IP que se comportan como puntos de acceso para enviar datos fuera de su propia red.

---

## Redes Virtuales  

- **Red de Área Local Virtual (VLAN)**: Redes lógicas independientes dentro de una misma red física.  
- **Voz sobre IP (VoIP)**: Método que permite realizar llamadas a través de la red.  

---

## Protocolos de Enrutamiento  

- **OSPF (Open Shortest Path First)**: Protocolo de enrutamiento que dirige paquetes de red por los medios más óptimos para llegar a su destino.  

---

## Protocolos de Servicios  

- **DHCP (Dynamic Host Configuration Protocol)**: Asigna direcciones IP dinámicamente y de forma automática a los dispositivos finales.  
- **DNS (Domain Name System)**: Traduce nombres de dominio (ej. www.dylan.com) en direcciones IP utilizables por las máquinas.  
- **HTTP(HyperText Transfer Protocol)**: Se utiliza para alojar una pagina web desde un servidor. Tambien permite que los usuarios accedan a recursos web a traves de navegadores.
- **TFTP(Trivial File Transfer Protocol)**: Protocolo diseñado para transferir archivos como configuraciones, firmware o copias de seguridad entre dispositivos y servidores.

---

## Access-Lists (ACLs)  

Permiten restringir o conceder acceso a servicios, medios o dispositivos finales. Las ACL son secuenciales, lo que quiere decir, que se leen de arriba hacia abajo, ppor lo que, primero deberemos añadir las lineas de host y después las de red. Solo puede haber una ACL en cada interfáz. En las estándar cuando va en una interfáz desde el router hacia la red se pone "out" y cuando va en una interfáz desde el router hacia otro router se pone "in" .  
Se configuran en dispositivos de capa 3 y pueden ser:

1. **Estándar**: Configuradas cerca del destino, solo es necesario especificar la red o ip origen que deseamos controlar.  
   - **Numeradas**: Identificadas con un número, no editables tras su configuración.  
   - **Nombradas**: Identificadas con un nombre, editables tras su configuración.  

2. **Extendidas**: Configuradas cerca de la fuente para un mayor control, se debe especificar el origen y destino, y las especificaciones de las comunicaciones a controlar, como podria ser el protocolo de comunicación y el puerto4 .  
   - **Numeradas**: Identificadas con un número, no editables tras su configuración.  
   - **Nombradas**: Identificadas con un nombre, editables tras su configuración. 

---

## Protocolos de Transferencia de Archivos  

- **TFTP (Trivial File Transfer Protocol)**: Permite la transferencia de archivos entre sistemas conectados a una red.  

---

## Protocolos de Comunicación  

- **Telnet**: Protocolo que permite acceder y configurar otro dispositivo dentro de la red mediante texto.  

---

## Traducción de Direcciones  

### NAT (Network Address Translation)  
Protocolo que traduce IPs privadas a IPs globales. Se configura en el router conectado al ISP o red externa.  

1. **NAT Estática**: Traduce una IP privada a una IP pública fija (útil para servidores, impresoras, etc.).  
2. **NAT Dinámica**: Traduce un rango de IPs privadas a un rango de IPs públicas mediante una **Access-List** y un "pool" de IPs públicas.

---

### PAT (Port Address Translation)  
Protocolo similar a NAT pero permite traducción de múltiples direcciones privadas a una sola IP pública, añadiendo información de puerto.  

1. **PAT Dinámico**: Traduce de manera similar a NAT dinámica, pero permite compartir IPs públicas mientras no están en uso.  
2. **PAT a Puerto**: Traduce un conjunto de redes a un puerto específico de la interfaz del router conectado al ISP.

---

Con este resumen de conceptos, estás listo para seguir esta guía de configuracion en **Packet Tracer**. [GUIA](./Guia.md)


