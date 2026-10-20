# COMPLETAR  
Comparando sus conocimientos antes de hacer la práctica con sus conocimientos después de hacer la tarea, explicar los principales aprendizajes logrados para beneficio de su formación profesional.  
Si solucionó un problema presentado al realizar la práctica también se debe documentar.

# Aprendizajes obtenidos y problemas solucionados

## Principales aprendizajes

Antes de realizar esta práctica, tenía conocimientos básicos sobre Docker, principalmente relacionados con la creación y ejecución de contenedores. Sin embargo, desconocía varias de las opciones que ofrece esta herramienta para administrar los recursos, almacenar información y controlar el funcionamiento de los servicios.

Durante el desarrollo de la práctica, aprendí a utilizar diferentes tipos de volúmenes para gestionar la persistencia de datos, comprendiendo las diferencias entre los volúmenes nombrados, anónimos y los montajes de directorios del sistema anfitrión. También reforcé mis conocimientos sobre la comunicación entre contenedores mediante redes Docker, utilizando servicios como MySQL, PostgreSQL, WordPress, Drupal y pgAdmin.

Otro aprendizaje importante fue la administración de recursos. Mediante los parámetros `--memory`, `--memory-swap`, `--cpus` y `--cpuset-cpus`, comprendí cómo establecer límites de memoria y procesamiento para evitar que un contenedor utilice recursos excesivos del equipo.

Además, aprendí a interpretar las configuraciones de Healthcheck y las políticas de reinicio, identificando su utilidad para supervisar el estado de los servicios y controlar su comportamiento ante posibles fallos.

Finalmente, adquirí experiencia en la creación de imágenes personalizadas mediante Dockerfile. Aprendí a utilizar instrucciones como `FROM`, `RUN`, `COPY`, `EXPOSE` y `CMD`, así como a construir diferentes versiones de una imagen, inspeccionar sus características y comprender el funcionamiento de la caché durante la construcción.

Considero que estos conocimientos contribuyen a mi formación como futuro ingeniero de software, ya que Docker permite desarrollar, probar y desplegar aplicaciones en entornos más organizados, reproducibles y fáciles de administrar.

## Problemas presentados y soluciones aplicadas

Uno de los principales inconvenientes ocurrió durante la construcción de la imagen personalizada de Apache basada en CentOS 7. Al ejecutar el comando `docker build`, se presentó un error relacionado con los repositorios de paquetes, debido a que CentOS 7 llegó al final de su ciclo de soporte y sus repositorios originales dejaron de estar disponibles de la misma manera.

Para solucionar este problema, modifiqué el Dockerfile con una instrucción que deshabilita las direcciones originales de los repositorios y utiliza los repositorios históricos de CentOS 7 disponibles en `vault.centos.org`. Después de realizar este cambio, pude construir correctamente la imagen e instalar Apache.

También identifiqué que, al reconstruir una imagen, Docker puede reutilizar capas almacenadas en caché. Esto me permitió comprender la importancia de modificar y guardar correctamente los archivos antes de generar una nueva versión. Posteriormente, actualicé el archivo HTML, reconstruí la imagen y comprobé los cambios desde el navegador.

Otro aspecto que reforcé fue la identificación de conflictos al reutilizar nombres de contenedores. Para resolverlos, aprendí a detener y eliminar los contenedores de prueba antes de crear otros con el mismo nombre, sin afectar los demás servicios.

## Conclusión

Esta práctica me permitió pasar de conocer únicamente los comandos básicos de Docker a comprender mejor cómo administrar contenedores, imágenes, redes, almacenamiento y recursos del sistema.

Además de aprender nuevas instrucciones, desarrollé habilidades para interpretar mensajes de error, identificar sus causas y aplicar soluciones. Considero que esta experiencia será útil en futuros proyectos académicos y profesionales, especialmente en actividades relacionadas con el desarrollo, las pruebas y el despliegue de aplicaciones de software.
