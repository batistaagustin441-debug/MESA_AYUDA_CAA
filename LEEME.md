# Mesa de Ayuda — CAA Corp · Port nativo a Godot 4.7.2 (fases 1 a 4 · juego completo)

Reescritura del juego HTML/three.js en **GDScript nativo**, con escenas y materiales de Godot (sin HTML dentro), y con un salto de calidad visual: materiales PBR, iluminación global y post-proceso.

## Abrir y jugar

1. Abre Godot 4.7.2 → **Import** → elige `project.godot`.
2. La primera vez Godot importa las texturas (unos segundos).
3. **F5** para jugar.

Requiere una GPU con **Vulkan** (renderer Forward+). Para exportar: *Project → Export → Add… → Windows Desktop / Linux*.

## Controles (los mismos del original)

| Tecla | Acción |
|---|---|
| Clic | Mirar con el mouse (Esc lo libera) |
| WASD / flechas | Mover · ← → giran |
| Shift | Correr |
| Rueda | Zoom |
| E | Interactuar (sentarse en la PC, atender en sitio, consola Cisco, ascensor, casa, hablar) |
| F | Usar lo que llevas en la mano (beber, comer, entregar documentos) |
| Q | Soltar el objeto |
| X | Confrontar a un espía sorprendido en el acto |
| V | Primera / tercera persona |
| M | Mapa «Ir a…» (caminas solo hasta un lugar o persona) |
| Tab | Menú lateral (misiones, logros, ajustes) |
| P | Pausa |
| Enter | Chat de la sala (multijugador) |
| Esc | Cerrar pantalla / soltar el mouse |

**Al volante del superdeportivo:** W/S acelerar y frenar (S en parado = reversa) · A/D girar · Espacio freno de mano (derrape) · Shift turbo · C cambia la cámara (persecución, cercana, cabina) · H bocina · R reubicar en el carril · E estacionar y bajarte.
| F11 | Pantalla completa |

## Qué incluye la fase 1

- **Mundo completo** con las mismas coordenadas, medidas y colisiones del original: oficina de TI, 6 departamentos del piso 1, pasillo con ascensor, apartamento (sala, cocina, comedor, dormitorio), data center con 6 racks Cisco y LEDs, y piso 2 (taller, almacén, Soporte N2, Marketing, Legal, Capacitación).
- **Tickets**: los 24 casos originales con el mismo texto y las mismas puntuaciones, selección diaria de 8, prioridades, SLA, visitas en sitio (Marta, Luis, Carlos, copiadora), usuarios que **te buscan** caminando hasta ti, estrellas y feedback.
- **Jornada** por turnos (el reloj avanza con cada acción, como en el original), fin de día con el mismo cálculo de sueldo, XP, rangos, logros, gastos de vida y valoración media; volver a casa (estudiar, cocinar, TV, dormir) y día siguiente.
- **Consola Cisco IOS** completa: modos user/priv/config/vlan/interface, abreviaturas, `?`, historial ↑↓, `enable secret`, `show vlan|ip interface|interfaces|running-config|version`, `write memory`, `copy`, `erase`, `reload`, rangos de interfaces, SVI con IP, y los 3 trabajos diarios.
- **NPC** sentados en sus puestos con el mismo generador de personajes cartoon (peinados, gafas, barba, corbata, gafete), saludos, consejos y aviso de ⚠ cuando tienen un ticket pendiente.
- HUD, minimapa, pantallas dinámicas (monitores, TV con anuncios animados, reloj de pared), sonido sintetizado como el WebAudio original y guardado en `user://itg1.json`.

## Mejoras visuales

- 12 sets de texturas PBR tileables (albedo + normal + roughness a 1024 px): baldosa cerámica, parqué, madera, moqueta, hormigón pulido, yeso, tela, metal cepillado, plástico, techo acústico, alfombra y rejilla de rack. Mapeo triplanar en espacio mundo (nada se estira).
- Iluminación global SDFGI, SSAO, SSIL, reflejos SSR, niebla volumétrica, glow, tonemapping AgX, MSAA 4×, luces reales en cada lámpara y luz cálida entrando por las ventanas, con sombras suaves.
- Tinte de atardecer según la hora del juego (los mismos colores del original).
- Props con más detalle: marcos de puerta, zócalos, plantas con follaje, teclados, tazas, libros, frutero, hornillas, rejillas de rack, etc.

