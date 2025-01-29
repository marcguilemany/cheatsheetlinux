$\color{blue}{\textsf{Podman Command}}$

Por defecto, si no se especifica el tag será latest

```latex
Buscando Imagenes         % Start of the document

podman images => Lista todas las imagenes locales
podman history image:tag => Muestra información de como se contruyó la imagen
podman login registryURL -u username [-p password] => Hace el login al registry remoto
podman search searchString => Busca en la cache local y remota del registry buscan la imagen
    ##Nota: La lista de las images de define en /etc/containers/registries.conf
podman logout => Se sale del registry


Construyendo Imagenes

podman build -t image:tag .=> Crea y tagea una imagen según las instrucciones del Dockerfile en el directorio en el que está
    ##Nota: Has de estar donde se encuentra el Dockerfile para generar la imagen

podman build -t image:tag -f Dockefile2 => Lo mismo que lo anterior, pero especificando un Dockefile distinto

podman tag image:tag image:tag2 => Añadir un nombre adicional a la imagen local

podman tag image:tag registry/username/image:tag => Same as above, but the additional name includes a remote registry
podman push registry/username/image:tag => Push an image to a remote registry