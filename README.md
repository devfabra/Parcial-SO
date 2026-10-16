# Parcial-SO

> Integrantes de parcial: Said Sepulveda, Miguel Rodriguez, Sebastian Fabra, Julian Rodriguez<br><br>
> Curso: Sistemas Operativos

## Pregunta-1
**B.La sustitución de comandos, que asigna a una variable la salida del comando date.** 
*Debido a que la sustitución de comandos ($(...)) captura la salida de date en una variable, que luego se usa para construir un nombre de archivo único en cada ejecución del respaldo.*

## Pregunta-2
**B.El operador >>, que anexa la nueva línea después del contenido existente.** 
*Debido a que el operador >> agrega la nueva línea al final del archivo de bitácora sin borrar el contenido anterior; el operador > sí lo sobrescribiría por completo.*

## Pregunta-3
**A.Una condicional if con el operador -gt, que compara valores numéricos enteros.** 
*Debido a que el operador -gt realiza comparación numérica de enteros (“mayor que”), mientras que = solo compara cadenas de texto y no sirve para valores numéricos.*

## Pregunta-4
**C. `*/30 * * * *`, que ejecuta el script cada treinta minutos durante todo el día.**
*Debido a que en el campo de minutos */30 significa “cada 30 minutos” (minuto 0 y 30 de cada hora), y los asteriscos restantes cubren todas las horas, días y meses.*

## Pregunta-5
**D.Un bucle while read con IFS igual a coma y el archivo redirigido al bucle.** 
*Debido a que esta construcción lee el CSV línea por línea, usa la coma como separador de campos (IFS=',') y asigna cada campo a una variable; un for sobre cat dividiría incorrectamente por espacios.*

## Pregunta-6
**D.Ambas informaciones juntas son necesarias para resolver el problema.** 
*Debido a que useradd requiere privilegios de superusuario y además falla si el nombre de usuario ya existe; con solo una de las dos condiciones no se garantiza que se creen todas las cuentas del lote.*

## Pregunta-7
**A.Solo la afirmación 1 es verdadera.** 
*Debido a que -mtime +7 selecciona archivos modificados hace más de 7 días (verdadera), mientras que -mtime evalúa la fecha de modificación del contenido, no el último acceso de lectura (ese es -atime, por lo que la afirmación 2 es falsa).*

## Pregunta-8
**C. La afirmación y la razón son verdaderas, y la razón explica la afirmación.**
*Debido a que si la variable de ruta está vacía, `rm -rf "$RUTA/"*` se expande a `rm -rf /*` y borra desde la raíz del sistema; por eso es obligatorio validar previamente con `[ -n "$RUTA" ]` o `${RUTA:?}`.*

## Pregunta-9
**B.systemctl is-active --quiet, cuyo código cero indica ejecución actual del servicio.** 
*Este comando permite comprobar si un servicio está activo. Si devuelve el código 0, significa que está activo; si devuelve otro código, significa que no lo está.*

## Pregunta-10
**D. I, II, IV, III.** 
*Primero se consulta el estado del servicio, después se reinicia si está detenido, luego se comprueba nuevamente y finalmente se registra el resultado con la fecha y hora.*

## Pregunta-11
**A. grep -i error archivo | wc -l, que filtra las líneas y cuenta cuántas resultan.** 
*Debido a que busca la palabra “error” sin distinguir entre mayúsculas y minúsculas, y wc -l cuenta las líneas que coinciden.*

## Pregunta-12
**B. awk con la acción print aplicada a la variable de campo $5.** 
*El comando awk permite seleccionar campos de una línea. $5 indica que se debe mostrar el quinto campo.*

## Pregunta-13
**C. Anteponer sudo y agregar la opción -y para aceptar las confirmaciones.** 
*sudo y -y. sudo permite ejecutar el comando con permisos de administrador y -y acepta automáticamente las confirmaciones de instalación.*

## Pregunta-14
**A. Éxito registrado con && y fallo registrado con ||, ambos tras la instalación.** 
*Al usar && y ||. && ejecuta el siguiente comando si la instalación fue exitosa, mientras que || lo ejecuta si la instalación falla. Así se puede registrar el resultado.*

## Pregunta-15
**B. Un bucle for sobre "${hosts[@]}", que entrega cada elemento por separado.** 
*La estructura recorre cada elemento del arreglo hosts, permitiendo ejecutar una acción para cada dirección almacenada.*

## Pregunta-16
**D. La rama else se ejecuta y el host queda registrado como inaccesible.** 
*La rama else se ejecuta y el host queda registrado como inaccesible. Si el comando ping -c 1 no recibe respuesta, devuelve un código distinto de cero y se ejecuta la parte else, que registra el host como inaccesible.*

## Pregunta-17
**C. `*.jpg|*.png|*.gif` seguido de un paréntesis de cierre y los comandos.**
*En un case, para meter varias extensiones en la misma rama las separas con `|`, así `*.jpg|*.png|*.gif)`. Las comas, el punto y coma o el `&` no sirven para eso.*

## Pregunta-18
**A. Registrar con trap una función de limpieza asociada a la pseudoseñal EXIT.** 
*Trap con una función de limpieza sobre EXIT se ejecuta siempre que el script termina, sea por error o porque lo interrumpieron. SIGKILL y SIGSTOP no se pueden atrapar, y alias o export no sirven para esto.*

## Pregunta-19
**B. Ordenar con ls -t, saltar los N primeros con tail y borrar los restantes.** 
*ls -t ordena por fecha, con lo más nuevo primero. Con tail te saltas las N más recientes y lo que queda es lo viejo, que es justo lo que quieres borrar.*

## Pregunta-20
**C. awk con separador dos puntos y condición sobre el campo 3 igual a cero.** 
*En /etc/passwd los campos van separados por dos puntos y el UID es el tercero. Entonces filtras con separador : y campo 3 igual a 0, que te da las cuentas con poderes de root.*

## Pregunta-21
**D. Sockets TCP y UDP en escucha, con puertos expresados en forma numérica.** 
*ss -tuln te muestra los sockets TCP y UDP que están escuchando, con los puertos en número. La t es TCP, la u UDP, la l listening y la n numérico.*

## Pregunta-22
**A. awk con la variable OFS igual a coma y la asignación $1=$1 que reconstruye la línea.** 
*OFS es el separador de salida de awk, así que lo pones en coma. El $1=$1 fuerza a awk a rearmar la línea con ese separador nuevo.*

## Pregunta-23
**D. systemctl enable --now apache2, que inicia el servicio y lo habilita para cada arranque.** 
*systemctl enable --now apache2 hace las dos cosas de una vez: lo habilita para el arranque y lo inicia ya.*

## Pregunta-24
**A. Comparar $# con el valor 2 y terminar con exit 1 si difiere.** 
*$# te dice cuántos argumentos le pasaron al script. Si no son exactamente 2, sales con exit 1.*

## Pregunta-25
**C. PS3, que almacena el texto con el que select solicita la opción.** 
*PS3 es la variable que guarda el texto que muestra select cuando te pide elegir una opción.*
