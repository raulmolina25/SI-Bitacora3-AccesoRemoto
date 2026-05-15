

**Elaboración Documentación Técnica**  
**Raúl Molina Cordones**  
**DAM**  
**15/05/2026**

[**Desplegamiento de la infraestructura	3**](#desplegamiento-de-la-infraestructura)

[**Ejecución	3**](#ejecución)

[Conexión con el contenedor	3](#conexión-con-el-contenedor)

[Entorno gráfico	3](#entorno-gráfico)

# Desplegamiento de la infraestructura {#desplegamiento-de-la-infraestructura}

Hemos guardado el archivo docker-compose.yml dentro de la carpeta, abrimos la terminal dentro de la carpeta y lo ejecutamos: docker-compose up \-d

# Ejecución {#ejecución}

## Conexión con el contenedor {#conexión-con-el-contenedor}

Usando ssh alumno@localhost \-p 2222 nos hemos conectado al contenedor poniendo de contraseña: sistemas\_informaticos

Hemos generado un par de llaves para mayor seguridad: ssh-keygen \-t ed25519 \-C "[tu\_correo@ejemplo.com](mailto:tu_correo@ejemplo.com)" ssh-keygen \-t ed25519 \-C "raulmolina.25@campuscamara.es" 

Hemos copiado manualmente nuestra llave publica al contenedor.

## Entorno gráfico {#entorno-gráfico}

Hemos establecido conexión con el contenedor a traves de la web: [http://localhost:3000/](http://localhost:3000/)

Hemos creado un archivo .txt en el entorno y insertado un mensaje