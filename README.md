# Reparacion_Hantek_DSO5062B
Este es un instructivo para solucionar una falla del osciloscopio marca Hantek modelo DSO5062B.

# Descripción del problema

Después de unos segundos de encender el equipo, se conjela la pantalla y los controles no responden. La figura a continuación muestra la pantalla del osciloscopio luego de inicializar.

![Imagen 01_pantalla_inicio](https://raw.githubusercontent.com/DarioCapu/Reparacion_Hantek_DSO5062B/master/Imagenes/01_pantalla_inicio.png)

Se encontró que los equipos que presentaban este problema no realizaban el conteo de los booteos.

![Imagen 02_pantalla_parametros](https://raw.githubusercontent.com/DarioCapu/Reparacion_Hantek_DSO5062B/master/Imagenes/02_pantalla_parametros.png)

# Conexión con la PC

Para poder solucionar este problema hay que conectarse por comunicación serie a través de un puerto de servicio del osciloscopio. 

![Imagen 03_Osciloscopio_sin_carcaza](https://raw.githubusercontent.com/DarioCapu/Reparacion_Hantek_DSO5062B/master/Imagenes/03_Osciloscopio_sin_carcaza.png)

Desamontado la carcaza trasera del equipo, queda a la vista la fuente de alimentación y la placa principal. El terminal de conexión para la comunicación serie es identificado como J801. Donde los pines que nos interesan para la conexión son

| Pin # | Descripción | Conexión | 
| ----- | ----------- | -------- |
| Pin 2 | GND | Cable Rojo |
| Pin 3 | Tx | Cable Negro |
| Pin 4 | Rx | Cable Blanco |

![Imagen 04_conexion_serial](https://raw.githubusercontent.com/DarioCapu/Reparacion_Hantek_DSO5062B/master/Imagenes/04_conexion_serial.png)

![Imagen 05_conexion_serial](https://raw.githubusercontent.com/DarioCapu/Reparacion_Hantek_DSO5062B/master/Imagenes/05_conexion_serial.png)

Para realizar la comuncación con la PC se utilizón un conversor TTL-USB conde se conctó el terminal Tx del Osciloscopio con el Rx del conversor, el Rx del Osciloscopio con el Tx del conversor, y masa con masa.

![Imagen 06_ttl_usb](https://raw.githubusercontent.com/DarioCapu/Reparacion_Hantek_DSO5062B/master/Imagenes/06_ttl_usb.png)

# Usando la terminal

Utilizado el programa minicom se coniguro la comunicación como 115200 8N1.

![Imagen 07_com_parametros](https://raw.githubusercontent.com/DarioCapu/Reparacion_Hantek_DSO5062B/master/Imagenes/07_com_parametros.png)

Encendiendo el osciloscopio se obtien como respuesta

![Imagen 08_inicio_osciloscopio](https://raw.githubusercontent.com/DarioCapu/Reparacion_Hantek_DSO5062B/master/Imagenes/08_inicio_osciloscopio.png)

Se inicializa la consola de la interfaz.

![Imagen 09_consola](https://raw.githubusercontent.com/DarioCapu/Reparacion_Hantek_DSO5062B/master/Imagenes/09_consola.png)

Para que el equipo funcione correctamente se deben eliminar de la carpeta */param/sav* los archivos *chk1kb_091023*, *set1kb_100302.0*, *set1kb_100302.1* y *run1kb_100302*. Luego se reinicia el osciloscopio con el comando *reboot*.

![Imagen 10_directorios](https://raw.githubusercontent.com/DarioCapu/Reparacion_Hantek_DSO5062B/master/Imagenes/10_directorios.png)

Luego de apagar y prender el equipo, se verifica que esté realizando la cuenta de los booteos.

![Imagen 11_boot_count](https://raw.githubusercontent.com/DarioCapu/Reparacion_Hantek_DSO5062B/master/Imagenes/11_boot_count.png)
