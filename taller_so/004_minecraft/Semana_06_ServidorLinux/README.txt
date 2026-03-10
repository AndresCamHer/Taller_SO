# Proyecto: Servidor Linux explicado en Minecraft

Esta practica representa la administración de un servidor **Linux** usando un mundo de **Minecraft**.  
El edificio principal simboliza el servidor y cada sala corresponde a un aspecto clave de la administración: acceso, usuarios, permisos, red y seguridad.

---

## Sala TTY
- **Significado**: TTY = *Teletypewriter*, nombre histórico de las terminales.  
- **Función técnica**: Permite acceder a terminales virtuales. El comando `tty` muestra el dispositivo actual. `/dev/tty3` es la tercera terminal virtual activa.  
- **Uso en la práctica**: Entramos con `Ctrl+Alt+F3` y salimos con `Ctrl+Alt+F2`.  
- **Problema que resuelve**: Da acceso directo al sistema incluso si falla la interfaz gráfica.

---

## Sala Usuarios
- **Comandos principales**:  
  - `adduser`: crea un usuario y modifica `/etc/passwd`.  
  - `groupadd`: crea grupos para organizar usuarios.  
  - `usermod -aG`: añade un usuario a un grupo.  
- **Función técnica**: Gestiona cuentas y permisos de acceso.  
- **Uso en la práctica**: Se representaron Admin, Usuario1 y Usuario2 con casas distintas.  
- **Problema que resuelve**: Permite que varias personas usen el sistema con roles controlados.

---

## Sala Permisos
- **Comandos principales**:  
  - `chmod`: *change mode*, cambia permisos de archivos.  
  - `chown`: *change owner*, cambia el dueño de un archivo.  
- **Ejemplo**: `chmod 770` da permisos completos a dueño y grupo, y ninguno a otros. No se recomienda `777` porque da acceso total a cualquiera.  
- **Uso en la práctica**: Se protegió un cofre llamado `/soporte`.  
- **Problema que resuelve**: Evita accesos no autorizados a archivos críticos.

---

## Sala Red
- **Comandos principales**:  
  - `ip a`: muestra direcciones IP.  
  - `ping`: prueba conexión entre equipos usando ICMP (palabra viene del sonar submarino).  
  - `ip route`: muestra rutas y la puerta de enlace (gateway).  
- **Uso en la práctica**: Se construyó un servidor central y clientes conectados con caminos como cables.  
- **Problema que resuelve**: Diagnostica problemas de comunicación entre servidor y clientes.

---

## Sala Firewall
- **Comando principal**: `ufw` (*uncomplicated firewall*).  
- **Función técnica**: `ufw enable` activa el firewall.  
- **Puertos**:  
  - Puerto 80 = HTTP.  
  - TCP = protocolo de transmisión confiable.  
  - Bloquear puerto 22 = se pierde acceso remoto por SSH.  
- **Uso en la práctica**: Se construyó una muralla alrededor del servidor.  
- **Problema que resuelve**: Protege el servidor de accesos no autorizados y ataques externos.

---

## Conclusión
El mundo de Minecraft representa las funciones principales de un servidor Linux:  
- Acceso mediante TTY  
- Gestión de usuarios  
- Control de permisos  
- Configuración de red  
- Seguridad con firewall  

## Preguntas posibles

**¿Por qué ping usa ICMP?**  
Ping usa el protocolo ICMP porque es un protocolo ligero diseñado para enviar mensajes de control y verificación de conectividad entre equipos.  

**¿Qué pasa si no hay gateway?**  
Si no existe una puerta de enlace, el servidor solo puede comunicarse dentro de su red local y no podrá acceder a otras redes ni a Internet.  

**¿Qué riesgo tiene usar 777?**  
El permiso 777 da acceso total (lectura, escritura y ejecución) a cualquier usuario. Esto representa un riesgo de seguridad porque cualquiera podría modificar o ejecutar archivos críticos.  

**¿Por qué un firewall es importante?**  
El firewall es esencial porque controla el tráfico de red que entra y sale del servidor, bloqueando accesos no autorizados y protegiendo contra ataques externos.  

