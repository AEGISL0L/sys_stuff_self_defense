Los daimons son divinidades o espíritus menores, a menudo personificaciones de conceptos abstractos, seres de la misma naturaleza que los mortales y las deidades, similares a fantasmas, héroes ctónicos, guías espirituales, fuerzas de la naturaleza o las mismas deidades (ver el Simposio de Platón). Según el mito de Hesíodo, "grandes y poderosas figuras debían ser honradas después de la muerte como un daimon..." Un daimon no es tanto un tipo de ser casi divino, según Burkert, sino más bien un "modo peculiar" no personificado de su activida.


En la Teogonía de Hesíodo, Faetón se convierte en un daimon incorpóreo o un espíritu divino, pero, por ejemplo, los males liberados por Pandora son deidades mortales, keres, no daimones. También desde Hesíodo, la gente de la Edad de Oro fue transformada en daimones por voluntad de Zeus, para servir benevolentemente a los mortales como sus espíritus guardianes; "seres buenos que dispensan riquezas... [sin embargo], permanecen invisibles, conocidos sólo por sus actos". Los daimones de los héroes venerados se localizaban mediante la construcción de santuarios, para que no deambularan inquietos, y se creía que conferían protección y buena fortuna a quienes les ofrecían sus respetos.

Una tradición del pensamiento griego, que encontró acuerdo en la mente de Platón, era la de un daimon que existía dentro de una persona desde su nacimiento, y que cada individuo era obtenido por un daimon singular antes de su nacimiento por medio de sorteo.

En el Antiguo Testamento, los espíritus malignos aparecen en el libro de Jueces y en Reyes. En la Septuaginta, hecha para los judíos de habla griega de Alejandría, el griego ángelos (ἄγγελος, "mensajero") traduce la palabra hebrea mal'ak, mientras que daimónion (δαιμόνιον; pl. daimónia (δαιμόνια)), que lleva el significado de un espíritu natural que es menos que divino (ver sobrenatural), traduce la palabra hebrea shedim así como la palabra se'irim en algunos versos y palabras para ídolos (deidades extranjeras), y describe el ser Asmodeus en el Libro de Tobías. El uso de daimōnen el texto griego original del Nuevo Testamento hizo que la palabra griega se aplicara al concepto judeocristiano de un espíritu maligno a principios del siglo II d.C.


Mitología Griega:

    En la mitología griega, un "daemon" o "daimon" era un ser sobrenatural, a menudo benevolente, que podía actuar como un espíritu guía o un ente que realizaba ciertas tareas sin ser visto. No necesariamente eran malignos; más bien eran intermedios entre los dioses y los humanos, desempeñando funciones siniestras o benéficas dependiendo del contexto.

Adaptación a la Informática:

    El término fue introducido en el ámbito de la informática por los desarrolladores del sistema operativo Unix a finales de la década de 1960 y principios de la de 1970. Los desarrolladores querían un nombre que simbolizara un proceso que trabajara constantemente en el fondo, realizando tareas automáticamente, sin intervención humana directa. Un daemon es algo que, como el daimon mitológico, está siempre presente, pero sin que se note su acción.

Hoy en día, los daemons son componentes esenciales de la arquitectura de casi todos los sistemas operativos modernos. Estos programas permiten que muchas de las funcionalidades del sistema operativo estén automatizadas y gestionadas sin intervención del usuario. Su papel es especialmente relevante en sistemas multitarea como Linux, Unix y también en Windows (aunque en este último se suelen denominar "servicios").
Tipos de Daemons Comunes

En los sistemas Linux/Unix, los daemons se encuentran en varias categorías, cada uno especializado en algún tipo de tarea:

    Red y Comunicación:
        sshd: Es un daemon de seguridad que maneja las conexiones SSH, permitiendo la comunicación remota de manera segura.
        httpd y nginx: Estos daemons son los motores detrás de los servidores web, que sirven las páginas web a los navegadores de los usuarios.

    Tareas Programadas:
        cron: Se encarga de ejecutar scripts o comandos a horarios predefinidos. Es muy útil para realizar tareas de mantenimiento como respaldos, limpieza de archivos temporales, etc.

    Manejo de Hardware:
        udevd: Gestiona los eventos del hardware en Linux. Cada vez que se conecta un dispositivo (como una memoria USB), udevd se asegura de que sea reconocido y manejado adecuadamente.
        cupsd: Gestiona las impresoras conectadas al sistema y hace posible la impresión.

    Seguridad y Supervisión:
        firewalld: Gestiona y aplica reglas del firewall.
        auditd: Es el daemon del sistema de auditoría de seguridad que registra eventos importantes para seguridad y cumplimiento normativo.

    Administración del Sistema:
        systemd: En muchas distribuciones modernas de Linux, systemd es tanto el proceso de inicio como el sistema de gestión de daemons. Reemplazó a init en muchas distribuciones gracias a sus capacidades avanzadas, como la paralelización de procesos durante el arranque.

Cómo Funcionan los Daemons

Los daemons generalmente se inician durante el arranque del sistema y continúan ejecutándose hasta que el sistema se apaga. Sus características distintivas incluyen:

    Ejecución en Segundo Plano:
        Un daemon no tiene una interfaz visual, por lo que no interactúa directamente con el usuario. Se ejecuta "detrás de escena" y escucha solicitudes o eventos que debe manejar.

    Sin Dependencia de la Terminal:
        A diferencia de otros procesos, un daemon se desacopla de la terminal desde la que fue ejecutado, para que no se cierre si la terminal se cierra.

    Respuesta a Eventos:
        Algunos daemons, como inetd (el "super-servidor" de Unix), responden a eventos externos. inetd puede escuchar múltiples puertos y ejecutar el servicio apropiado cuando recibe una solicitud.

Creación de Daemons en Programación

Cuando los desarrolladores quieren crear un daemon, hay ciertas técnicas que deben implementar:

    Desacoplamiento de la Terminal:
        El proceso se "desacopla" de la terminal en la que se inició mediante una llamada al sistema como fork(), creando un proceso hijo que hereda la ejecución y continúa en segundo plano.

    Redirección de Salida Estándar:
        Un daemon redirige generalmente la entrada estándar (stdin), la salida estándar (stdout) y los errores estándar (stderr) a /dev/null, para evitar cualquier dependencia de la entrada/salida de la terminal.

    Establecer un Nuevo ID de Sesión:
        El daemon establece un nuevo ID de sesión con la llamada setsid(), que le asigna una nueva sesión independiente, garantizando que el daemon no esté asociado con un terminal específico.
