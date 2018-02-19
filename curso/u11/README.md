# Trabajando con alias

Los [Alias](http://httpd.apache.org/docs/2.4/mod/mod_alias.html#alias) nos permiten que el servidor sirva ficheros desde cualquier ubicación del sistema de archivo aunque este fuera del directorio indicado en el `DocuemntRoot`.	

Por ejemplo si pongo este alias en el fichero de configuración de `pagina1`:

	Alias "/image" "/ftp/pub/image"

Puedo acceder, por ejemplo, a una imagen con la URL `www.pagina1.org/image/logo.jpg`. 

No basta con poner la directiva `Alias`, además es necesario dar permiso de acceso al directorio, por lo tanto tendremos que poner:

	Alias "/image" "/ftp/pub/image"
	<Directory "/ftp/pub/image">
    	Require all granted
	</Directory>

## Ejercicios

Crea un alias en el host virtual `pagina1` , que mi permita acceder en la URL `http://www.pagina1.com/documentos` y visualice los ficheros del `/home/usuario/Documentos`. 
