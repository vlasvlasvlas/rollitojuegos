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

1. **El Ritual de Subida:** Al abrir el juego, la pantalla muestra el logo SUBE, el título del volumen y una frase aleatoria del chofer (`AL FONDO ATRAS`, `NO ME APUREN`, `BAJEN POR ATRAS`...). Cada persona que quiera participar debe dar un toque a la pantalla para sumar su pasaje. A cada pasajero se le asigna automáticamente un **character design** propio (uno de seis rostros kaomoji distintos) que lo identifica durante toda la partida.
2. **Inicio Automático:** Si nadie toca la pantalla durante 1.5 segundos, las puertas del colectivo se cierran automáticamente y arranca la partida.
3. **La Ronda de Pago:** La pantalla adopta la estética de una validadora SUBE, indicando la línea de colectivo, el número de viaje (`VIAJE N`), el destino narrativo (`VAN A LA FACU` / `VAN A UN CASAMIENTO EN LA PLATA` / `VAN A EZEIZA`...) y el pasajero al que le toca pagar (`PASAJERO X / Y`) junto con su rostro feliz. **El destino define el rango de costo del boleto:** viajes cortos son baratos (~$200-$400), medios intermedios (~$400-$700) y largos caros (~$700-$1100).
4. **El Veredicto (El Toque):** El jugador apoya su "tarjeta" tocando la pantalla. La pantalla se invierte a negro y carga la barra de "LEYENDO TARJETA" durante un par de segundos, impidiendo cualquier otra acción y generando tensión en el grupo. Durante la lectura, el rostro del pasajero adopta su expresión de **duda** rodeado por signos de exclamación que pulsan al ritmo de la barra, mientras la frecuencia del audio sube progresivamente.
5. **La Economía Oculta:** Cada jugador arranca con un saldo inicial aleatorio completamente invisible (que puede ir de positivo a muy negativo). Al pasar la tarjeta, se calcula un boleto aleatorio que se resta de ese saldo.
6. **Aprobada o Eliminado:**
   - Si el saldo final se mantiene por encima del límite de **-$1200.00**, la máquina arroja **OPERACIÓN APROBADA** (con un destello térmico de colores invertidos) acompañada por un arpegio mayor ascendente y el rostro vuelve a su expresión **feliz**. El jugador pasa el celular al siguiente pasajero.
   - Si la deuda supera los -$1200.00, la máquina grita **SALDO INSUFICIENTE** con un arpegio menor descendente, el rostro se transforma en su versión **triste**, y el jugador "se baja del bondi" quedando eliminado. La pantalla identifica al perdedor con `BAJATE PASAJERO N` para que el grupo sepa exactamente a quién le tocó.
7. **Transbordo por Eliminación:** Tras una eliminación, las puertas del bondi se cierran. **El juego pausa** mostrando el cartel `RECARGANDO SUBE` con un evento callejero aleatorio y queda esperando un toque para abrir el nuevo bondi. Los eventos están clasificados en tres categorías por signo y **modifican el saldo de todos los sobrevivientes** en la misma dirección: positivos (`LES CARGARON DE MAS`, `PROPINAS INESPERADAS`, `SUBE TIRADA EN EL PISO`...) suman entre $200 y $600, negativos (`PERDIERON LA TARJETA`, `MAQUINA SE COMIO LA PLATA`, `KIOSCO DUDOSO`...) restan entre $200 y $600, y neutros (`RECARGA EN EL CHINO`, `RECARGA POR APP`...) generan un drift chico de ±$200. La narrativa del cartel y la economía oculta quedan vinculadas: si el evento es bueno, todos ganan plata; si es malo, todos pierden.
8. **Transbordo por Vuelta Completa:** Si todos los pasajeros logran pagar sin caer, la máquina anuncia **TODOS PAGARON / CAMBIO DE BONDI / TRANSBORDO**: el grupo cumplió un viaje, el contador `VIAJE N` sube, las puertas se cierran, aparece el cartel de recarga callejera con un nuevo destino, y se suben a un bondi distinto al actual.
9. **Victoria:** La ronda continúa, de bondi en bondi, hasta que solo queda un único pasajero en pie. La pantalla `ULTIMO CON SALDO` muestra el número del pasajero ganador, su rostro feliz y su saldo final, todo coronado por un leitmotiv triunfal.

