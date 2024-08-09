---
id: nginx
aliases:
  - NGINX
tags:
  - severs
  - proxy
  - backend
  - devops
---

# NGINX

## ¿Que es NGINX?

NGINX es un `reverse proxy` conocido por servir como intermediario entre uno o varios servidores y los clientes que solicitan los recursos. Entre los proxys se encuentran diferentes tipos y cada uno puede tener funciones o fines diferentes.

## Reverse Proxy

### Ventajas

Algunas de las ventajas de los reverse proxy como NGINX son las siguientes:

1. Balanceo de carga

Balanceo de carga significa distribuir el trafico entrante de la aplicación a diversos servidores según se necesite, esto se hace para garantizar que ninguno de ellos se sature con demasiadas peticiones, mejorando la disponibilidad y la capacidad de respuesta del sistema.

El balanceo de carga es uno de los principales usos que se le da a NGINX, ya que esto es una manera de garantizar que nuestra aplicación sea escalable y no se sature por el trafico de red.

- Todos los servicios tienen que ser replicas idénticas.
- Se puede configurar de varias maneras, algunas son:
- Todas las peticiones entrantes van a diferentes servidores conforme entran.
- Todas las peticiones con un hash o una cockiee especifica van a un determinado servidor (Se usa para servicios con estado).
- Se mandan las solicitudes al servidor menos colapsado.

2. Mejora el rendimiento

NGINX también puede realizar tareas como la compresión de contenido, utilización de caché, y la optimización de contenido, todo esto con la finalidad de mejorar la velocidad de carga de las páginas.

3. Seguridad

Actúa como una capa extra de seguridad, ya que protege los servidores ocultando la verdadera IP y configurando firewalls para filtrar solicitudes o contenido malicioso.

4. Redirección de URL (Router)

Puede tomar las peticiones recibidas y modificar la URL según sea necesario para dirigir al cliente a los servidores o servicios previamente configurados.

5. Autenticación

También puede implementar métodos de autenticación al momento de conceder acceso a recursos.

6. Logs y Reports

Una utilidad que puede tener NGINX es el registro de logs, esto quiere decir que puedes monitorear las peticiones que se reciben y posteriormente tener un reporte con la información resultante.

## Configuración básica

```nginx

upstream app-name {
    #least_conn; #Dirige el trafico al server menos colapsado
    #ip_hash; #Hace un hash de la ip solicitante y siempre la dirige al mismo server

    server 172.17.0.2; #Servidor de donde se tomará el contenido
    server 172.17.0.3; #Servidor de donde se tomará el contenido
    #server 172.18.0.2; #Servidor de donde se tomará el contenido
    }

# http {
#     include mime.types;
#     default_type application/octet-stream;
#
#     sendfile on;
#     keepalive_timeout 65;
#
#     access_log /var/log/nginx/acces.goaccess.log combied;  #Direccion del archivo de logs y su tipo de formateo
#     }

#Configuración de caché
proxy_cache_path -var keys_zone=cache-name:10000m;

server {
    listen 80; #Puerto en donde se mostrara el contenido
    server_name localhost; #Nombre del host

    location / {
        #proxy_cache cache-name;
        #proxy_cache_valid any 30m;
        #proxy_cache_background_update on;
        #proxy_cache_methods GET POST HEAD;
        #proxy_cache_key $proxy_host$request_uri$cockie_sessionid;

        proxy_pass http://app-name; #Hacia donde se mostrara el contenido

        satisfy all;
        allow 172.17.0.0/24;
        deny all;

        auth_basic "Autentication";
        auth_basic_user_file /.htpasswd;
        }
    location /serv2 {
        proxy_pass http://172.17.0.3/;
        }
    }
```
