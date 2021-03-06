### Instalar y configurar servidor de Escritorio Remoto:
* Actualizar repositorios locales
~~~
sudo apt update
~~~

* Instalar xrdp
~~~
sudo apt install xrdp
~~~

* Hacer backup del fichero de configuración
~~~
sudo cp /etc/xrdp/xrdp.ini /etc/xrdp/xrdp.ini.bck
~~~

* Acceder al fichero de configuración
~~~
sudo nano /etc/xrdp/xrdp.ini
~~~

---------------------------------------------------
### Onptimizar:
* Modoficar variables
> max_bpp=128 \
> xserverbpp=128 \
> crypt_level=low

* Añadir variable debajo de max_bpp
> use_compression=yes

---------------------------------------------------
### Personalizar la interfaz
* Ir a la carpeta que utiliza xdrp para las imagenes y logos:
~~~
cd /usr/share/xdrp/
~~~

* Modificar o añadir dos imagenes con extensión ***.bmp*** y 24 pixeles, las llamaremos "imagenFondo.bmp" y "imagenLogo.bmp"

* Acceder al fichero de configuración
~~~
sudo nano /etc/xrdp/xrdp.ini
~~~

* Añadir colores como negro: 3d423f o verde: 2dd967

* Cambiar ***ls_tittle***

* Modificar ls_background_image
> ls_background_image=imagenFondo.bmp

* Modificar ls_logo_filename
> ls_logo_filename=/usr/share/xrdp/imagenLogo.bmp

---------------------------------------------------
### Reiniciar servicio xrdp:
~~~
sudo systemctl restart xrdp
~~~

---------------------------------------------------
### Revisar estado:
~~~
sudo systemctl status xrdp
~~~

---------------------------------------------------
### Cerrar sesión xrdp:
~~~
/etc/init.d/xrdp stop
~~~

---------------------------------------------------
### Usar xrdp:
~~~
/etc/init.d/xrdp start
~~~

---------------------------------------------------
### Verificar estado:
~~~
/etc/init.d/xrdp status
~~~

---------------------------------------------------
### Si está el firewall activo:
~~~
sudo ufw allow 3389/tcp
~~~
