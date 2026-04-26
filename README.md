# Rollito Juegos: Fanzine de Software Térmico

> ## ▶ [JUGAR ONLINE](https://vlasvlasvlas.github.io/rollitojuegos/)
>
> - **Catálogo del fanzine:** https://vlasvlasvlas.github.io/rollitojuegos/
> - **Vol. 01 — Saldo Insuficiente:** https://vlasvlasvlas.github.io/rollitojuegos/saldo_insuficiente.html
>
> Probalo desde el celular, hace falta tocar la pantalla para que arranque (los browsers requieren un toque para activar el audio).

**Rollito Juegos** es una antología colaborativa de minijuegos diseñados bajo las restricciones de una impresora térmica de punto de venta (POS) y la estética clásica de los fanzines. 

Inspirados en las revistas de programación de los años 80, donde el código fuente venía impreso en papel para que el lector lo tipeara y jugara en su casa, esta línea editorial retoma esa tradición pero adaptada a la inmediatez moderna: el juego se imprime en un recibo térmico con su código fuente visible como obra estética, acompañado de un **código QR** que permite escanearlo y jugarlo instantáneamente en cualquier celular.

## Reglas del Formato (Manifiesto de Desarrollo)

Nuestra intención es invitar a diversos creadores y desarrolladores de juegos experimentales (como los creadores de *Manija*, *2bam*, entre otros) a aportar sus propias creaciones a esta antología. Todos los minijuegos que formen parte de **Rollito Juegos** deben cumplir estrictamente estas reglas:

1. **Un Juego = Un Archivo:** El juego completo (lógica, estilos, "gráficos") debe estar contenido de manera autónoma en un único archivo HTML sin ninguna dependencia externa (ni CSS, ni JS sueltos, ni llamadas a librerías, ni imágenes).
2. **Restricción Física (40 Columnas):** Todo el texto, código y gráficos generados están limitados a un máximo absoluto de **40 caracteres de ancho** para asegurar que puedan ser impresos perfectamente en una ticketera POS estándar.
3. **Estética POS:** Blanco y negro estricto. Interfaz puramente tipográfica utilizando arte ASCII/ANSI. Sin imágenes pre-renderizadas.
4. **Interacción Mínima:** Mecánicas extremadamente simples y accesibles, idealmente resolubles con un solo botón o tocando cualquier parte de la pantalla táctil del celular.
5. **Código Legible y Breve:** El archivo HTML debe ser lo suficientemente corto y conciso como para funcionar como un "poema ejecutable" al imprimirse en el fanzine.

---

## Volumen 01: SALDO INSUFICIENTE (`saldo_insuficiente.html`)

**SALDO INSUFICIENTE** es el primer título original que inaugura esta colección. Más que un videojuego tradicional, es un **juego social de azar, ronda y eliminación** que convierte tu celular en una máquina validadora SUBE maldita.

### El Concepto y la Experiencia
El juego utiliza el teléfono móvil como un objeto físico que debe circular de mano en mano entre un grupo de personas (como una ruleta rusa urbana). El objetivo es sobrevivir a los pasajes de colectivo sin que tu saldo oculto cruce el límite negativo permitido por el sistema. Es un juego que genera tensión física y social, disfrazado de un trámite cotidiano del AMBA.

### Mecánica y Jugabilidad

