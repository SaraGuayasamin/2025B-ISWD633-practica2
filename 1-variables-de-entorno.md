# Variables de Entorno
### ¿Qué son las variables de entorno?
# COMPLETAR

### Para crear un contenedor con variables de entorno

```
docker run -d --name <nombre contenedor> -e <nombre variable1>=<valor1> -e <nombre variable2>=<valor2>
```

### Crear un contenedor a partir de la imagen de nginx:alpine con las siguientes variables de entorno: username y role. Para la variable de entorno rol asignar el valor admin.

# docker run -d --name nginx-con-env -e username=usuario1 -e role=admin nginx:alpine

# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR
<img width="1009" height="591" alt="image" src="https://github.com/user-attachments/assets/5c5566cb-e181-489c-aee1-d2ad23300494" />

### Crear un contenedor con la imagen de mysql, mapear todos los puertos
# docker run -d --name mysql-contenedor -e MYSQL_ROOT_PASSWORD=tu_clave mysql

### ¿El contenedor se está ejecutando?
# COMPLETAR
Sí, el contenedor llamado mysql-contenedor se está ejecutando correctamente. 
Esto se confirma con el comando docker ps -a, donde aparece con el estado Up, lo que indica que está activo y funcionando. También se observa que los puertos 3306/tcp y 33060/tcp están abiertos dentro del contenedor.


### Identificar el problema
# COMPLETAR
Aunque el contenedor está en ejecución, no se ha mapeado el puerto 3306 al host, lo que significa que no puedes conectarte a MySQL desde tu máquina local usando herramientas externas como MySQL Workbench o DBeaver. 
Esto se debe a que el comando usado para crear el contenedor no incluyó la opción .



### Para crear un contenedor con variables de entorno especificadas
- Portabilidad: Las aplicaciones se vuelven más portátiles y pueden ser desplegadas en diferentes entornos (desarrollo, pruebas, producción) simplemente cambiando el archivo de variables de entorno.
- Centralización: Todas las configuraciones importantes se centralizan en un solo lugar, lo que facilita la gestión y auditoría de las configuraciones.
- Consistencia: Asegura que todos los miembros del equipo de desarrollo o los entornos de despliegue utilicen las mismas configuraciones.
- Evitar Exposición en el Código: Mantener variables sensibles como contraseñas, claves API, y tokens fuera del código fuente reduce el riesgo de exposición accidental a través del control de versiones.
- Control de Acceso: Los archivos de variables de entorno pueden ser gestionados con permisos específicos, limitando quién puede ver o modificar la configuración sensible.

### Crear un contenedor con mysql, mapear todos los puertos y configurar las variables de entorno mediante un archivo
# COMPLETAR

# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR 

### ¿Qué bases de datos existen en el contenedor creado?
# COMPLETAR
