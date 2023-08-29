# Proxmox - IX Colombia
## _Guía definitiva_
Guía Práctica - Instalación y Configuración de Proxmox

## 1. Creación de la máquina virtual
  1. **Nombre y sistema operativo** ![N|Solid][001]
  2. **Memoria RAM Base** ![N|Solid][002]
  3. **Tamaño del Disco Duro** ![N|Solid][003] 
  4. **Resumen de la configuración** ![N|Solid][004]

## 2. Configuración de Interfaces de Red
  1. **Doble click en la máquina para ingresar a su configuración**![N|Solid][005]
  2. **Habilitar el primer adaptador**![N|Solid][006]
  3. **Habilitar el segundo adaptador**![N|Solid][007]


### _IMPORTANTE_
  >Si estás en windows y estas conectado solo al wifi, debes mantener el dispositivo encendido en todo momento, para asegurarte de esto, abre la consola y escribes el siguiente comando:

```
ping 8.8.8.8 -t
```
[N|Solid][008]

## 3. Instalación del Proxmox
  1. **Primera Opción**![N|Solid][009]
  2. **Colocar contraseña root**![N|Solid][010]
  3. **Configurar dominio**![N|Solid][010]

## 4. Actualización del Sistema
```sh
apt-get update
apt-get upgrade
```

## 5. Instalación de Herramientas
```sh
apt-get install lynx iptraf-ng apt-file screen traceroute net-tools ethtool
```


[001]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0001.png
[002]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0002.png
[003]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0003.png
[004]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0004.png
[005]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0005.png
[006]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0006.png
[007]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0007.png
[008]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0008.png
[009]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0009.png
[010]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0010.png
[011]: https://raw.githubusercontent.com/ebertlast/proxmox/master/assets/0011.png

[Naranja]: http://icons.iconarchive.com/icons/google/noto-emoji-animals-nature/256/22221-cat-icon.png