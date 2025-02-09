<h3>En el caso de clang vamos a usar los siguientes comandos</h3>
<code>clang -E programa.c -o programa.i</code>  # Preprocesar <br>
<code>clang -Wall -S programa.i -o programa.s</code>  # Compilar a ensamblador <br>
<code>clang -c programa.s -o programa.o</code>  # Generar código objeto <br>
<code>clang programa.o -o programa</code>   # Enlazar y crear el ejecutable <br>


<h2>3. Use el siguiente comando: <code>cpp programa.c programa.i</code> Revise el contenido de programa.i y conteste lo siguiente:</h2>
<h3>El preprocesador recopila y expande macros y otros fragmentos de código abreviado en el programa fuente.</h3>
<p>En este caso estamos usando clang, por lo que para este punto utilizamos <code>clang -E programa.c -o programa.i</code>.</p>
<ul>
    <li>¿Qué ocurre cuando se invoca el comando cpp con esos argumentos?</li>
        <p>Este comando ejecuta la fase de preprocesamiento del archivo <code>programa.c</code> y el resultado se guarda en <code>programa.i</code>.</p>
    <li>¿Qué similitudes encuentra entre los archivos <code>programa.c</code> y <code>programa.i</code>?</li>
        <p>No logramos encontrar mucha similitud entre los archivo, el archivo <code>programa.i</code> es mucho más grande que <code>programa.c</code>.</p>
    <li>¿Qué pasa con las macros y los comentarios del código fuente original en <code>programa.i?</code></li>
        <p>Las macros condicionales, definiciones y expansiones son resueltas. En el código, dado que la macro PI está comentada, el preprocesador elige la opción del 
        <code>#else</code>. Los comentarios, tanto los de linea como los de bloque son eliminados en el archivo preprocesado. Las cabeceras estándar <code>#include<stdio.h></code>, <code>#include<stdlib.h></code> son expandidas, es decir, todo el contenido de esas cabeceras es copiado al archivo <code>programa.i</code>, por esto el archivo <code>programa.i</code> es mucho más grande.</p>
    <li>Compare el contenido de <code>programa.i</code> con el de <code>stdio.h</code> e indique de forma general las similitudes entre ambos archivos.</li>
        <p>Tienen similitudes en las definiciones de funciones estándar, como <code>printf</code>, así como en la presencia de tipos y macros estándar. Sin embargo, 
        <code>programa.i</code> también contiene el código fuente del programa original y el contenido expandido de otras cabeceras (<code>stdlib.h</code>, etc.), mientras que <code>stdio.h</code> solo define las funciones y tipos relacionados con la entrada/salida estándar. Además, las directivas de preprocesador de <code>stdio.h</code> desaparecen en <code>programa.i</code>.</p>
    <li>¿A qué etapa corresponde este proceso?</li>
        <p>Corresponde a la fase de preprocesamiento del archivo <code>programa.c</code></p>
</ul>


<h2>4. Ejecute la siguiente instrucción: <code>gcc -Wall -S programa.i</code></h2>
<h3>El compilador transforma el código preprocesado en un programa objeto en lenguaje ensamblador, que es posteriormente convertido en código máquina por el ensamblador.</h3>
<p>En este caso estamos usando clang, por lo que para este punto utilizamos <code>clang -Wall -S programa.i -o programa.s</code>.</p>
<ul>
    <li>¿Para qué sirve la opción <code>-Wall</code>?
        <p>Activa la mayoría de las advertencias durante la compilación, lo que puede mostrar mensajes sobre posibles problemas en el código.</p>
    </li>
    <li>¿Qué le indica a gcc la opción <code>-S</code>?
        <p>Indica que el compilador debe detenerse después de la fase de generación de código ensamblador.</p>
    </li>
    <li>¿Qué contiene el archivo de salida y cuál es su extensión?
        <p>Contiene el código ensamblador del programa, es decir, una representación de bajo nivel que será utilizada por el ensamblador para crear el código objeto en el siguiente paso.</p>
    </li>
    <li>¿A qué etapa corresponde este comando?
        <p>Corresponde a la etapa de generación de código ensamblador.</p>
    </li>
</ul>


<h2>5. Ejecute la siguiente instrucción: <code>as programa.s -o programa.o</code></h2>

<p>En este caso estamos usando clang, por lo que para este punto utilizamos <code>clang -c programa.s -o programa.o</code>.</p>
<ul>
    <li>Antes de revisarlo, indique cuál es su hipótesis sobre lo que debe contener el archivo con extensión <code>.o</code>.
        <p>sadfdsf</p>
    </li>
    <li>Diga de forma general qué contiene el archivo <code>programa.o</code> y por qué se visualiza de esa manera.
        <p>sadfdsf</p>
    </li>
    <li>¿Qué programa se invoca con <code>as</code>?
        <p>sadfdsf</p>
    </li>
    <li>¿A qué etapa corresponde la llamada a este programa?
        <p>sadfdsf</p>
    </li>
</ul>



<h2>6. Encuentre la ruta de los siguientes archivos en el equipo de trabajo:</code>
<ul>
    <li>Scrt1.o
        <p>sadfadsf</p>
    </li>
    <li>crti.o
        <p>sadfadsf</p>
    </li>
    <li>crtbeginS.o
        <p>sadfadsf</p>
    </li>
    <li>crtendS.o
        <p>sadfadsf</p>
    </li>
    <li>crtn.o
        <p>sadfadsf</p>
    </li>
</ul>


<h2>7. Ejecute el siguiente comando, sustituyendo las rutas que encontró en el paso anterior:</h2>
<code>ld -o ejecutable -dynamic-linker /lib/ld-linux-x86-64.so.2 /usr/lib/crt1.o /usr/lib/crti.o programa.o -lc /usr/lib/crtn.o</code>

<ul>
    <li>En caso de que el comando <code>ld</code> mande errores, investigue como enlazar un programa utilizando el comando <code>ld</code>. Y proponga una posible solución para llevar a cabo este proceso con éxito.
        <p>sadfa</p>
    </li>
    <li>Describa el resultado obtenido al ejecutar el comando anterior.
        <p>sadfa</p>
    </li>
</ul>




<h2>8. Una vez que se enlazó el código máquina relocalizable, podemos ejecutar el programa con la siguiente instrucción en la terminal: <code>./programa</code></h2>


<h2>9. Quite el comentario de la macro <code>#define PI</code> en el código fuente original y conteste lo siguiente:</h2>
<ul>
    <li>Genere nuevamente el <code>archivo.i</code>. De preferencia asigne un nuevo nombre.
    </li>
    <li>¿Cambia en algo la ejecución final?
        <p>sadf</p>
    </li>
</ul>


<h2>9. Escribe un segundo programa en lenguaje C en el que agregue 4 directivas del preprocesador de C (cpp). Las directivas elegidas deben jugar algún papel en el significado del programa, ser distintas entre sí y diferentes de las utilizadas en el primer programa (aunque no están prohibidas si las requieren).</h2>
<ul>
    <li>Explique su utilidad general y su función en particular para su programa.
        <p>asdfasd</p>
    </li>
</ul>

<h2>Redacte un informe detallado con sus resultados y conclusiones.</h2>












