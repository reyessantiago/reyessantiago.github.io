---
layout: post
title: Instalación modelo WRF v4.0 - Guía en Español
---

## Introducción
------
Se presentan los pasos seguidos para la instalación del modelo WRF V4.0 en una máquina corriendo Ubuntu Desktop 19.10.

## Sofware requerido
------
Se debe correr este comando para instalar los compiladores requeridos. Generalmente si se descargó una versión reciente de Ubuntu estos compiladores ya vendrán instalados por defecto, sin embargo, es recomendable revisar dicha instalación.

**Nota:** usar el comando `sudo` hará que ejecute el código con permisos de administrador, por lo que es necesario que ingrese la contraseña del usuario administrador de su equipo.

```javascript
sudo apt-get install build-essential csh gfortran m4
```

En mi caso requería instalar algunos paquetes, se introduce la contraseña del equipo y se da da enter.

![Instalacion compiladores](/images/F1.png)


## Revisión de las variables de entorno
-----
Después de haber instalado los compiladores es necesario revisar que los enlances a las variables de entorno se hayan creado correctamente. Si la instalación fue exitosa, al correr estos comandos debería ver la ruta a cada uno de los compiladores como lo muestra la imagen a continuación:

```javascript
which gfortran
which cpp
which gcc
```

![Variable de entorno](/images/F2.png)

## Pruebas de compatibilidad de los compiladores
-----
Existen algunas pruebas que pueden correrse para verificar que el compilador de fortran se cargó correctamente, y además que es compatible con el compilador para C. Cree una carpeta llamada **TEST** y descargue el archivo tar que contiene las pruebas y extraígalo en esta carpeta.

```javascript
mkdir TEST/
cd TEST/
wget http://www2.mmm.ucar.edu/wrf/OnLineTutorial/compile_tutorial/tar_files/Fortran_C_tests.tar
tar -xvf Fortran_C_tests.tar
```
![Descarga pruebas](/images/F3.png)



Se debe crear un nuevo directorio llamado **Build_WRF** y otro llamado **TESTS**. La ubicación de estas carpetas es arbitraria, sin embargo se recomienda hacerla en la ruta ```javascript /home/USUARIO/```. 
