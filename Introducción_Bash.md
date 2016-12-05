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

    !#/bin/bash
    # Script de Hola Mundo
    echo "Hola Mundo"
    
Salida:

    Hola Mundo

**Comentario en Bash**

Pero ¿el símbolo '#' escrito al inicio de una linea, es un comentario? En realidad sí, como en la segunda linea vemos, eso es un comentario, es decir, algo que no es interpretado y está ahí para que el programador/coder/scripter se ubique y sepa que es lo que hace el código, esto ayuda a tener mejor orden y al corregir el codigo si tiene BUGS. Pero la excepción a esto, es al escribir #!/ruta/de/interprete , esto nos sirve para llamar a nuestro interprete, como perl, bash, sh, python, etc, (que son otros lenguajes) y se usa para los lenguajes interpretados, de modo que se ejecuten en donde corresponde....

**Imprimiendo en Bash**

Por último, tenemos el comando ``echo``, como en ``batch``, que sirve para imprimir texto en la pantalla.

BASH funciona igual que nuestra terminal favorita, esto es por que nuestra terminal usa BASH para funcionar, y claro, cuando hacemos scripts es para automatizar procesos. Así es que la sintaxis es muy simple, un comando por línea.

Recomendamos leer los manuales y experimentar en el sistema operativo (claro sin ser root si no sabemos que es lo que hacemos) para aprender.

Como en todo lenguaje, necesitamos del uso de variables, que nos servirán para todo lo que queramos hacer en determinadas situaciones. Una variable, es una cadena de datos que se almacena en la memoria y que podemos llamar en cualquier momento para darle ``X`` uso.

**Asignando variables**

En BASH, las variables se asignan simplemente dando el nombre de la variable y su valor:

    #!/bin/bash
    #Asignando variables
    hola=1

Como podemos leer aquí, este código asigna el valor 1 a la variable "hola". En BASH las variables son "CASE SENSITIVE" (sensibles), es decir, la variable ``Hola`` no es lo mismo que ``HOLA`` ni que ``holA``.

Otro de los puntos importantes de las variables en BASH es que no tenemos que asignarles un tipo, es decir, podemos darle a las variables cualquier valor y lo aceptará sin tener que decirle a BASH si es numérico o si son letras.

**Invocando variables**

Ya sabemos asignar una variable, pero de poco nos sirve si no podemos llamarla.

En BASH, las variables las invocamos simplemente anteponiendo un símbolo de dolar '$' antes del nombre de la variable.
Ejemplo:

    #!/bin/bash
    #Asignando variables
    hola=1
    #Llamando a la variable $hola
    $hola
    #Mostrando el contenido de la variable
    echo $hola

Explicación

Si ponemos atención al código, en BASH, las variables simplemente se reemplazan por su valor al llamarlas, de modo que en ellas podemos almacenar X texto ó numero, ya sean comandos o lo que sea.

Al llamar a la variable, observamos que simplemente da el valor y lo pasa como una orden al interprete, pero si lo ponemos siguiendo un comando como ``echo`` entonces este mostrará el contenido de la variable.

Ejemplo de uso:

    #!/bin/bash
    #
    # Se guarda en la variable el valor generado    por $RANDOM,
    # el % 5 asegura obtener un numero menor a 5 .
    RNM=`expr $RANDOM % 5`
    echo $RNM

**Comandos básicos**

Para poder trabajar eficientemente en BASH, es indispensable conocer los comandos más básicos, aquí una pequeña lista que debemos conocer a la perfección:

                               Comandos básicos para BASH

|Comando [Opciones]           |Descripción del comando                    |Ejemplo de uso|          |:---------------             | :----------------------                   | :-------------|
|cat fich1 [...fichN]         |Concatena y muestra un archivos            |cat /etc/passwd
|cd [dir]                     |Cambia de directorio                       |cd /tmp
|chmod permisos fich          |Cambia los permisos de un archivo          |chmod +x miscript
|chown usuario:grupo fich     |Cambia el dueño de un archivo              |chown nobody miscript                                               
|cp fich1...fichN dir         |Copia archivos                             |cp foo foo.backup                                  
|diff [-e]arch1 arch2         |Encuentra diferencias entre archivos       |diff foo.c newfoo.c
|du [-sabr] fich              |Reporta el tamaño del archivo              |du -s /home/
|file arch                    |Muestra el tipo de un archivo              |file arc_desconocido
|find dir test acción         |Encuentra archivos                         |find . -name ``.bak -
                                                                           print
|grep [-cilnv] expr archivos  |Busca patrones en archivos                 |grep mike /etc/passwd
|head -count fich             |Muestra el inicio de un archivo            |head prog1.c
|mkdir dir                    |Crea un directorio                         |mkdir temp
|mv fich1 ...fichN dir        |Mueve un archivo(s) a un directorio        |mv a.out prog1
|mv fich1 fich2               |Renombra un archivo                        |mv .c prog_dir
|less / more fich(s)          |Visualiza página a página un archivo       |less muy_largo.c
                              less acepta comandos vi 
|ln [-s] fich acceso          |Crea un acceso directo a un archivo        |ln -s /users/
                                                                           mike/.profile
