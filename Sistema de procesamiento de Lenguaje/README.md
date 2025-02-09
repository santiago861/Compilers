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