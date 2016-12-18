Bash en un shell de Unix (interprete de comando de UNIX), escrito para el proyecto GNU.
El nombre es un acrónimo de **b**ourne-**a**gain-**s**hell. Haciendo un juego de palabras (born-again significa *renacimiento*) sobre el Bourne shell (sh), que fue uno de los primeros shells importantes de Unix.

Bash es el shell por defecto en la mayoría de sistemas GNU/Linux, además de Mac OS Tiger, y puede ejecutarse en la mayoría de sistemas operativos tipo [UNIX](https://es.wikipedia.org/wiki/Unix). También se ha portado a Microsoft, Windows 10, por el proyecto [Cygwin](https://es.wikipedia.org/wiki/Cygwin).

Brian Fox escribió el shell bash en 1987. Ya en 1990 Chet Ramey se convirtió en su principal desarrollador.

La sintaxis de órdenes de bash es un superconjunto de la sintaxis del shell Bourne. La especificación definitiva de la sintaxis de órdenes de bash, puede encontrarse en el [BASH Reference Manual](https://tiswww.case.edu/php/chet/bash/bashref.html), distribuido por el proyecto GNU. en esta sección destaca algunas de las características únicas de bash.

La mayoría de los shell [scripts](https://es.wikipedia.org/wiki/Script) (guiones de intérprete de órdenes) Bourne pueden ejecutarse por Bash sin ningún cambio, con la excepción de aquellos guiones del intérprete de órdenes, o consola, Bourne que hacen referencia a variables especiales de Bourne o que utilizan una orden interna de Bourne. La sintaxis de órdenes de Bash incluye ideas tomadas desde el [Korn Shell (ksh)](https://es.wikipedia.org/wiki/Korn_Shell) y el [C Shell (csh)](https://es.wikipedia.org/wiki/C_Shell), como la edición de la línea de órdenes, el historial de órdenes, la pila de directorios, las variables $RANDOM y $PPID, y la sintaxis de substitución de órdenes POSIX: $(...). Cuando se utiliza como un intérprete de órdenes interactivo, Bash proporciona autocompletado de nombres de programas, nombres de archivos, nombres de variables, etc, cuando el usuario pulsa la tecla TAB.

La sintaxis de Bash tiene muchas extensiones que no proporciona el intérprete Bourne. Varias de las mencionadas extensiones se enumeran a continuación.

**Mi primer Hola Mundo en Bash**

Para empezar, haré una mención al simplismo "Hola mundo" de BASH, y también lo explicare. Para ejecutar los scripts en una terminal, usar: ./<nombre-script> o simplemente: bash <nombre-script>

Es muy simple, en realidad. Lo que hacemos aquí al escribir primero "#!/bin/bash", es llamar a nuestra shell BASH, que por lo general se ubica en /bin/bash, pero podría estar en otro lugar, así que si no la tenemos ahí se ejecutara el comando "locate bash" desde nuestra terminal, o bien si no tenemos locate podemos usar "which bash" o bien desde nuestro directorio raiz ( / ) ejecutamos "find bash" para localizar la ruta del programa bash. En mi caso con una terminal zsh la ruta es: #!/usr/bin/zsh

 ```bash
#!/bin/bash
# Script de Hola Mundo
echo "Hola Mundo"
```    
Salida:

```bash
Hola Mundo
```    
    
**Comentario en Bash**

Pero ¿el símbolo '#' escrito al inicio de una linea, es un comentario? En realidad sí, como en la segunda linea vemos, eso es un comentario, es decir, algo que no es interpretado y está ahí para que el programador/coder/scripter se ubique y sepa que es lo que hace el código, esto ayuda a tener mejor orden y al corregir el código si tiene BUGS. Pero la excepción a esto, es al escribir #!/ruta/de/interprete , esto nos sirve para llamar a nuestro interprete, como perl, bash, sh, python, etc, (que son otros lenguajes) y se usa para los lenguajes interpretados, de modo que se ejecuten en donde corresponde....

**Imprimiendo en Bash**

Por último, tenemos el comando ``echo``, como en ``batch``, que sirve para imprimir texto en la pantalla.

BASH funciona igual que nuestra terminal favorita, esto es por que nuestra terminal usa BASH para funcionar, y claro, cuando hacemos scripts es para automatizar procesos. Así es que la sintaxis es muy simple, un comando por línea.

Recomendamos leer los manuales y experimentar en el sistema operativo (claro sin ser root si no sabemos que es lo que hacemos) para aprender.

Como en todo lenguaje, necesitamos del uso de variables, que nos servirán para todo lo que queramos hacer en determinadas situaciones. Una variable, es una cadena de datos que se almacena en la memoria y que podemos llamar en cualquier momento para darle ``X`` uso.

**Asignando variables**

En BASH, las variables se asignan simplemente dando el nombre de la variable y su valor:
```bash
#!/bin/bash
#Asignando variables
hola=1
```
Como podemos leer aquí, este código asigna el valor 1 a la variable "hola". En BASH las variables son "CASE SENSITIVE" (sensibles), es decir, la variable ``Hola`` no es lo mismo que ``HOLA`` ni que ``holA``.

Otro de los puntos importantes de las variables en BASH es que no tenemos que asignarles un tipo, es decir, podemos darle a las variables cualquier valor y lo aceptará sin tener que decirle a BASH si es numérico o si son letras.

**Invocando variables**

Ya sabemos asignar una variable, pero de poco nos sirve si no podemos llamarla.

En BASH, las variables las invocamos simplemente anteponiendo un símbolo de dolar '$' antes del nombre de la variable.
Ejemplo:
```bash
#!/bin/bash
#Asignando variables
hola=1
#Llamando a la variable $hola
$hola
#Mostrando el contenido de la variable
echo $hola
```
Explicación

Si ponemos atención al código, en BASH, las variables simplemente se reemplazan por su valor al llamarlas, de modo que en ellas podemos almacenar X texto ó numero, ya sean comandos o lo que sea.

Al llamar a la variable, observamos que simplemente da el valor y lo pasa como una orden al interprete, pero si lo ponemos siguiendo un comando como ``echo`` entonces este mostrará el contenido de la variable.

Ejemplo de uso:
```bash
#!/bin/bash
#
# Se guarda en la variable el valor generado    por $RANDOM,
# el % 5 asegura obtener un numero menor a 5 .
RNM=`expr $RANDOM % 5`
echo $RNM
```
**Comandos básicos**

Para poder trabajar eficientemente en BASH, es indispensable conocer los comandos más básicos, aquí una pequeña lista que debemos conocer a la perfección:

                               Comandos básicos para BASH

| Comando [Opciones]          | Descripción del comando                                                      | Ejemplo de uso                |
|-----------------------------|------------------------------------------------------------------------------|-------------------------------|
| cat fich1 [...fichN]        | Concatena y muestra un archivos                                              | cat /etc/passwd               |
| cd [dir]                    | Cambia de directorio                                                         | cd /tmp                       |
| chmod permisos fich         | Cambia los permisos de un archivo                                            | chmod +x miscript             |
| chown usuario:grupo fich    | Cambia el dueño un archivo                                                   | chown nobody miscript         |
| cp fich1...fichN dir        | Copia archivos                                                               | cp foo foo.backup             |
| diff [-e]arch1 arch2        | Encuentra diferencia entre archivos                                          | diff foo.c newfoo.c           |
| du [-sabr] fich             | Reporta el tamaño del directorio                                             | du -s /home/                  |
| file arch                   | Muestra el tipo de un archivo                                                | file arc_desconocido          |
| find dir test acción        | Encuentra archivos.                                                          | find . -name ``.bak -print    |
| grep [-cilnv] expr archivos | Busca patrones en archivos                                                   | grep mike /etc/passwd         |
| head -count fich            | Muestra el inicio de un archivo                                              | head prog1.c                  |
| mkdir dir                   | Crea un directorio.                                                          | mkdir temp                    |
| mv fich1 ...fichN dir       | Mueve un archivo(s) a un directorio                                          | mv a.out prog1                |
| mv fich1 fich2              | Renombra un archivo.                                                         | mv .c prog_dir                |
| less / more fich(s)         | Visualiza página a página un archivo. less acepta comandos vi.               | less muy_largo.c              |
| ln [-s] fich acceso         | Crea un acceso directo a un archivo                                          | ln -s /users/mike/.profile .  |
| ls                          | Lista el contenido del directorio                                            | ls -l /usr/bin                |
| pwd                         | Muestra la ruta del directorio actual                                        | pwd                           |
| rm fich                     | Borra un fichero.                                                            | rm foo.c                      |
| rm -r dir                   | Borra todo un directorio                                                     | rm -rf prog_dir               |
| rmdir dir                   | Borra un directorio vacío                                                    | rmdir prog_dir                |
| tail -count fich            | Muestra el final de un archivo                                               | tail prog1.c                  |
| at [-lr] hora [fecha]       | Ejecuta un comando mas tarde                                                 | at 6pm Friday miscript        |
| cal [[mes] año]             | Muestra un calendario del mes/año                                            | cal 1 2025                    |
| date [mmddhhmm] [+form]     | Muestra la hora y la fecha                                                   | date                          |
| echo string                 | Escribe mensaje en la salida estándar                                        | echo ``Hola mundo             |
| finger usuario              | Muestra información general sobre un usuario en la red                       | finger nn @maquina.aca.com.co |
| id                          | Número id de un usuario                                                      | id usuario                    |
| kill [-señal] PID           | Matar un proceso                                                             | kill 1234                     |
| man comando                 | Ayuda del comando especificado                                               | man gcc, man -k printer       |
| passwd                      | Cambia la contraseña.                                                        | passwd                        |
| ps [axiu]                   | Muestra información sobre los procesos que se están ejecutando en el sistema | ps -ux , ps -ef               |
| who / rwho                  | Muestra información de los usuarios conectados al sistema.                   | who                           |

**Acceso a los parámetros**

los guiones de bash reciben los parámetros que les pasa la shell como $1, $2,..., $n. Podemos saber cuantos hemos recibido con el símbolo $#.
Por ejemplo, si nuestro guion necesita dos parámetros pondremos:
```bash
if [ $# -lt 2 ]; then
    echo "Necesitas pasar dos parámetros."
    exit 1
fi
```
Además disponemos del array $@, el cual contiene todos los parámetros pasados al guion y podemos iterar sobre estos de la siguiente manera:
```bash
for param in  "$@"
do
    echo "$param"
done
```
**Matemáticas con enteros**

Una gran limitación del intérprete Bourne es que no puede realizar cálculos con enteros sin lanzar un proceso externo. En cambio, un proceso Bash puede realizar cálculos con enteros utilizando la orden((...)) y la sintaxis de variables $[...] de la siguiente manera:

```bash
VAR=55                 # Asigna el valor        entero 55 a la variable VAR
((VAR = VAR + 1))      # Suma uno a la variable VAR. Observe la ausencia del carácter  '$'.
((++VAR))              # Otra forma de sumar uno a VAR. Preincremento estilo C.
((VAR++))              # Otra forma de sumar uno a VAR. Postincremento estilo C.
echo $[VAR * 22]       # Multiplica la variable VAR por 22 y sustituye la orden por el resultado.
echo $((VAR * 22))     # Otra forma de realizar lo mismo.
```

La orden ((...)) también se puede utilizar en sentencias condicionales, ya que su [código de retorno](https://es.wikipedia.org/w/index.php?title=C%C3%B3digo_de_retorno&action=edit&redlink=1) es 0 o 1 dependiendo de si la condición cierta o falsa:

```bash
if ((VAR == Y * 3 + X * 2))
then
        echo Si
fi
((Z > 23)) && echo Si
```
La orden ((...)) soporta los siguientes [operadores relacionales](https://meta.wikimedia.org/wiki/w:en:Relational_operator) : **'==', '!=', '>', '<', '>=', y '<='.

Un proceso Bash no puede realizar cálculos en [coma flotante](https://es.wikipedia.org/wiki/Coma_flotante). Los únicos shell Unix capaces de esto son el [Korn Shell](https://es.wikipedia.org/wiki/Korn_Shell) (versión de 1993) y el zsh (a partir de la versión 4.0).

**Redirecciones de entrada/salida**

La sintaxis de Bash permite diferentes formar de [redireción](https://es.wikipedia.org/wiki/Redirecci%C3%B3n) de entrada/salida de las que el shell de Bourne tradicional carece.  Bash puede redirigir la [salida estándar](https://es.wikipedia.org/wiki/Salida_est%C3%A1ndar) y los flujos de [error estándar](https://es.wikipedia.org/wiki/Error_est%C3%A1ndar) a la vez utilizando la sintaxis:

```bash
orden >$ archivo
```

que es más simple que teclear la orden Bourne equivalente, "orden > archivo 2>&1". Desde la versión 2.05b, Bash puede redirigir la entrada estándar desde una cadena utilizando la siguiente sintaxis (denominada "here strings"):

```bash
orden <<< "cadena de leer como entrada estándar"
```

Si la cadena contiene espacios en blanco, deben de utilizarse comillas.

*Ejemplo*:

Redirige la salida estándar a un archivo, escribe datos, cierra el archivo y reinicia [stdout](https://es.wikipedia.org/w/index.php?title=Stdout&action=edit&redlink=1).

```bash
# hace que el descriptor de archivo 6 sea una copia de stdout (descriptor archivo 1)
exec 6>&1
# abre el archivo "test.data" para escritura
exec 1>test.data
# genera algún contenido
echo "data:data:data"
# recupera stdout original, al hacer que sea una copia del descriptor de archivo 6
exec 1>&6
# cierra el descriptor de archivo 6
exec 6>&-
```

**Abre y cierra archivos**

```bash
# abre el archivo test.data para lectura
exec 6<test.data
# lee hasta el final del archivo
while read -u 6 dta
do
    echo "$dta"
done
# cierra el archivo test.data
exec 6<&-
```

**Captura la salida de órdenes externas**

```bash
# ejecuta 'find' y guarda los resultados en VAR
# busca nombres de archivos que terminan con la letra "h"
VAR=$(find . -name "*h")
```

**Expresiones regulares**

Los procesos Bash 3.0 soportan emparejamientos de [expresiones regulares](https://es.wikipedia.org/wiki/Expresi%C3%B3n_regular) utilizando la siguiente sintaxis, reminiscente de [Perl](https://es.wikipedia.org/wiki/Perl):

```bash
[[ string =~ regex]]
```

La sintaxis de expresiones regulares es la misma que documenta la [página de manual](https://es.wikipedia.org/wiki/Man_(Unix) regex(3). El estado de salida de la orden anterior es 0 si la cadena concuerda con la expresión regular, y 1 si no casan. En las expresiones regulares puede accederse a las partes delimitadas por paréntesis, utilizando la variable shell BASH_REMATCH, de la siguiente manera:

```bash
if [[ foobarbletch =~ 'foo(bar)bl(.*)']]
then
     echo The regex matches!
     echo $BASH_REMATCH      -- outputs: foobarbletch
     echo ${BASH_REMATCH[1]} -- outputs: bar
     echo ${BASH_REMATCH[2]} -- outputs: etch
fi
```

Esta sintaxis proporciona un rendimiento superior a lanzar un proceso separado para ejecutar una orden [grep](https://es.wikipedia.org/wiki/Grep), porque el emparejamiento de las expresiones regulares tiene lugar en el propio proceso Bash. Si la expresión regular o la cadena contiene un espacio en blanco o un [metacarácter](https://es.wikipedia.org/wiki/Metacar%C3%A1cter) del shell (como '*' o '?'), debe ser entrecomillada.

**Escape con contrabarra**

Las palabras con la forma $'string' se tratan de un modo especial. Estas palabras se expanden a string, con los caracteres escapados por la contrabarra reemplazados según especifica el [lenguaje de programación C](https://es.wikipedia.org/wiki/Lenguaje_de_programaci%C3%B3n_C). Las secuencias de escape con contrabarra, se decodifican del siguiente modo:

                                                 Escapes con contrabarra

| Backslash escape    |                                     Se expande a...                                            |
|---------------------|------------------------------------------------------------------------------------------------|
| \b                  | Un carácter de retroceso                                                                       |
| \e                  | Un carácter de escape                                                                          |
| \f                  | Un carácter de alimentación de línea (form feed)                                               |
| \n                  | Un carácter de nueva línea                                                                     |
| \r                  | Un carácter de retorno de carro                                                                |
| \t                  | Un tabulador horizontal                                                                        |
| \v                  | Un tabulador vertical                                                                          |
| \\                  | Un carácter contrabarra                                                                        |
| \'                  | Un carácter de comilla simple                                                                  |
| \nnn                | El carácter de 8 bits cuyo valor es el número octal nnn (de uno a tres dígitos)                |
| \xHH                | El carácter de 8 bits cuyo valor es el número hexadecimal HH (uno o dos dígitos hexadecimales) |
| \cx                 | Un carácter control-X                                                                          |

**Guiones de inicio de Bash**

Cuando Bash arranca, ejecuta las órdenes que se encuentran en diferentes guiones.

Cuando se invoca a Bash como un shell interactivo para el inicio de una sesión (]]login shell]]), o como un shell no interactivo con la opción --login, en primer lugar lee y ejecuta órdenes desde el archivo /etc/profile, si existe. Después, busca ~/.bash_profile, ~/.bash_login, y ~/.profile, en este orden, y lee y ejecuta las órdenes desde el primero que existe y es legible. La opción --noprofile puede utilizarse al comenzar un nuevo shell para inhibir este comportamiento.

Cuando un **login shell** termina, Bash lee y ejecuta las órdenes de ~/.bash_logout, si existe.

Cuando un shell interactivo que no es un login shell arranca, Bash lee y ejecuta órdenes desde ~/.bashrc, si existiese. Esto puede evitarse utilizando la opción --norc. La opción --rcfile archivo forzará a Bash a leer y ejecutar órdenes desde archivo en lugar de ~/.bashrc.

Cuando Bash arranca de un modo no interactivo, por ejemplo para ejecutar un guion de consola diferente, busca la variable de entorno BASH_ENV, si existe expande su valor, y lo utiliza como el nombre del archivo para leer y ejecutar. Bash se comporta como si se ejecutase la siguiente orden:

```bash
if [ -n "$BASH_ENV" ]; then . "$BASH_ENV"; fi
```

pero el valor de la variable PATH no se utiliza para buscar el archivo.

Si se invoca a Bash con el nombre sh, intenta replicar el comportamiento de las versiones antiguas de sh, a la vez que se mantiene la conformidad con el estándar POSIX. Cuando se invoca como un login shell interactivo, o un shell no interactivo con la opción --login, primero intenta leer y ejecutar órdenes desde /etc/profile y ~/.profile, en este orden. La opción --noprofile puede utilizarse para evitar este comportamiento.

Cuando se invoca como un shell interactivo con el nombre sh, Bash busca la variable ENV, si está definida expande su valor, y utiliza el valor expandido como el nombre de un archivo para leer y ejecutar. Como un shell invocado como sh no intenta leer y ejecutar órdenes desde ningún otro archivo de arranque, y la opción --rcfile no tiene efecto. Un shell no interactivo invocado con el nombre sh no intenta leer ningún otro archivo de arranque. Cuando se invoca como sh, Bash entra en el modo posix después de leer los archivos de inicio.

Cuando se inicia Bash en el modo posix, por ejemplo con la opción --posix, sigue el estándar [POSIX](https://es.wikipedia.org/wiki/POSIX) para los archivos de inicio. En este modo, los shells interactivos expanden la variable ENV y se leen, y ejecutan, las órdenes desde el archivo cuyo nombre es el valor de la variable expandida. No se lee ningún otro archivo de arranque.

Bash intenta determinar cuando está siendo ejecutado por un dominio de shell remoto, normalmente rshd. Si Bash determina que está siendo ejecutado por rshd, lee y ejecuta órdenes desde ~/.bashrc, si este archivo existe y es legible. No hará esto si se invoca como sh. La opción --norc puede utilizarse para evitar este comportamiento, y la opción --rcfile puede utilizarse para forzar a leer otro archivo, pero rshd normalmente no invoca al shell con estas opciones o permite que sean especificadas.

**Bashismo**

Se llama bashismo al uso de características de Bash que no están contempladas en las especificaciones [POSIX](https://es.wikipedia.org/wiki/POSIX) para los intérpretes de comandos. En general, se recomienda evitarlas, para permitir la portabilidad de guiones a otros sistemas operativos.



                                                           Comandos Bash



| Comando | Descripción                                     |
|---------|-------------------------------------------------|
| man     | Muestra el manual del comando que le indiquemos |
| info    | Provee información del comando indicado         |
| help    | Da una ayuda de los comandos                    |
| whatis  | Da una breve descripción de los comandos        |


**Comandos para archivos y directorios**

| Comando    | Descripción                                                                            |
|------------|----------------------------------------------------------------------------------------|
| ls         | Lista los archivos y directorios                                                       |
| sort       | Ordena alfabéticamente una lista de archivos                                           |
| cd         | Cambia de directorio                                                                   |
| pwd        | Muestra la ruta al directorio actual                                                   |
| tree       | Muestra la estructura de directorios y archivos en forma gráfica                       |
| mkdir      | Crea un directorio                                                                     |
| rmdir      | Borra directorios (los directorios deben estar vacíos).                                |
| rm -r      | Borra directorios (los directorios pueden no estar vacíos)                             |
| cp         | Copia archivos                                                                         |
| rm         | Borra archivos                                                                         |
| mv         | Mueve o renombra archivos y directorios                                                |
| cat        | Muestra el contenido de uno o varios archivos                                          |
| more       | Ve el contenido de los archivos página a página                                        |
| less       | Ve el contenido de los archivos                                                        |
| split      | Dividir archivos                                                                       |
| find       | Busca archivos                                                                         |
| locate     | Localiza archivos según una lista generada                                             |
| updatedb   | Actualiza la lista de los archivos existentes                                          |
| whereis    | Muestra la ubicación de un archivo                                                     |
| file       | Muestra el tipo de archivo                                                             |
| whatis     | Muestra descripción del archivo                                                        |
| wc         | Muestra el total de líneas, palabras o caracteres en un archivo                        |
| grep       | Busca un texto en un archivos                                                          |
| head       | Muestra el inicio de un archivo                                                        |
| tail       | Muestra el final de un archivo                                                         |
| tailf      | Muestra el final de un archivo y lo que se añada en el instante (logs)                 |
| tr         | Reemplaza caracteres en un fichero de texto                                            |
| sed        | Cambia una cadena de caracteres por otra                                               |
| join       | Cruza la información de dos archivos y muestra las partes que se repiten               |
| paste      | Toma la primera línea de cada archivo y las combina para formar una línea de salida    |
| uniq       | Elimina líneas repetidas adyacentes del archivo entrada cuando copia al archivo salida |
| cut        | Sirve para seleccionar columnas de una tabla o campos de cada línea de archivo         |
| ln         | Crea enlaces a archivos o carpetas                                                     |
| diff       | Muestra las diferencias entre dos archivos                                             |
| fuser      | Muestra que usuario tiene en uso o bloqueado un archivo o recurso                      |
| tar        | Empaqueta archivos                                                                     |
| gzip       | Comprime archivos en formato .gz                                                       |
| gunzip     | Descomprime archivos en formato .gz                                                    |
| compress   | Comprime archivos Z                                                                    |
| uncompress | Descomprime archivos Z                                                                 |
| chmod      | Cambia permisos de archivos y directorios                                              |
| chown      | Cambia de propietario/usuario                                                          |
| chgrp      | Cambia de grupo                                                                        |
| vi         | Abre el editor de texto vi                                                             |
| nano       | Abre el editor de texto nano                                                           |
| pico       | Edita un fichero de texto                                                              |


**Comandos para la gestión de usuarios**

| Comando  | Descripción                                                       |
|----------|-------------------------------------------------------------------|
| adduser  | Agrega un nuevo usuario                                           |
| useradd  | Agrega un nuevo usuario                                           |
| userdel  | Borra un usuario                                                  |
| passwd   | Permite cambiar la contraseña                                     |
| su       | Cambia de usuario                                                 |
| whoami   | Muestra el nombre de usuario actual                               |
| logname  | Muestra el nombre de usuario                                      |
| id       | Muestra datos de identificación del usuario                       |
| finger   | Da información de usuario                                         |
| chfn     | Cambia la información propocionada por el comando finger          |
| who      | Muestra los usuarios actuales del sistema                         |
| w        | Muestra detalles de los usuarios actuales aplicado al comando who |
| last     | Información de los últimos usuarios que han usado el sistema      |
| mail     | Abre la aplicación de correo electrónico                          |
| pine     | Lector de correo en modo texto                                    |
| write    | Manda un mensaje a la pantalla de un usuario                      |
| mesg     | Activa o desactiva la función de recepción de mensajes            |
| wall     | Envía mensaje a todos los usuarios                                |
| talk     | Establecer una conversación/diálogo con otro usuario              |
| banner   | Saca un diálogo/letrero en la pantalla                            |
| set      | Proporciona información sobre el entorno del usuario              |
| addgroup | Agrega un nuevo grupo                                             |
| groupadd | Agrega un nuevo grupo                                             |
| chown    | Cambia el propietario de un fichero                               |


**Comandos para la gestión de procesos**

| Comando | Descripción                                                             |
|---------|-------------------------------------------------------------------------|
| top     | Muestra los procesos que se están ejecutando y permite matarlos         |
| ps      | Muestra la lista de procesos del usuario                                |
| ps aux  | Muestra la lista de procesos de la máquina                              |
| kill    | Envía un evento concreto a un proceso                                   |
| killall | Mata un proceso por su nombre                                           |
| time    | Mide el tiempo que tarda un proceso en ejecutarse                       |
| fg      | Trae a primer plano un proceso parado o en segundo plano                |
| bg      | Pone un proceso en segundo plano                                        |
| &       | Colocado al final de la línea de un comando,lo ejecuta en segundo plano |
| nice    | Ajusta la prioridad de un proceso de -20 a 19                           |


**Comandos para la gestión de discos y dispositivos**

| Comando | Descripción                                                       |
|---------|-------------------------------------------------------------------|
| mount   | Monta un disco/dispositivo                                        |
| umount  | Desmonta un disco/dispositivo                                     |
| df      | Muestra el espacio libre de los discos/dispositivos               |
| du      | Muestra el espacio usado por el disco/dispositivo o un directorio |
| mkfs    | Formatea un disco/dispositivo                                     |
| fsck    | Estado del disco/dispositivo                                      |
| fdisk   | Abre la aplicación para la gestión de particiones                 |


**Comandos para el acceso remoto**

| Comando | Descripción                                              |
|---------|----------------------------------------------------------|
| rlogin  | Se conecta a otra máquina de forma remota (remote login) |
| rsh     | Se conecta a otra máquina de forma remota (remote shell) |
| ftp     | Se conecta a otra máquina por el protocolo FTP           |


**Comandos para el apagado y reinicio del sistema**

| Comando  | Descripción                 |
|----------|-----------------------------|
| reboot   | Reinicia la máquina         |
| halt     | Apaga el sistema            |
| shutdown | Apaga el sistema            |
| init 0   | Apaga la máquina            |
| init 6   | Reinicia la máquina         |
| reisub   | Reinicia en caso de bloqueo |

**Comandos para la gestión del sistema**

| Comando   | Descripción                                                                                             |
|-----------|---------------------------------------------------------------------------------------------------------|
| uptime    | Muestra el tiempo transcurrido de encendido de la máquina                                               |
| exit      | Cerrar sesión actual                                                                                    |
| logout    | Salir del sistema                                                                                       |
| nohup     | Proporciona inmunidad frente a rupturas de comunicación y abandonos en ejecución de comandos            |
| dmesg     | Muestra mensajes del arranque de la máquina                                                             |
| history   | Muestra todos los comandos escritos por el usuario                                                      |
| uname     | Proporciona información del sistema operativo                                                           |
| tee       | Copia la entrada estándar a la salida estándar y a un archivo                                           |
| host      | Muestra la dirección IP del servidor en una red local. Ej: host malpelo.univalle.edu.co => 192.168.31.5 |
| hostname  | Muestra el nombre del servidor                                                                          |
| umask     | Muestra y permite cambiar la máscara de usuario                                                         |
| chroot    | Cambia la raíz para que root ejecute algo de forma particular                                           |
| chsh      | Cambia el login shell                                                                                   |
| free      | Muestra el estado de la memoria                                                                         |
| date      | Muestra la fecha y hora actual                                                                          |
| cal       | Muestra el calendario                                                                                   |
| clear     | Borra las líneas de texto escritas en la pantalla/terminal                                              |
| at        | Ejecuta un comando con un retardo de tiempo especificado                                                |
| env       | Muestra las variables de entorno                                                                        |
| export    | Permite el uso de variables por programas en todos los caminos del usuario                              |
| modprobe  | Carga un módulo                                                                                         |
| startx    | Arranca/inicia el servidor X                                                                            |
| xev       | Muestra los eventos de las teclas y el ratón                                                            |
| lspci     | Muestra los periféricos conectados al puente PCI                                                        |
| lsmod     | Muestra los módulos cargados en el sistema                                                              |
| echo      | Escribe un mensaje en la salida estándar                                                                |
| alias     | Crea un alias                                                                                           |
| unalias   | Borra un alias                                                                                          |
| bc        | Muestra la calculadora                                                                                  |
| mc        | Ejecuta Midnight Commander                                                                              |
| xkill     | Mata una ventana gráfica                                                                                |
| rpm       | Instala los paquetes RPM de RedHat                                                                      |
| dpkg      | Instala los paquetes DEB de Debian                                                                      |
| kernelcfg | Manejo de los módulos cargados en el kernel                                                             |
| insmod    | Inserta módulos en el kernel                                                                            |
| rmmod     | Elimina módulos del kernel                                                                              |
| updatedb  | Actualiza la base de datos interna de archivos                                                          |
| sh        | Cambia al bash/shell                                                                                    |
| setxkbmap | Realiza la función de la tecla AltGr (en modo X)                                                        |


**Comandos de red**

| Comando    | Descripción                                                                                                                         |
|------------|-------------------------------------------------------------------------------------------------------------------------------------|
| netstat    | Muestra estado de la red                                                                                                            |
| ifconfig   | Muestra la configuración del dispositivo de red                                                                                     |
| iwconfig   | Muestra la configuración del dispositivo de red inalámbrico                                                                         |
| nmap       | Escanea la red y muestra los puertos que se encuentran disponibles. Ej: nmap malpelo.univalle.edu.co/~ahbarome/ => 80/tcp open http |
| ping       | Indica si hay respuesta por parte del servidor                                                                                      |
| nslookup   | Muestra la IP del servidor DNS conectado(Servidor predeterminado: UnKnown Address: 192.168.1.1)                                     |
| telnet     | Conexión a un equipo/máquina de forma remota                                                                                        |
| netconf    | Configuración de la red                                                                                                             |
| ntop       | Muestra los procesos de la red                                                                                                      |
| route -n   | Muestra la tabla de rutas de la conexión de red                                                                                     |
| installpkg | Instalar en slackware                                                                                                               |


**Comandos para gestión de impresoras**

| Comando   | Descripción                                             |
|-----------|---------------------------------------------------------|
| lpq       | Muestra las colas de impresión                          |
| lpc       | Estado de las impresoras                                |
| lprm      | Elimina un trabajo de la cola de impresión              |
| printtool | Configuración de la impresora                           |
| pr        | Imprime un archivo                                      |
| jobs      | Muestra los trabajos que están en una cola de impresión |


**Combinación especial de teclas**

| Comando        | Descripción                                                  |
|----------------|--------------------------------------------------------------|
| ctrl+l         | Borra las líneas de texto de pantalla/terminal               |
| ctrl+alt+F1 F2 | Cambio de consola                                            |
| ctrl+F1 F2     | Cambio de escritorio                                         |
| ctrl+z         | Suspensión de un proceso                                     |
| ctrl+d         | Muestra el final de un archivo EOF                           |
| ctrl+c         | Termina/finaliza un proceso en ejecución                     |
| tab            | Completa nombres de carpetas o archivos                      |
| ctrl+backspace | Cierra el modo X (sale del sistema X y regresa a la consola) |


**Símbolos**

| Comando               | Descripción                                                                |
|-----------------------|----------------------------------------------------------------------------|
| ~                     | Apagar el equipo por otros medios (alt+126)                                |
| .                     | Ubicación en directorio actual                                             |
| |                     | Redirección de comandos. Pipeline o tubería (alt+124)                      |
| >                     | Redirecciona la salida estándar (stdout) de un comando (alt+62)            |
| 2>                    | Redirecciona la salida estándar de errores (stderr) de un comando (alt+62) |
| <                     | Redirecciona un comando (alt+60)                                           |
| &                     | Colocado al final de la línea de comando, lo ejecuta en segundo plano      |
| && orden_1 && orden_2 | Ejecuta la orden_2 si la orden_1 termina correctamente (OK)                |
| || orden_1 || orden_2 | Ejecuta la orden_2 si la orden_1 no termina correctamente (OK)             |





> Definición sobre Bash de la Wikipedia: [wiki/Bash](https://es.wikipedia.org/wiki/Bash)