### Logros Técnicos del Volumen 01
- **Animación de Puertas (`Z()`):** Una transición algorítmica de apenas unas líneas de código que dibuja el cierre y apertura de puertas (`▓`) para separar el menú, los transbordos y el fin del juego. La animación incluye una **pausa interactiva** cuando las puertas están totalmente cerradas: el juego espera el toque del usuario para reanudar la apertura, dando tiempo a leer el cartel narrativo del transbordo.
- **Feedback Visual Térmico:** Uso de una expresión regular avanzada para identificar frases críticas (`LEYENDO TARJETA`, `OPERACION APROBADA`, `SALDO INSUFICIENTE`, `APROXIME TARJETA`, `TODOS PAGARON`, `CAMBIO DE BONDI`, `TRANSBORDO`) e invertir su color (blanco sobre negro) en tiempo real sin romper el cálculo estricto de las 40 columnas, emulando el "quemado" de papel inverso en una ticketera.
- **Character Design Multi-Estado:** Cada pasajero recibe uno de seis rostros kaomoji únicos al subir, y cada rostro existe en tres versiones expresivas (feliz, dudando, triste) que se alternan según el estado del juego — convirtiendo a cada teléfono en una pequeña ronda de personajes con identidad visual propia. La pantalla de victoria identifica explícitamente al ganador con su número de pasajero y su rostro feliz.
- **Narrativa Procedural del Transbordo:** Cada cambio de bondi sortea un destino, un costo asociado a la distancia del viaje, un evento de recarga callejera y una frase del chofer. El resultado es que cada partida cuenta una mini-anécdota distinta sin scripts ni lógica de historia, solo combinaciones aleatorias de listas costumbristas del AMBA.
- **Audio Chiptune en WebAudio API (~30 líneas):** Capa sonora vanilla JS con osciladores cuadrados/triangulares/sawtooth que acompaña cada momento del juego: leitmotiv inspirado en el *Himno de Finlandia* de Sibelius al iniciar y en versión triunfal al ganar; tick sutil en cada toque del usuario; pulsos ascendentes durante la lectura de tarjeta; arpegios mayores/menores para aprobado/rechazado; bocinazo sawtooth en cada transbordo. El AudioContext se inicializa lazy en el primer toque para cumplir con las políticas de autoplay de los browsers modernos.
- **Cambio de Línea Garantizado:** El sorteo del nuevo bondi durante un transbordo está forzado a no repetir la línea actual, asegurando que cada viaje se sienta como un cambio de escenario y no como un giro vacío.
- **Economía Atada a la Narrativa:** Los eventos de recarga callejera están clasificados internamente en tres categorías por signo (positivos, neutros, negativos) y modifican el saldo de todos los sobrevivientes en la misma dirección que el evento. Un `LES CARGARON DE MAS` suma plata a todos; un `MAQUINA SE COMIO LA PLATA` se la come a todos. La pantalla de transbordo refuerza el resultado con un emoticón ASCII (`:-)` / `:-(`) para que el grupo perciba inmediatamente si el random le jugó a favor o en contra. La narrativa del fanzine y la mecánica del juego quedan vinculadas, evitando que la partida sea predecible y dándole sabor temático a cada cambio de bondi.
- **Arte ASCII Adaptativo:** Dos logos diferenciados de la tarjeta SUBE: uno grande y clásico en la pantalla de inicio, y uno técnico con "ondas de lectura" durante el juego. Además, la interfaz del número de colectivo adapta sus espacios automáticamente (`padEnd`) para que la forma del bus nunca se rompa.
- **Código en 40 Columnas Estrictas:** Todo el archivo HTML respeta el manifiesto del fanzine: ninguna línea de código supera los 40 caracteres de ancho, garantizando que el código fuente pueda imprimirse perfectamente en una ticketera POS estándar como parte del fanzine físico.

---

## Próximos Volúmenes

- **Playtesting de Saldo Insuficiente:** Probar el juego en reuniones reales para ajustar la fórmula matemática de los saldos ocultos iniciales y la duración óptima de las partidas.
- **Volumen 02 (En desarrollo):** Ideación del próximo juego de la antología, explorando conceptos como "Autitos en la Gral. Paz" (enfocado en destreza y evasión infinita) o "Cajera del Fin del Mundo".
- **Diseño de los Cartuchos Físicos:** Diagramación del fanzine térmico impreso final, incluyendo el mini-lore de cada juego, el bloque de código fuente impreso estéticamente, y su respectivo código QR.

---

## Agradecimientos

- **Dante Bellini** ([@dantemepe](https://github.com/dantemepe)) — por el aporte conceptual y de diseño al fanzine.
