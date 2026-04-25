# Rollito Juegos: Fanzine de Software Térmico

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

1. **El Ritual de Subida:** Al abrir el juego, la pantalla pide a los jugadores que "suban al bondi". Cada persona que quiera participar debe dar un toque a la pantalla para sumar su pasaje. A cada pasajero se le asigna automáticamente un **character design** propio (uno de seis rostros kaomoji distintos) que lo identifica durante toda la partida.
2. **Inicio Automático:** Si nadie toca la pantalla durante 1.5 segundos, las puertas del colectivo se cierran automáticamente y arranca la partida.
3. **La Ronda de Pago:** La pantalla adopta la estética de una validadora SUBE, indicando la línea de colectivo, el número de viaje (`VIAJE N`) y el pasajero al que le toca pagar (`PASAJERO X / Y`) junto con su rostro feliz.
4. **El Veredicto (El Toque):** El jugador apoya su "tarjeta" tocando la pantalla. La pantalla se invierte a negro y carga la barra de "LEYENDO TARJETA" durante un par de segundos, impidiendo cualquier otra acción y generando tensión en el grupo. Durante la lectura, el rostro del pasajero adopta su expresión de **duda** rodeado por signos de exclamación que pulsan al ritmo de la barra.
5. **La Economía Oculta:** Cada jugador arranca con un saldo inicial aleatorio completamente invisible (que puede ir de positivo a muy negativo). Al pasar la tarjeta, se calcula un boleto aleatorio que se resta de ese saldo.
6. **Aprobada o Eliminado:**
   - Si el saldo final se mantiene por encima del límite de **-$1200.00**, la máquina arroja **OPERACIÓN APROBADA** (con un destello térmico de colores invertidos) y el rostro vuelve a su expresión **feliz**. El jugador pasa el celular al siguiente pasajero.
   - Si la deuda supera los -$1200.00, la máquina grita **SALDO INSUFICIENTE**, el rostro se transforma en su versión **triste**, y el jugador "se baja del bondi" quedando eliminado.
7. **Transbordo por Eliminación:** Tras una eliminación, el juego ejecuta una animación de puertas cerrándose y abriéndose, realizando un "transbordo" que cambia a los sobrevivientes a otra línea de colectivo (siempre distinta a la actual).
8. **Transbordo por Vuelta Completa:** Si todos los pasajeros logran pagar sin caer, la máquina anuncia **TODOS PAGARON / CAMBIO DE BONDI / TRANSBORDO**: el grupo cumplió un viaje, el contador `VIAJE N` sube, las puertas se cierran y se suben a un nuevo bondi de otra línea.
9. **Victoria:** La ronda continúa, de bondi en bondi, hasta que solo queda un único pasajero en pie: el "ÚLTIMO CON SALDO".

### Logros Técnicos del Volumen 01
- **Animación de Puertas (`Z()`):** Una transición algorítmica de apenas unas líneas de código que dibuja el cierre y apertura de puertas (`▓`) para separar el menú, los transbordos y el fin del juego.
- **Feedback Visual Térmico:** Uso de una expresión regular avanzada para identificar frases críticas (`LEYENDO TARJETA`, `OPERACION APROBADA`, `SALDO INSUFICIENTE`, `APROXIME TARJETA`, `TODOS PAGARON`, `CAMBIO DE BONDI`, `TRANSBORDO`) e invertir su color (blanco sobre negro) en tiempo real sin romper el cálculo estricto de las 40 columnas, emulando el "quemado" de papel inverso en una ticketera.
- **Character Design Multi-Estado:** Cada pasajero recibe uno de seis rostros kaomoji únicos al subir, y cada rostro existe en tres versiones expresivas (feliz, dudando, triste) que se alternan según el estado del juego — convirtiendo a cada teléfono en una pequeña ronda de personajes con identidad visual propia.
- **Cambio de Línea Garantizado:** El sorteo del nuevo bondi durante un transbordo está forzado a no repetir la línea actual, asegurando que cada viaje se sienta como un cambio de escenario y no como un giro vacío.
- **Arte ASCII Adaptativo:** Dos logos diferenciados de la tarjeta SUBE: uno grande y clásico en la pantalla de inicio, y uno técnico con "ondas de lectura" durante el juego. Además, la interfaz del número de colectivo adapta sus espacios automáticamente (`padEnd`) para que la forma del bus nunca se rompa.

---

## Próximos Volúmenes

- **Playtesting de Saldo Insuficiente:** Probar el juego en reuniones reales para ajustar la fórmula matemática de los saldos ocultos iniciales y la duración óptima de las partidas.
- **Volumen 02 (En desarrollo):** Ideación del próximo juego de la antología, explorando conceptos como "Autitos en la Gral. Paz" (enfocado en destreza y evasión infinita) o "Cajera del Fin del Mundo".
- **Diseño de los Cartuchos Físicos:** Diagramación del fanzine térmico impreso final, incluyendo el mini-lore de cada juego, el bloque de código fuente impreso estéticamente, y su respectivo código QR.