## Fase 2 (incluida)

- **Escritorio real** en tu PC y en las de los usuarios: ventanas que se arrastran, redimensionan, minimizan y maximizan (doble clic en el título), barra de tareas, menú inicio con buscador, notificaciones con contador y menú contextual para cambiar el fondo.
- **Zoho Desk con todas sus pestañas**: Habilidades (9 ramas con puntos), Eventos (encuentra y bloquea la IP de la fuerza bruta), Active Directory (desbloquear, restablecer, deshabilitar ex empleados), Correo (phishing o legítimo), Monitor de red (3 caídas por jornada con su acción correcta), Tablet MFA (código que cambia cada 15 s), Empleos, Tienda y BIOS (en sitio: Secure Boot, TPM y SSD primero).
- **Apps**: Navegador con buscador, YouTube simulado con 10 videos animados y su música (las capacitaciones dan XP), guías, foro, noticias, clima y wiki (requiere VPN en PCs remotas); CAA Connect; Símbolo del sistema (ping, nslookup, ipconfig /flushdns, tasklist, taskkill, net start spooler, gpupdate, cleanmgr…); Administrador de tareas; Chat del equipo; Notas (se guardan); Calculadora; Este equipo; Snake.
- **Escritorio remoto** (desde CAA Connect) o **en persona** en el puesto de cada usuario («Usar la PC de…»): su correo con carpetas, Descargas (borra el malware), VPN, scripts remotos según los síntomas detectados y «Resolver ticket».
- Las alertas del monitor y el ataque sin investigar afectan el fin de jornada igual que en el original.

## Fase 3 (incluida)

- **Lobby y avatar**: nombre, ropa, piel, pelo, gorra y estilo; vista inicial (1.ª o 3.ª persona).
- **Llamadas entrantes** con diálogo y respuestas que suman o restan XP y satisfacción.
- **Taller (piso 2)**: banco de reparación con PC animada, herramientas de diagnóstico (inspección visual, POST, multímetro, memtest…), almacén de piezas con precios y órdenes de reparación del día.
- **Oficina viva**: 17 compañeros con horarios propios que llegan, trabajan, conversan, van al café o a reuniones y se marchan, navegando con A*; personal en el piso 2 y sala de juegos.
- **Café, agua, nevera e impresora** con objetos en la mano (límite diario de bienestar).
- **Espías y sala de CCTV**: vigila las cámaras y confronta (X) a quien robe información.
- **SOC del infiltrado**: alertas con plazos, evidencias en AD/EQ/SW/NAS/CCTV, imagen forense con CRC32, consultas SQL al SIEM, controles NIST/ISO 27001, reunión de emergencia, acusación y análisis post-incidente.
- **5 niveles de misiones** con certificado final exportable a PNG.
- **Pausa y ajustes** (volumen, sensibilidad, calidad, sombras, minimapa, FPS) y **música procedural** que se intensifica con las alertas.

## Fase 4 (incluida): Ciudad de Panamá, superdeportivo, bancos y multijugador

