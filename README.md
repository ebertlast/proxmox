# Proxmox - IX Colombia
## _Guía definitiva_
Guía Práctica - Instalación y Configuración de Proxmox

## 1. Creación de la máquina virtual
  1. **Nombre y sistema operativo** ![N|Solid][0001]
  2. **Memoria RAM Base** ![N|Solid][0002]
  3. **Tamaño del Disco Duro** ![N|Solid][0003] 
  4. **Resumen de la configuración** ![N|Solid][0004]

## 2. Configuración de Interfaces de Red
  1. **Doble click en la máquina para ingresar a su configuración**![N|Solid][0005]
  2. **Habilitar el primer adaptador**![N|Solid][0006]
  3. **Habilitar el segundo adaptador**![N|Solid][0007]


### _IMPORTANTE_
  >Si estás en windows y estas conectado solo al wifi, debes mantener el dispositivo encendido en todo momento, para asegurarte de esto, abre la consola y escribes el siguiente comando:

```
ping 8.8.8.8 -t
```
[N|Solid][0008]

## 3. Instalación del Proxmox
  1. **Primera Opción**![N|Solid][0009]
  2. **Configurar pais e idioma de teclado**![N|Solid][0009.5]
>Si se carga automáticamente el país, es una señal de que tiene internet la máquina virtual.
  3. **Colocar contraseña root**![N|Solid][0010]
  4. **Configurar hostname**![N|Solid][0011]

>Importante: Si se van a configurar varios host como es mi caso, se deben colocar los nombres de los equipos como qry01.ix.in, qry02.ix.in y qry03.ix.in respectivamente

## 4. Actualización del Sistema
```sh
apt-get update
apt-get upgrade
```

## 5. Instalación de Herramientas
```sh
apt-get install lynx iptraf-ng apt-file screen traceroute net-tools ethtool
```

## 6. Configurar el ambiente
```sh
nano  /root/.bashrc
```
![N|Solid][0012]

## 7. Descargar el webmin
```sh
md downloads
cd downloads
lynx webmin.com
```
>Descargar la opción deb para nuestra distribución debian 

![N|Solid][0013]

## 8. Instalar el webmin
```sh
apt-get install ./webmin_2.102_all.deb -y
```
## 9. Borrar el LVM innecesario y ocuparlo en root
  1. Dentro del proxmox debemos navegar hasta Centro de Datos / Almacenamiento
   - Seleccionar local-lvm
   - Dar click al botón Eliminar
   - ![N|Solid][0014]
  2. Ir a la consola de la máquina y borrar el LVM

   ```sh
    cd /dev/pve
    lvremove /dev/pve/data
   ```
   - ![N|Solid][0015] 
  3. Entrar al webmin
   - El **puerto** por **defecto** del **webmin** es el **10000**, entrar con la siguiente url https://ip.de.la.maquina:10000
   - Una vez dentro debemos navegar hasta **Hardware / Logical Volume Management / Logical Volumes**
   - Hacer click en **root**
   - ![N|Solid][0016]
   -  Seleccionar **Use all free vg space** y click en el boton **Save**
   - ![N|Solid][0017] 

## 10. Cambiar puertos por defecto del webmin
  Por seguridad debemos cambiar el puerto por defecto a 10101 y opcionalmente deshabilitar las conexiones entrantes por IPV6.
   - ![N|Solid][0018]
   - ![N|Solid][0019]

## 11. Cambiar el idioma del webmin
   - ![N|Solid][0020]

## 12. Actualizar los repositorios de Proxmox
   - ![N|Solid][0021]
   - ![N|Solid][0022]
   - ![N|Solid][0023]
   - ![N|Solid][0024]
   - ![N|Solid][0025]
   - ![N|Solid][0026]


[0001]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0001.png
[0002]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0002.png
[0003]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0003.png
[0004]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0004.png
[0005]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0005.png
[0006]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0006.png
[0007]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0007.png
[0008]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0008.png
[0009]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0009.png
[0009.5]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0009.5.png
[0010]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0010.png
[0011]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0011.png
[0012]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0012.png
[0013]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0013.png
[0014]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0014.png
[0015]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0015.png
[0016]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0016.png
[0017]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0017.png
[0018]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0018.png
[0019]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0019.png
[0020]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0020.png
[0021]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0021.png
[0022]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0022.png
[0023]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0023.png
[0024]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0024.png
[0025]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0025.png
[0026]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0026.png

[Naranja]: http://icons.iconarchive.com/icons/google/noto-emoji-animals-nature/256/22221-cat-icon.png