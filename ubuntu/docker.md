### Dar permisos de root a docker:
* Crear el usuario docker:
~~~
sudo groupadd docker
~~~

* Dar permisos a docker:
~~~
sudo usermod -aG docker $USER
~~~
