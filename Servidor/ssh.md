### Instalar servidor ssh:
* Instalar OpenSSH:
~~~
sudo apt-get install openssh-server
~~~

* Editar configuración:
~~~
sudo nano /etc/ssh/sshd_config
~~~

- Arrancar servidor:
~~~
sudo /etc/init.d/ssh start
~~~

* Parar servidor:
~~~
sudo /etc/init.d/ssh stop
~~~

* Reiniciar servidor:
~~~
sudo /etc/init.d/ssh restart
~~~

------------------------------------------------------------------------------------
### Instalar y configurar fail2ban:
* Instalar fail2ban (banear IPs que hagan muchos intentos de conexión fallidos)
~~~
sudo apt-get install fail2ban
~~~

* Entrar en la configuración
~~~
sudo nano /etc/fail2ban/jail.local
~~~

* Añadir lo siguiente:
>	[ssh] \
>	enabled = true \
>	port = 1234 \
>	filter = sshd \
>	logpath = /var/log/auth.log \
>	maxretry = 3

* Iniciar fail2ban:
~~~
sudo /etc/init.d/fail2ban start
~~~

* Ver logs de conexión:
~~~
grep /var/log/sshd/var/log/auth.log | less
~~~

------------------------------------------------------------------------------------
### Para más seguridad:
https://www.redeszone.net/tutoriales/seguridad/servidor-ssh-comprobar-seguridad-proteger/

------------------------------------------------------------------------------------
### Comprobar conexiones:
* Inicios de sesion aceptadas:
~~~
sudo cat /var/log/auth* | grep Accepted | awk '{print $1 " " $2 "\t" $3 "\t" $11 "\t" $9 }'
~~~

* Intentos de inicio de sesión:
~~~
ps -Af | grep sshd: | grep @pts
~~~

* Conexiones ftp activas:
~~~
netstat -tan | grep \:21
~~~

* Conexiones ftp activas:
~~~
netstat -tan | grep \:22
~~~

------------------------------------------------------------------------------------
### Enjaular usuarios en sftp:
https://blog.desdelinux.net/transferir-archivos-mediante-sftp-y-jaulas-en-debian-y-en-ubuntu/