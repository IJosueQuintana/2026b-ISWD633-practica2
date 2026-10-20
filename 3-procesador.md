# Limitar uso de procesador
Limitar la cantidad de núcleos de CPU:
```
--cpus="1.5"
```

Asignar núcleos de CPU específicos:
```
--cpuset-cpus="0-2"
```

**¿Como saber el numero de procesadores virtuales que tiene una máquina?**
Para conocer la cantidad de procesadores lógicos disponibles en Windows, se puede utilizar el siguiente comando de PowerShell:

(Get-CimInstance Win32_ComputerSystem).NumberOfLogicalProcessors

Para consultar la cantidad de procesadores virtuales disponibles para Docker, se utiliza:

docker info --format "{{.NCPU}}"

Estos comandos permiten identificar los recursos de procesamiento disponibles y determinar qué núcleos pueden asignarse a los contenedores mediante los parámetros --cpus y --cpuset-cpus.

## Ejemplos
_Puedes copiar y ejecutar directamente cada uno de los comandos_

Limitar el uso de CPU a 1.5 núcleos
```
docker run -d --name server-nginx --cpus="1.5" nginx:alpine
```

Restringir el contenedor para que use los núcleos de CPU 0 a 2:
```
docker run -d --name server-nginx --cpuset-cpus="0-2" nginx:alpine
```

Restringir el contenedor para que use los núcleos de CPU 1 y 3:
```
docker run -d --name server-nginx --cpuset-cpus="1,3" nginx:alpine
```
