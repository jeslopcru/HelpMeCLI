# Comandos y ayuda de Varnish

### Arrancar y parar
```
varnishadm start
varnishadm stop
```

### Ver errores 503
`varnishlog -c -m TxStatus:503`

### Filtrar solo una URL
`varnishlog -c -m Hash:/some/url`

### ver el referer de una request
`varnishtop -i RxHeader -I \^Referer`





### Ejecutar todos los tests de varnish de la carpeta test
```
# El servicio Varnish debe estar parado para poder lanzar las pruebas.
sudo service varnish stop
 
# Lanzar todas las pruebas y detenerse en cuanto falle una de ellas.
for i in `find ../test -type f -name "*.vtc"`; do echo;echo;echo "========== TEST $i =========="; sudo varnishtest $i; if [ $? -ne 0 ]; then break; fi; done
```

### Cambio en caliente de Varnish
```
#listado de VCL
varnishadm vcl.list 

#Hacemos el cambio
varnishadm vcl.load nombreCambio main.vcl

# Si todo va bien (no hay errores de sintaxis o de estructura), el código compila y estará disponible
varnishadm vcl.list

#Activamos
varnishadm vcl.use nombreCambio
```