|ls                           |Lista el contenido del directorio          |ls -l /usr/bin
|pwd                          |Muestra la ruta del directorio actual      |pwd
|rm fich                      |Borra un fichero                           |rm foo.c
|rm -r dir                    |Borra todo un directorio                   |rm -rf prog_dir
|rmdir dir                    |Borra un directorio vacío                  |rmdir prog_dir
|tail -count fich             |Muestra el final de un archivo             |tail prog1.c
|at [-lr] hora [fecha]        |Ejecuta un comando mas tarde               |at 6pm Friday miscript
|cal [[mes] año]              |Muestra un calendario del mes/año          |cal 1 2025
|date [mmddhhmm] [+form]      |Muestra la hora y la fecha                 |date
|echo string                  |Escribe mensaje en la salida estándard     |echo id usuario``Hola mundo
|finger usuario               |Muestra información general sobre un 
                               usuario en la red                          |finger nn
                                                                           @maquina.aca.com.co
|id                           |Número id de un usuario                    |id usuario
|kill [-señal] PID            |Matar un proceso                           |kill 1234                      
|man comando                  |Ayuda del comando especificad              |man gcc,man -k printer
|passwd                       |Cambia la contraseña                       |passwd
|ps [axiu]                    |Muestra información sobre los procesos     |ps -ux , ps -ef
                               que se están 
                               ejecutando en el sistema
|who / rwho                   |Muestra información de los usuarios        |who
                               conectados al sistema


**Acceso a los parámetros**

los guiones de bash reciben los parámetros que les pasa la shell como $1, $2,..., $n. Podemos saber cuantos hemos recibido con el símbolo $#.
Por ejemplo, si nuestro guion necesita dos parámetros pondremos:

    
    if [ $# -lt 2 ]; then
    echo "Necesitas pasar dos parámetros."
    exit 1
    fi
    
Además disponemos del array $@, el cual contiene todos los parámetros pasados al guion y podemos iterar sobre estos de la siguiente manera:

    
    for param in  "$@"
    do
     echo "$param"
    done
    

**Matemáticas con enteros**

Una gran limitación del intérprete Bourne es que no puede realizar cálculos con enteros sin lanzar un proceso externo. En cambio, un proceso Bash puede realizar cálculos con enteros utilizando la orden((...)) y la sintaxis de variables $[...] de la siguiente manera:

    
    VAR=55                 # Asigna el valor        entero 55 a la variable VAR
    ((VAR = VAR + 1))      # Suma uno a la variable VAR. Observe la ausencia del carácter  '$'.
    ((++VAR))              # Otra forma de sumar uno a VAR. Preincremento estilo C.
    ((VAR++))              # Otra forma de sumar uno a VAR. Postincremento estilo C.
    echo $[VAR * 22]       # Multiplica la variable VAR por 22 y sustituye la orden por el     resultado.
    echo $((VAR * 22))     # Otra forma de realizar lo mismo.
    

La orden ((...)) también se puede utilizar en sentencias condicionales, ya que su código de retorno es 0 o 1 dependiendo de si la condición cierta o falsa:

    
    if ((VAR == Y * 3 + X * 2))
    then
        echo Si
    fi
    ((Z > 23)) && echo Si
    

La orden ((...)) soporta los siguientes operadores relacionales : **'==', '!=', '>', '<', '>=', y '<='.

Un proceso Bash no puede realizar cálculos en coma flotante. Los únicos shell Unix capaces de esto son el Korn Shell (versión de 1993) y el zsh (a partir de la versión 4.0).

**Redirecciones de entrada/salida**

La sintaxis de Bash permite diferentes formar de redireción de entrada/salida de las que el shell de Bourne tradicional carece.  Bash puede redirigir la salida estándar y los flujos de error estándar a la vez utilizando la sintaxis:

    
    orden >$ archivo
    
que es más simple que teclear la orden Bourne equivalente, "orden > archivo 2>&1". Desde la versión 2.05b, Bash puede redirigir la entrada estándar desde una cadena utilizando la siguiente sintaxis (denominada "here strings"):

    
    orden <<< "cadena de leer como entrada   estándar"
    

Si la cadena contiene espacios en blanco, deben de utilizarse comillas.
**Ejemplo** Redirige la salida estándar a un archivo, escribe datos, cierra el archivo y reinicia stdout.

    
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
    
Abre y cierra archivos

    
    # abre el archivo test.data para lectura
    exec 6<test.data
    # lee hasta el final del archivo
    while read -u 6 dta
    do
    echo "$dta" 
    done
    # cierra el archivo test.data
    exec 6<&-
    

Captura la salida de órdenes externas

    
    # ejecuta 'find' y guarda los resultados en VAR
    # busca nombres de archivos que terminan con la letra "h"
    VAR=$(find . -name "*h")
    

**Expresiones regulares**

Los procesos Bash 3.0 soportan emparejamientos de expresiones regulares utilizando la siguiente sintaxis, reminiscente de Perl:

    
    [[ string =~ regex]]
    

La sintaxis de expresiones regulares es la misma que documenta la página de manual regex(3). El estado de salida de la orden anterior es 0 si la cadena concuerda con la expresión regular, y 1 si no casan. En las expresiones regulares puede accederse a las partes delimitadas por paréntesis, utilizando la variable shell BASH_REMATCH, de la siguiente manera:

    
    if [[ foobarbletch =~ 'foo(bar)bl(.*)']] 
    then
         echo The regex matches!
         echo $BASH_REMATCH      -- outputs:     foobarbletch
         echo ${BASH_REMATCH[1]} -- outputs: bar
         echo ${BASH_REMATCH[2]} -- outputs:   etch
    fi
    

Esta sintaxis proporciona un rendimiento superior a lanzar un proceso separado para ejecutar una orden grep, porque el emparejamiento de las expresiones regulares tiene lugar en el propio proceso Bash. Si la expresión regular o la cadena contiene un espacio en blanco o un metacarácter del shell (como '*' o '?'), debe ser entrecomillada.

**Escape con contrabarra**





