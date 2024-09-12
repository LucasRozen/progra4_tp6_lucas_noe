# Reporte
### Organización de carpetas
Hicimos una carpeta con el nombre del repo y adentro una carpeta para el frontend y otra para el backend.
### Armado de Imágenes y Compose
Usamos el boilerplate de Chat GPT que dejó nuestro profesor de programación Diego Freijo en la presentación de la clase de Docker, ya que eran las mismas tecnologías. Teniendo eso de base, modificamos las rutas acorde a la estructura de carpetas de nuestra app.
### Reinicio automático del servicio
Para que el servicio siga andando aún si se reinicia el servidor, agregamos la configuración "restart: unless-stopped" a cada imagen en el docker-compose para que el servicio se reincie automáticamente después de un reinicio del servidor, a menos que se haya detenido manualmente con ```docker stop```.
### Problemas interesantes
Un problema interesante que tuvimos fue que nos tiraba error de CORS pero el CORS estaba agregado al index.ts. Este backend en particular tenía subidos a github los archivos .js, entonces el problema era que no estaba configurado el CORS en el index.js. Enotnces le pedimos a ChatGPT que nos tire el código para agregar el CORS en el index.js, lo agregamos y funcionó :).
### Creación de .env
En el servidor de AWS creamos los .env correspondientes tanto para el backend como para el frontend parándonos en la carpeta de cada aplicación y ejecutando el comando "nano .env" para entrar en un editor de texto de la terminal y agregar las variables de entorno necesarias al archivo. Luego salimos del editor con ```ctrl + x```, ```Y``` para guardar los cambios, y por último ```Enter```.
