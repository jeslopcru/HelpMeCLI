#Comandos y ayuda de linux

### Copiar desde un servidor a local - Descargar los logs
scp -pr USUARIO@IP_SERVER_REMOTO:/var/log/apache2/access.log.28.gz /home/jesuslc/logs

### Copiar desde local a un servidor - Subir un archivo
` scp /home/jesuslc/.ssh/id_rsa.pub  USUARIO@IP_SERVER_REMOTO:/home/pedro/clave_publica.t`

### Descomprimir un archivo
`tar -zxvf`
### Comprimir
`tar czvf archive.tar.gz path/`

### codificacion de un archivo
`file <nombre archivo>`

### Convertir codificación
`iconv `

## Enlaces simbolicos
### Borrar enlace
`unlink /srv/www/deployWordpress/current`

### Crear enlace carpeta a enlazar directorio donde crear el enlace
`ln -s  /srv/www/deployWordpress/current /var/www/wordpress`

### Teclado en español
`sudo setxkbmap -layout 'es,es' -model pc105`

### Cuando falla el sonido
`pavucontrol`

### Hacer alias para acceso rápido del terminal
```
sudo vi /etc/bash.bashrc
alias wp='cd /home/jesuslc/workspace/wordpress/'
```

### Saber los procesos que consumen mas memoria
`ps aux --width 30 --sort -rss | head`

### Renombrar todas las fotos con la fecha
`for i in *jpg; do jhead -n%Y-%m-%d-%f $i; done`

## Búsquedas

###Encontrar imágenes de más de 100kb
`find . -type f -size +100k -name '*.jpg'`



## CURL

### Enviarn HTTP POST
`curl https://api.faker.com/v1/customers -i -XPOST -H 'Content-Type: application/json' -d '{"firstName":"Walter", "lastName":"White"}'`


## Screen

### Como ejecutar comandos dentro de screen
Pulsar Control+A (las dos teclas simultaneamente, en minisculas) y despues el comando que queramos

#### Control+A k Matar el screen actual

#### Control+A d Minimizar el screen actual

### Crear un screen con nombre
`screen -S foobar`

### Reabrir un screen previo
`screen -r foobar`

### Listar todos los screen creados
`screen -ls`