**Ciudad con referencias reales.** Sales por la puerta «SALIDA» del pasillo del piso 1 (o al terminar la jornada) a la **Av. Balboa**, con la orientación verdadera: mirando al mar, **Punta Paitilla** queda a la izquierda (este) y el **Casco Antiguo** con el **Cerro Ancón** a la derecha (oeste). Se maneja por la derecha.
- Avenida de 6 carriles con isleta central sembrada de palmas, carril exclusivo **«SOLO BUS»** pintado en la vía, líneas blancas segmentadas, doble línea amarilla junto a la isleta, pasos peatonales tipo cebra, líneas de pare, flechas, vialetas reflectivas, tapas de alcantarilla, manchas y grietas (calcomanías reales en el asfalto).
- Intersecciones semaforizadas con la **Calle 29 Este**, la **Av. Federico Boyd** y la **Calle Uruguay** (retornos por la isleta), señales **PARE** octogonales, rótulos azules de calle, pórticos verdes con destinos (Punta Paitilla · Corredor Sur · Vía España / Casco Antiguo · Cinta Costera 3 · Av. de los Poetas) y límite de velocidad.
- **Cinta Costera**: acera, parque con palmas y guayacanes en flor, estacionamientos, ciclovía roja, paseo de trote, plaza frente al mar, malecón con baranda de acero, escollera de rocas y el **Monumento a Vasco Núñez de Balboa**. Mercado de Mariscos al oeste.
- Rascacielos de Bella Vista con fachadas procedurales (muro cortina, balcones, franjas) y ventanas que se encienden al atardecer; península de **Paitilla / Punta Pacífica** con la torre vela y la torre retorcida; **Casco Antiguo** con catedral y el viaducto marino de la Cinta Costera 3; **Cerro Ancón** con la gran bandera; **Puente de las Américas** a lo lejos y barcos fondeados esperando su turno para el Canal.
- Tráfico con seguimiento y semáforos, **MiBus** (Albrook ⇄ Paitilla) que se detiene en sus paradas, un **diablo rojo**, taxis amarillos, placas «PANAMÁ», peatones y ciclistas.
- Cielo físico (dispersión de Rayleigh/Mie), sol que sigue la hora del juego (sale por Paitilla, se pone tras el Casco), perspectiva aérea, sombras en cascada, SSR sobre los charcos y el mar.

**Superdeportivo** (diseño propio en cuña, sin logotipos): carrocería lofteada con pintura metalizada con barniz, fibra de carbono, rines de aluminio, discos y pinzas, faros LED, luces traseras, escape cuádruple, alerón e interior. Física arcade con 7 marchas, derrape con freno de mano, choques, balanceo y cabeceo, motor V10 sintetizado, chirrido de llantas, bocina, tres cámaras y HUD con velocidad, marcha, RPM y distancia a cada destino.

**Bancos** (Banco del Istmo y Banca Canal Pacífico): sucursales completas con ventanillas, atención al cliente, cajeros automáticos, bóveda, tablero de turnos, Departamento de TI y SOC con video wall. Clientes que hacen fila, guardia que patrulla y **9 misiones** (Atención al Cliente, TI y SOC) con área de trabajo y bono del 20 %.

**Tu casa** es el punto de guardado; al terminar la jornada los compañeros salen a sus autos, manejas a casa y duermes.

**Multijugador nativo (ENet):** en el lobby, «Crear sala» muestra un código de 7 letras (y la IP); tus compañeros eligen «Unirme» y lo escriben. Hasta 4 técnicos en la misma red (puerto UDP 24575). Se ven los avatares, quién maneja y el chat (Enter). Para jugar por Internet, el anfitrión debe abrir ese puerto en su router.

## Requisitos de los Sprints 2 y 3 (agregados)

- **Enemigo con FSM** (`scripts/enemy_intruder.gd`, escena `scenes/intruso.tscn`): un falso «técnico de mantenimiento» patrulla el Piso 1 desde las 10:00 y te persigue si te ve (radio, cono de visión y línea de visión). Estados: PATRULLA → PERSECUCION → BUSQUEDA → PATRULLA, HUIDA y FUERA. Todos los valores se ajustan en el Inspector de `intruso.tscn`. Si te alcanza te clona la credencial (−12 de seguridad); escapa corriendo o confróntalo con **X**.
- **Vida, derrota y victoria**: la seguridad es la vida del técnico. En 0 aparece **GAME OVER** (Reintentar / Menú). Al llegar a casa tras la jornada aparece **¡Jornada completada!** (Descansar / Menú).
- **Menú principal** con Jugar, Créditos y Salir (pie fijo, navegable con teclado) y pantalla de **créditos** con roles y licencias.
- **Audio en buses**: Master, Music y SFX (`default_bus_layout.tres`), cada uno con su slider en la pausa.
- Valores del jugador expuestos en el Inspector de `scenes/main.tscn` (velocidad, correr, FOV, giro con flechas).
- Pruebas automáticas: `godot --headless --path . -- test=1` (110 comprobaciones).

## Estructura

