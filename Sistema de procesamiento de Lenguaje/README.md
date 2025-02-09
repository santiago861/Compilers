<h3>En el caso de clang vamos a usar los siguientes comandos</h3>
<code>clang -E programa.c -o programa.i</code>  # Preprocesar <br>
<code>clang -S programa.i -o programa.s</code>  # Compilar a ensamblador <br>
<code>clang -c programa.s -o programa.o</code>  # Generar código objeto <br>
<code>clang programa.o -o programa</code>   # Enlazar y crear el ejecutable <br>


<h2>Use el siguiente comando: <code>cpp programa.c programa.i</code> Revise el contenido de programa.i y conteste lo siguiente:</h2>
<h3>El preprocesador recopila y expande macros y otros fragmentos de código abreviado en el programa fuente.</h3>
<p>En este caso estamos usando clang, por lo que para este punto utilizamos <code>clang -E programa.c -o programa.i</code></p>
<ul>
    <li>¿Qué ocurre cuando se invoca el comando cpp con esos argumentos?</li>
        <p>Este comando ejecuta la fase de preprocesamiento del archivo <code>programa.c</code> y el resultado se guarda en <code>programa.i</code></p><br>
    <li>¿Qué similitudes encuentra entre los archivos programa.c y programa.i?</li>
    <ul>
        <p>No logramos encontrar mucha similitud entre los archivo, el archivo <code>programa.i</code> es mucho más grande que <code>programa.c</code></p>
    </ul>
    <li>¿Qué pasa con las macros y los comentarios del código fuente original en programa.i?</li>
    <ul>
        <p>Las macros condicionales, definiciones y expansiones son resueltas. En el código, dado que la macro PI está comentada, el preprocesador elige la 
        opción del <code>#else</code</p><br>
        <p>Los comentarios, tanto los de linea como los de bloque son eliminados en el archivo preprocesado</p><br>
        <p>Las cabeceras estándar <code>#include <stdio.h></code>, <code>#include <stdlib.h></code> son expandidas, es decir, todo el contenido de esas 
        cabeceras es copiado al archivo programa.i, por esto el archivo <code>programa.i</code> es mucho más grande
    </ul>
    <li>Compare el contenido de programa.i con el de stdio.h e indique de forma general las similitudes entre ambos archivos.</li>
    <ul>
        <p>dsaf</p>
    </ul>
    <li>¿A qué etapa corresponde este proceso?</li>
    <ul>
        <p>dsaf</p>
    </ul>
</ul>