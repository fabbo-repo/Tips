### Habilitar firewall:
~~~
sudo ufw enable
~~~

------------------------------------------------------------------------------------
### Ver estado del firewall:
~~~
sudo ufw status
~~~

------------------------------------------------------------------------------------
### Ver lista de aplicaciones que reconoce el firewall
~~~
sudo ufw app list
~~~

------------------------------------------------------------------------------------
## Permitir una app a través del firewall
~~~
sudo ufw allow "nombreApp"
~~~

------------------------------------------------------------------------------------
### Ver estado samba con números de líneas
~~~
sudo ufw status numbered
~~~

------------------------------------------------------------------------------------
### Eliminar una línea de estado
~~~
sudo ufw delete numLinea
~~~

------------------------------------------------------------------------------------
### Eliminar reglas definidas anteriormente:
~~~
sudo ufw reset
~~~
