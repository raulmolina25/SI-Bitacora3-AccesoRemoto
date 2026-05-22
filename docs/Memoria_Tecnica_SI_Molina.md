

**Elaboración Documentación Técnica**  
**Raúl Molina Cordones**  
**DAM**  
**15/05/2026**


# Desplegamiento de la infraestructura 

Hemos guardado el archivo docker-compose.yml dentro de la carpeta, abrimos la terminal dentro de la carpeta y lo ejecutamos: docker-compose up \-d

# Ejecución

## Conexión con el contenedor 

Usando ssh alumno@localhost \-p 2222 nos hemos conectado al contenedor poniendo de contraseña: sistemas\_informaticos

Hemos generado un par de llaves para mayor seguridad: ssh-keygen \-t ed25519 \-C "[tu\_correo@ejemplo.com](mailto:tu_correo@ejemplo.com)" ssh-keygen \-t ed25519 \-C "raulmolina.25@campuscamara.es" 

Hemos copiado manualmente nuestra llave publica al contenedor.

## Entorno gráfico 

Hemos establecido conexión con el contenedor a traves de la web:(http://localhost:3000/

Hemos creado un archivo .txt en el entorno y insertado un mensaje

# 2. Estimación de Costes de Infraestructura

<img width="1210" height="221" alt="image" src="https://github.com/user-attachments/assets/c3c7b063-114a-4242-88e9-d845bc14e6e1" />

# 3. Estrategia de Despliegue y Comunicación

##3.1. Sistema de Transferencia de Ficheros   
Para el despliegue de la aplicación en el entorno de producción, utilizaremos el protocolo SFTP (SSH File Transfer Protocol). Se descarta por completo el uso de FTP tradicional debido a que transmite las credenciales y los datos en texto plano, lo que expone el sistema a ataques de interceptación.  
SFTP garantiza la seguridad del proceso al ejecutarse sobre un canal cifrado mediante SSH (Secure Shell). Esto asegura que tanto las contraseñas de acceso como los archivos binarios y de configuración viajen completamente encriptados entre el servidor de integración continua y el servidor de producción. Además, implementaremos la autenticación mediante claves criptográficas SSH (públicas/privadas) en lugar de contraseñas tradicionales, y restringiremos el acceso por IP para mitigar intentos de acceso no autorizados.

## 3.2. Mensajería y Alertas de Incidencias
El equipo utilizará Slack como plataforma centralizada para la comunicación técnica y la gestión de operaciones (ChatOps). Configuraremos integraciones nativas y webhooks conectados directamente con nuestro sistema de monitorización. Si el servidor sufre una caída o los servicios críticos dejan de responder, el sistema enviará alertas automáticas e instantáneas a un canal exclusivo denominado #alertas-produccion. Esto garantizará que el equipo de soporte reciba notificaciones en tiempo real, reduciendo al mínimo el tiempo de respuesta ante cualquier fallo en la infraestructura.
