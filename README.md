# SI-Bitacora4-AccesoRemoto

## 2. Preparación del Entorno

## Tarea 1: Despliegue de la Infraestructura
Crea una carpeta en tu equipo llamada SI_Bitacora4_NombreApellido.  
Guarda el archivo docker-compose.yml dentro de esa carpeta.  
Abre una terminal dentro de esa carpeta y ejecuta: docker-compose up -d  
Aqui tuve un pequeño error y era por no tener abierto el Docker Desktop  
<img width="1632" height="99" alt="image" src="https://github.com/user-attachments/assets/8324f743-436d-4f4f-9b6b-2f5df2b5c17d" />

Verifica que los contenedores están corriendo con docker ps. Deberías ver un servidor de consola (SSH) y uno gráfico (Webtop/RDP).  

# 3. Fase de Ejecución: Tareas Evaluables

## 3.1. SSH: Forjando la Llave Maestra

El acceso por contraseña es cosa del pasado. Un administrador profesional utiliza criptografía de clave pública.
- Paso A (Conexión Inicial): Conéctate al contenedor usando ssh alumno@localhost -p 2222. La contraseña es sistemas_informaticos.  
 ssh alumno@localhost -p 2222  
 sistemas informaticos  
 <img width="804" height="212" alt="image" src="https://github.com/user-attachments/assets/c980db6b-292f-4ca7-8913-32242b09804b" />

- Paso B (Generación de Identidad): En tu máquina anfitriona, genera un par de llaves: ssh-keygen -t ed25519 -C "tu_correo@ejemplo.com"  
ssh-keygen -t ed25519 -C "raulmolina.25@campuscamara.es"  
<img width="1036" height="403" alt="image" src="https://github.com/user-attachments/assets/31db25f3-6d00-4cc5-95e7-9a8d182f80fe" />

- Paso C (Transferencia): Copia tu llave pública al servidor. Puedes usar ssh-copy-id -p 2222 alumno@localhost o hacerlo manualmente pegando el contenido en ~/.ssh/authorized_keys dentro del contenedor.  
Con  ssh-copy-id -p 2222 alumno@localhost me daba error   
<img width="1608" height="161" alt="image" src="https://github.com/user-attachments/assets/fb90f1d8-7097-473e-9fa8-a68ce0a526e5" />
Lo que hice para solucinarlo fue hacerlo manualmente, pegando el contenido en el contenedor en ~/.ssh/authorized_keys  

## 3.2. RDP: El Escritorio en tu Navegador

A veces, la consola no es suficiente. Necesitamos el entorno gráfico. Y tenemos una alternativa:  
- Conexión: Abre tu cliente de Escritorio Remoto (MSTSC en Windows o Remmina en Linux) y apunta a localhost:3389.  
Da error por problemas del ordenador de clase  
<img width="567" height="373" alt="image" src="https://github.com/user-attachments/assets/053ec529-2083-4993-b299-4dbd46783598" />  

- Web: Si tu cliente RDP falla, ve a http://localhost:3000. Verás el escritorio de Ubuntu dentro de tu navegador gracias a Apache Guacamole [3].  
Sin embargo en la web tras entrar en http://localhost:3000 va perfectamente  
<img width="1918" height="985" alt="image" src="https://github.com/user-attachments/assets/b3fd5ef8-b8fe-4442-9c3d-46e5372bf6fc" />  

- Prueba de éxito: Crea un archivo de texto en el escritorio del contenedor llamado PRUEBA_LOGRADA.txt con un mensaje para el profesor.  
<img width="138" height="131" alt="image" src="https://github.com/user-attachments/assets/99f14cf5-97af-4355-86de-ce36eacccdd6" />  
<img width="655" height="746" alt="image" src="https://github.com/user-attachments/assets/b5ae8378-f192-47c4-be06-aad4306e0910" />  

- Reflexión Final: Comenta brevemente por qué crees que SSH es más utilizado en servidores de producción que RDP.  
Porque SSH prioriza la seguridad, mas eficaz y mas rapido, y RDP prioriza mas lo visual, es todo mas visual con su GUI   