1. **El Lobby del Bondi:** El juego abre con una portada (logo SUBE + nombre del volumen). El primer jugador inicia el lobby manteniendo presionada la pantalla durante 1 segundo (una barra visual de 0 a 100 acompaña el hold para hacer la acción deliberada). En el lobby se ven les pasajeres a bordo con sus caritas kaomoji; cada nuevo hold suma une pasajere al primer slot vacío. Doble toque quita le ultime cargade si me arrepentí. Si nadie suma durante 3.5 segundos, el bondi arranca.
2. **El Briefing de Misión:** Antes de salir, una pantalla anuncia la misión sorteada — `VOLVER A CASA` (vuelta del laburo al barrio), `A LA MARCHA` (cruce hacia el centro y la Plaza de Mayo), o `AL RECITAL` (banda barrial nocturna) — con su intro narrativa, destino final, cantidad de tramos (6), lista de pasajeres y un mini-tutorial explícito sobre el rango de saldo inicial ($1300-$1700) y el piso del saldo (-$1000) bajo el cual te bajan del bondi. Un arpegio mayor C-E-G suena como fanfare de inicio.
3. **El Recorrido:** Cada misión recorre 6 tramos secuenciales con lugares geográficos reales del AMBA (`CENTRO`, `ABASTO`, `ALMAGRO`, `CONGRESO`, `PLAZA DE MAYO`, `AVELLANEDA`, etc.). En cada tramo, todes les pasajeres vives pagan su SUBE en orden. La pantalla de boarding muestra: misión actual, destino final, número de tramo (`‹ TRAMO 3 DE 6 ›`), lugar geográfico, narrativa del momento, pasajere de turno, su carita, y su saldo en bloque invertido (información visible para que el grupo perciba la tensión).
4. **El Minijuego `PEGALE EN LA RANURA`:** El pago de la SUBE es un minijuego de timing: un cursor `▼` se mueve de izquierda a derecha en una ranura con tres zonas — `█` perfect (estrecha), `═` ok (mediana), `·` miss (resto). Una barra de `PACIENCIA CHOFER` se vacía con el tiempo; si se acaba sin tap, miss automático. Tap para clavar el cursor: si pegás perfect, el chofer dice **MM SOS ESTUDIANTE? OK** y cobra 65% del boleto. Zona ok = 95%. Miss = 150%. La dificultad escala por nivel: la zona perfect arranca en 3 chars y se achica, la velocidad del cursor crece 0.2 por nivel.
5. **La Economía Oculta:** Cada pasajere arranca con un saldo aleatorio entre $1300 y $1700. Al pagar, se sortea un boleto del rango del tramo actual y se aplica el multiplicador del minijuego. Si el saldo resultante queda sobre **-$1000**, **OPERACIÓN APROBADA** (arpegio mayor, carita feliz, pasa al siguiente). Si cruza el piso, **SALDO INSUFICIENTE** (arpegio menor, carita triste) y le pasajere "se baja del bondi" en el lugar geográfico exacto: `PASAJERX 3 SE BAJA EN ABASTO`.
6. **Transbordo entre Tramos:** Cuando termina un tramo (todes pagaron o alguien cayó), las puertas se cierran y aparece un cartel `RECARGANDO SUBE` con un evento callejero categorizado. Positivos (`LES CARGARON DE MAS`, `PROPINAS INESPERADAS`, `SUBE TIRADA EN EL PISO`...) suman entre $100 y $300 a todes les sobrevivientes. Negativos (`PERDIERON LA TARJETA`, `MAQUINA SE COMIO LA PLATA`, `KIOSCO DUDOSO`...) restan entre $300 y $700. Neutros (`RECARGA EN EL CHINO`, `RECARGA POR APP`...) generan drift chico de ±$150. El monto exacto se muestra explícito (`+$ 250` o `-$ 400`) acompañado de un emoticón ASCII (`:-)` o `:-(`).
7. **Cierre Narrativo:** Cuando se completan los 6 tramos (o cuando todes mueren antes), el juego termina con uno de cuatro cierres según la supervivencia: **LLEGARON ENTERES** (todes), **LLEGARON N DE TOTAL** (mayoría), **PASAJERX X LLEGÓ SOLE** (une, con carita animada de festejo), o **NADIE VOLVIÓ HOY** (ninguno). La pantalla muestra dos listas: `LLEGARON:` con les sobrevivientes y sus caritas, y `QUEDARON EN EL CAMINO:` con el número de cada pasajere caide y el lugar geográfico donde se quedó. El cierre se corona con un leitmotiv triunfal.

### Logros Técnicos del Volumen 01