```
scenes/main.tscn          escena principal (todo se construye en código)
scripts/data.gd           datos fijos (tickets, rangos, logros, puntos de interacción)
scripts/game.gd           reglas y estado (autoload «Game»)
scripts/cisco.gd          emulador Cisco IOS
scripts/world.gd          construcción del edificio
scripts/mats.gd           materiales PBR
scripts/rig.gd            personajes
scripts/canvas_tex.gd     texturas dinámicas (pantallas, TV, reloj)
scripts/main.gd           bucle principal, jugador, interacción, objetos, vistas
scripts/ui/               HUD, PC, consola, fin de jornada, minimapa
scripts/ui/desktop.gd     gestor de ventanas tipo Windows
scripts/ui/apps.gd        navegador, CMD, tareas, correo, etc.
scripts/ui/zoho_tabs.gd   pestañas de Zoho Desk
scripts/ui/remote_ui.gd   escritorio remoto
scripts/soc.gd            SOC / infiltrado (autoload «Soc»)
scripts/office_life.gd    NPC, rutas A*, espías
scripts/audio/music.gd    música y efectos procedurales
scripts/ui/call_ui.gd     llamadas · bench_ui.gd taller · cctv_ui.gd cámaras
scripts/ui/soc_ui.gd      interfaz del SOC · menu_ui.gd pausa/menú · cert_ui.gd certificado
scripts/ui/lobby_ui.gd    lobby, editor de avatar y salas multijugador
scripts/city/city.gd      Ciudad de Panamá (Av. Balboa, Cinta Costera, skyline, tráfico, peatones)
scripts/city/cars.gd      superdeportivo, autos, MiBus y diablo rojo procedurales
scripts/city/drive.gd     manejo, cámara, motor y HUD de velocidad
scripts/city/bank.gd      interior de los bancos · scripts/ui/bank_ui.gd misiones
scripts/city/city_data.gd trazado, destinos y misiones
scripts/net.gd            multijugador ENet (autoload «Net») · scripts/ui/chat_ui.gd chat
shaders/                  asfalto con demarcación vial, mar y fachadas
assets/textures/city/     texturas PBR y señales (tools/gen_city_textures.py)
assets/textures/          texturas PBR generadas
assets/fonts/             Space Grotesk y JetBrains Mono (OFL)
```

## Ampliación de la ciudad (zona oeste) y lancha

- **Mercado de Mariscos** (oeste de CAA Corp por la Av. Balboa): nave, puestos de comida, ceviche ($4), muelle con pangas y pelícanos, y la **lancha**.
- **Ramal norte** (frente al Mercado): calle hacia la **Plaza 5 de Mayo** (obelisco, fuente, kiosco y raspao) y el barrio de **Curundú** (multifamiliares, cancha y el Infocentro).
- **Cinta Costera 3**: viaducto sobre el mar con ciclovía; al fondo el **Casco Antiguo** (casas coloniales y la catedral).
- **Calzada de Amador**: palmeras, ciclovía, museo de colores y las islas **Naos, Perico y Flamenco** con sus marinas. En el horizonte, el Puente de las Américas y la isla Taboga.
- **Lancha** (muelle del Mercado): `1` router a Isla Naos · `2` servidor a Isla Flamenco · `3` rescate de un pescador · `4` carrera de 10 boyas con récord. `R` vuelve al muelle, `E` te bajas en el muelle.
- **Misiones comunitarias** (una vez por día): Infocentro de Curundú (red sin DHCP), kiosco de la Plaza 5 de Mayo (smishing) y el datáfono del Mercado (red abierta).
- **Peatones con ruta**: más de 60 personas caminan solas, se detienen y siguen (vendedores, trotadores, ciclistas, niños en la cancha).
- **Rendimiento**: la ciudad se construye en segundo plano mientras estás en la oficina; los objetos lejanos se dejan de dibujar según su tamaño; el fundido espera a que la escena esté lista.
- Viaje rápido (`M` en la ciudad) a todas las zonas nuevas.

## Versión web

`GODOT=/ruta/a/godot tools/build_web.sh` genera en `build/entrega_web/` el zip para itch.io, el HTML único y la versión para hosting. Para la web reduce las texturas a la mitad, quita sombras de lámparas, usa menos autos y reproduce todo el audio como bucles pregrabados (sin cortes).
