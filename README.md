![Wordpress][Wordpress-img]

# Instalar un Wordpress en un servidor con Ubuntu 16.04


Proyecto en [Ansible][ansible-url] en proceso de desarrollo que permite configurar un servidor con todos las aplicaciones necesarias para la ejecución de un blog con [Wordpress][wordpress-url].

## Configurar

### Copiar el archivo de configuración

```bash
cp hosts.sample hosts
```

* En la sección ***[wordpress]*** reemplazar ***<IP|dominio>*** por la IP o el nombre del dominio de su servidor.

* En la sección ***[wordpress:vars]*** por lo general no sufre cambios

* Reemplazarl los valores para wp_mysql_db, wp_mysql_user y wp_mysql_password según sea el caso


La versión final del archivos ***hosts*** debería ser similar a:

``` yaml
[wordpress]
123.123.0.12

[wordpress:vars]
ansible_ssh_user=root
ansible_python_interpreter=/usr/bin/python3

wp_mysql_db=wordpress
wp_mysql_user=wordpress
wp_mysql_password=secret

```


## Ejecutar

Desde la termnal escribir:

``` sh
ansible-playbook playbook.yml -i hosts
```


## TODO
* Vagrant
* Pruebas
* Refactorización


[wordpress-img]: images/wordpressIcon2.png

[ansible-url]: https://www.ansible.com/
[wordpress-url]: https://es.wordpress.com/