- **Onboarding por Gestos Diferenciados:** Toque simple no compromete acciones (resuelve el problema clásico de "tap por curiosidad y aparecen pasajeres fantasma"). Hold sostenido (1 segundo) suma pasajere o avanza pantalla, con barra de progreso visible 0 a 100 que vuelve la espera deliberada y diegética. Doble toque quita le ultime pasajere agregade si hubo error. Lenguaje universal: el mismo gesto vale para touch, mouse y cualquier tecla del teclado.
- **Sistema de Misiones Guionadas:** Tres misiones temáticas (volver del laburo, ir a una marcha, ir a un recital barrial) con seis tramos secuenciales cada una y lugares geográficos reales del AMBA. Cada misión define su intro, destino final, ranges de costo por tramo y cuatro variantes narrativas de cierre según supervivencia. Toda la configuración (misiones, eventos, balance) vive en un `config.yaml` editable como fuente canónica.
- **Briefing Pre-Misión con Tutorial Embebido:** Pantalla intermedia entre lobby y boarding que anuncia la misión sorteada con su intro, destino, lista de pasajeres y reglas explícitas (rango de saldo inicial, dinámica del minijuego, piso del saldo). Resuelve el problema de onboarding sin tutorial intrusivo — el jugador entra a la primera partida con contexto suficiente.
- **Eliminación Geolocalizada con Lista de Caídes:** Cuando alguien cruza el piso del saldo, el cartel dice exactamente dónde se bajó (`PASAJERX 3 SE BAJA EN ABASTO`). Una lista interna trackea cada caída con su lugar; al final de la partida la pantalla de cierre muestra dos columnas: `LLEGARON:` con les sobrevivientes y `QUEDARON EN EL CAMINO:` con quién se quedó dónde. Convierte la pérdida en anécdota memorable.
- **Minijuego "PEGALE EN LA RANURA":** El pago de la SUBE es un mini-juego de timing en lugar de una barra de carga pasiva. Cursor `▼` que rebota en una ranura con tres zonas (perfect/ok/miss), barra de paciencia que se agota, y multiplicadores del boleto según hit (perfect = 0.65x, ok = 0.95x, miss = 1.5x). La dificultad escala por nivel: zona perfect se achica, velocidad del cursor crece. Suma decisión y skill al loop sin romper la simplicidad del manifiesto.
- **Cuatro Cierres Narrativos por Misión:** El final de la partida cambia según cuántes lleguen — TODES enteres (full success), mayoría con N de TOTAL, une SOLE (con carita animada de festejo en cuatro frames), o NINGUNE (failure narrativo). Cada misión define sus textos propios. La carita ganadora baila en loop con brazos arriba `\(^o^)/`, parpadeo y boca abierta.
- **Animación de Puertas (`Z()`):** Transición algorítmica en pocas líneas que dibuja cierre y apertura de puertas (`▓`) para separar tramos, transbordos y fin del juego. Incluye **pausa interactiva** cuando las puertas están totalmente cerradas: el juego espera el toque del usuario para reanudar la apertura, dando tiempo a leer el cartel narrativo del transbordo.
- **Feedback Visual Térmico:** Sistema de marcadores ASCII para jerarquía visual en monospace estricto: `‹ ... ›` se renderiza como bloque negro invertido (texto blanco sobre fondo negro) emulando el quemado de papel térmico, y `« ... »` se renderiza como texto celeste bold para énfasis secundario. La conversión preserva el ancho visual exacto para que el borde ASCII de 40 columnas nunca se descuadre. Una expresión regular adicional captura frases críticas del juego (`OPERACION APROBADA`, `SALDO INSUFICIENTE`, `MM SOS ESTUDIANTE? OK`, `TRANSBORDO`, etc.) y las invierte en tiempo real.
- **Character Design Multi-Estado:** Cada pasajere recibe une de seis rostros kaomoji al subir, en tres versiones expresivas (feliz, dudando, triste) que se alternan según el estado del juego. La pantalla de cierre con une SOLE survivor anima la carita en un ciclo de cuatro frames: rest, brazos arriba con boca abierta, parpadeo, sonrisa con boca abierta. Cada estilo conserva su identidad visual durante el baile (les de anteojos festejan con sus anteojos puestos, etc.).
- **Audio Chiptune en WebAudio API (~30 líneas):** Capa sonora vanilla JS con osciladores cuadrados/triangulares/sawtooth: leitmotiv inspirado en el *Himno de Finlandia* de Sibelius al iniciar el juego y en versión triunfal al ganar; arpegio mayor C-E-G como fanfare al arrancar la misión; tick sutil en cada toque del usuario; barrido de frecuencia durante el minijuego (la nota sube con la posición del cursor); arpegios mayores/menores para perfect/ok/miss; bocinazo sawtooth en cada transbordo. El AudioContext se inicializa lazy en el primer toque y se hace `resume()` defensivo para WebKit/iOS.
- **Economía Atada a la Narrativa:** Los eventos de recarga callejera están clasificados en tres categorías por signo (positivos, neutros, negativos) con rangos de monto disjuntos. Un `LES CARGARON DE MAS` suma entre $100 y $300 a todes; un `MAQUINA SE COMIO LA PLATA` resta entre $400 y $700. Neutros generan drift chico de ±$150. El monto exacto se sortea una sola vez por evento y se aplica uniforme a todes les sobrevivientes (legibilidad sobre realismo). La pantalla de transbordo muestra el monto explícito junto con un `:-)` o `:-(` para que el grupo perciba al instante si el random les jugó a favor o en contra.
- **Cambio de Línea Garantizado:** El sorteo del nuevo bondi durante cada transbordo está forzado a no repetir la línea actual, asegurando que cada tramo se sienta como un cambio de escenario y no como un giro vacío.
- **Configuración Externa via YAML:** Toda la lógica narrativa y numérica (misiones con tramos, eventos con rangos, multiplicadores del minijuego, piso del saldo, duración del hold, frases del chofer, kaomojis) vive en `config.yaml` como fuente canónica editable. El HTML mirrorea los valores manualmente; un build futuro podría inlinearlo automáticamente para preservar el manifiesto de "un juego = un archivo" en la versión imprimible.
- **Código en 40 Columnas Estrictas:** El archivo HTML respeta el manifiesto del fanzine: las líneas de código se mantienen dentro de 40 caracteres de ancho, garantizando que el código fuente pueda imprimirse perfectamente en una ticketera POS estándar como parte del fanzine físico.

---

## Próximos Volúmenes

- **Playtesting de Saldo Insuficiente:** Probar el juego en reuniones reales para ajustar la fórmula matemática de los saldos ocultos iniciales y la duración óptima de las partidas.
- **Volumen 02 (En desarrollo):** Ideación del próximo juego de la antología, explorando conceptos como "Autitos en la Gral. Paz" (enfocado en destreza y evasión infinita) o "Cajera del Fin del Mundo".
- **Diseño de los Cartuchos Físicos:** Diagramación del fanzine térmico impreso final, incluyendo el mini-lore de cada juego, el bloque de código fuente impreso estéticamente, y su respectivo código QR.

---

## Agradecimientos

- **Dante Bellini** ([@dantemepe](https://github.com/dantemepe)) — por el aporte conceptual y de diseño al fanzine.
