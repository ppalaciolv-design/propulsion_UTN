# PROMPTS.md — Trazabilidad del uso de IA
## TP1: Diseño y Optimización de Ciclos Termodinámicos
**Materia:** Propulsión — Ingeniería Aeronáutica, UTN FRH  
**Cátedra:** Ing. Aer. Ariel Jorge Gagliardi / Ing. Rodrigo Bracco  
**Grupo 4** | Año: 2025

---

> Este archivo documenta el uso de Claude (Anthropic) como herramienta de asistencia durante el desarrollo del TP1, conforme a los requisitos de trazabilidad establecidos en el enunciado. Se registra cada interacción significativa con: fecha, etapa, prompt utilizado, respuesta obtenida, y decisiones tomadas sobre el material generado.

---

## ETAPA 1 — Fundamentos e Investigación

---

### [E1-01] Sección 1.1 — Introducción teórica: ciclos Otto, Diesel y Sabathé

**Fecha:** 29/04/2025  
**Etapa:** 1.1 — Introducción teórica

**Prompt (paráfrasis):**
> Redactar la sección 1.1 del informe con un repaso teórico de los ciclos Otto, Diesel y Sabathé. Incluir hipótesis del modelo base, procesos de cada ciclo, ecuaciones de estados termodinámicos, expresión de rendimiento, PME y temperatura máxima. Apoyarse en el material de la cátedra. Mantenerlo breve.

**Respuesta obtenida:**
Se generó el borrador completo de la sección 1.1 con las hipótesis del ciclo de aire frío estándar, tablas de procesos para los tres ciclos, ecuaciones de estados termodinámicos, expresiones de η_th y PME. Las expresiones directamente presentes en los apuntes de Gagliardi fueron identificadas como tales; las derivadas por Claude fueron marcadas con ⚠️ *derivación estándar*.

**Decisiones:**
- ✅ Aceptado: estructura general, hipótesis del modelo, ecuaciones de Otto y Diesel (coinciden con apuntes).
- ✅ Aceptado: advertencia explícita sobre qué sale de los apuntes y qué es derivación estándar.
- ✏️ Modificado: se corrigió la expresión de q_in en el Paso 0 del cálculo manual (ver E1-05); el denominador correcto es (1 + AFR) y no solo AFR.
- ❌ Rechazado: expresión cerrada de η_th,Sabathé incluida sin verificación contra fuente primaria — se mantiene marcada como inferida hasta validar con bibliografía.

**Justificación:** El material de la cátedra no presenta la expresión cerrada del rendimiento del ciclo Sabathé. Se acepta la derivación estándar como referencia pero se explicita su condición de inferencia para no presentarla como respaldada por los apuntes.

---

### [E1-02] Sección 1.2 — Introducción al motor Lycoming O-235

**Fecha:** 29/04/2025  
**Etapa:** 1.2 — Motor aeronáutico de referencia

**Prompt (paráfrasis):**
> Escribir unos párrafos de introducción al motor Lycoming O-235: qué es, cómo se denomina la nomenclatura, qué tipo de ciclo usa, qué combustible, en qué aeronaves se instala. Indicar fuentes primarias recomendadas.

**Respuesta obtenida:**
Se generaron tres párrafos introductorios describiendo la configuración del motor, el origen de la denominación "O-235", el vínculo con el ciclo Otto y el AVGAS 100LL, y la asociación con el Cessna 152. Claude indicó explícitamente qué datos son de conocimiento general del sector y cuáles requieren verificación contra el TCDS FAA y el manual Lycoming.

**Decisiones:**
- ✅ Aceptado: párrafos introductorios con el hilo argumental que conecta combustible → relación de compresión → eficiencia térmica.
- ✏️ Modificado: variante de motor ajustada a L2C tras verificación en el Operator's Manual oficial (ver E1-03).
- ✅ Aceptado: advertencias de fuente primaria requerida (TCDS FAA E-217).

**Justificación:** Los datos de denominación y configuración general son verificables y coinciden con el manual. La conexión conceptual con la sección 1.1 es deliberada para fortalecer el argumento de diseño de cara a la defensa oral.

---

### [E1-03] Sección 1.2.1 — Caracterización del motor O-235-L2C

**Fecha:** 29/04/2025  
**Etapa:** 1.2.1 — Caracterización del motor

**Prompt (paráfrasis):**
> Con el Operator's Manual del Lycoming O-235 subido como fuente primaria, redactar la tabla de caracterización del motor: cilindros, cilindrada, bore, stroke, relación de compresión, potencia máxima, RPM, consumo, peso, refrigeración. Citar sección del manual para cada dato.

**Respuesta obtenida:**
Se generó la tabla de caracterización completa extrayendo datos directamente del manual (Secciones 1, 2 y 3). Se calculó la cilindrada unitaria (233,3/4 = 58,3 in³) y el BSFC (inferido de consumo en Gal/hr y densidad AVGAS), ambos marcados como cálculos derivados no explícitos en el manual.

**Decisiones:**
- ✅ Aceptado: todos los datos extraídos directamente del manual con referencia de sección.
- ✅ Aceptado: cilindrada unitaria como cálculo derivado marcado.
- ✏️ Modificado: se aclaró que la potencia rated del O-235-L2C es 118 HP (serie K, L, M) y no 115 HP como figura en fuentes secundarias — el manual lo distingue explícitamente de la variante K2C.
- ⚠️ Pendiente: BSFC calculado con densidad estándar AVGAS (6,0 lb/US gal) — citar con precaución hasta confirmar densidad exacta de la partida de combustible.

**Justificación:** El manual es fuente primaria FAA-aprobada. Cualquier dato que no figure explícito se marcó como derivado para mantener trazabilidad en la defensa oral.

---

### [E1-04] Sección 1.3 — Condiciones atmosféricas ISA a 5.000 ft

**Fecha:** 29/04/2025  
**Etapa:** 1.3 — Condiciones atmosféricas

**Prompt (paráfrasis):**
> Calcular y redactar las condiciones ISA a 5.000 ft para la misión. Incluir T, p, ρ, velocidad del sonido y relación de densidad σ. Justificar la elección de altitud con datos del manual del motor.

**Respuesta obtenida:**
Se calcularon las condiciones ISA con las relaciones estándar de la troposfera (ICAO Doc. 7488-CD): T = 278,24 K, p = 84,31 kPa, ρ = 1,056 kg/m³, σ = 0,862. Se vinculó con la tabla de potencia a altitud del manual (Sección 8) que indica 84,6% de la potencia SL a 5.000 ft, resultando en ≈100 HP — validando el punto de diseño limpio de la misión.

**Decisiones:**
- ✅ Aceptado: cálculos ISA completos con formulación estándar ICAO.
- ✅ Aceptado: justificación del punto de diseño a plena mariposa ≈ 100 HP.
- ✅ Aceptado: tabla resumen de condiciones.
- ℹ️ Nota: se evaluó cambiar la altitud a 2.000 ft (argumento avión escuela) pero se mantuvo 5.000 ft por coherencia con el enunciado y la limpieza del punto de diseño.

**Justificación:** 5.000 ft es la altitud del enunciado y produce un punto de diseño termodinámicamente limpio: plena mariposa = potencia de misión. Cambiar a 2.000 ft hubiera requerido justificar operación a mariposa parcial (~91%), añadiendo complejidad sin beneficio para el modelo base.

---

### [E1-05] Cálculo manual — Ciclo Otto base de la misión

**Fecha:** 29/04/2025  
**Etapa:** Cálculo manual de referencia (previo a Etapa 3)

**Prompt (paráfrasis):**
> Resolver completamente el ciclo Otto base de la misión: calcular q_in desde la estequiometría del isoctano con λ=1,10, luego todos los estados termodinámicos (T, p, v) en los cuatro puntos del ciclo, η_th, q_sal, w_neto y PME. Incluir verificación contra datos reales del O-235-L2C.

**Respuesta obtenida:**
Se desarrolló el cálculo paso a paso con explicación física de cada ecuación. Se obtuvo: q_in = 2.521 kJ/kg, T_max = 4.169 K, η_th = 57,5%, w_neto = 1.450 kJ/kg, PME_ideal = 1.735 kPa. Se calculó la PME real del motor (835 kPa) y se obtuvo un factor de conversión ideal→real de 0,48. Se generó también el diagrama p-v con todos los estados y calores marcados.

**Decisiones:**
- ✅ Aceptado: estequiometría completa con explicación de cada término (origen del AFR, del 0,233, del PCI, distinción PCI/PCS).
- ✏️ Corregido durante la sesión: denominador de q_in era AFR en la primera versión → corregido a (1+AFR) tras detectar el error conceptual. La corrección reduce q_in de ~2.680 a 2.521 kJ/kg y T_max de ~4.391 K a 4.169 K.
- ✅ Aceptado: verificación PME real vs ideal y factor 0,48 como referencia cuantitativa de las irreversibilidades.
- ✅ Aceptado: diagrama p-v generado como archivo HTML descargable.
- ⚠️ Nota: T_max de 4.169 K es un valor del ciclo ideal con hipótesis de aire frío estándar — en la realidad las temperaturas máximas rondan los 2.500 K. Esta diferencia se documenta explícitamente en el informe.

**Justificación:** El cálculo manual es el resultado de referencia contra el cual se validará la aplicación en la Etapa 4. La corrección del denominador de q_in fue detectada por razonamiento dimensional durante la misma sesión y corregida antes de usar el valor en cualquier cálculo posterior.

---

---

## ETAPA 2 — Diseño de la aplicación

---

### [E2-01] Especificación funcional — decisiones de diseño

**Fecha:** 29/04/2025  
**Etapa:** 2.1 a 2.4 — Especificación funcional completa

**Prompt (paráfrasis):**
> Redactar la especificación funcional de la aplicación respondiendo: qué entradas tendrá, qué salidas producirá, cómo se organizan las pantallas, qué controles interactivos tendrá el usuario y cómo se estructurará el código. Incluir tabla de entradas/salidas, lista de requisitos funcionales y diagrama de módulos.

**Decisiones previas al desarrollo (tomadas por el grupo):**
- El usuario elige el ciclo a analizar (no comparación simultánea).
- Geometría mixta: número de cilindros y relación s/D son entradas; bore, carrera y cilindrada son salidas calculadas.
- Stack: HTML + JavaScript puro, sin dependencias externas, una sola página.

**Respuesta obtenida:**
Se generó la especificación completa con 8 requisitos funcionales (RF-01 a RF-08), tabla de 13 entradas y 20 salidas con unidades y observaciones, descripción de la organización en tres columnas (panel de entradas, diagrama p-v, resultados), y diagrama de módulos con 5 funciones puras independientes de la interfaz.

**Decisiones:**
- ✅ Aceptado: estructura de requisitos funcionales RF-01 a RF-08.
- ✅ Aceptado: principio de separación entre funciones de cálculo puro e interfaz (facilita validación en Etapa 4).
- ✅ Aceptado: wireframe digital generado como archivo HTML independiente.
- ✏️ Modificado: se agregó RF-07 (validación contra O-235-L2C) que no estaba en el enunciado pero enriquece el análisis de la Etapa 5.

**Justificación:** La separación entre lógica de cálculo e interfaz es un requisito implícito del enunciado cuando pide "módulos de cálculo separados de la interfaz". El wireframe digital es equivalente al boceto a mano alzada que pide el enunciado, con mayor claridad visual.

---

### [E2-02] Wireframe digital de la interfaz

**Fecha:** 29/04/2025  
**Etapa:** 2.4 — Pantallas, interfaz y controles

**Prompt (paráfrasis):**
> Generar un wireframe digital de la interfaz de la aplicación en HTML, mostrando el layout de tres columnas, los controles de cada panel, el diagrama p-v central y el panel de resultados con los valores del cálculo manual de referencia.

**Respuesta obtenida:**
Archivo HTML estático (`wireframe_app.html`) que representa fielmente el diseño de la interfaz con todos los controles, agrupaciones, campos deshabilitados condicionalmente (r_c y r_p para ciclo Otto) y panel de resultados con valores de referencia del cálculo manual.

**Decisiones:**
- ✅ Aceptado: layout de tres columnas coincide con la especificación funcional.
- ✅ Aceptado: comportamiento condicional de campos mostrado visualmente.
- ✅ Aceptado: panel de validación con semáforo verde/amarillo/rojo.

**Justificación:** El wireframe cumple el requisito del enunciado de incluir "wireframes a mano alzada o digitales". La versión digital permite verificar la organización visual antes de programar la interfaz real.

---

## ETAPA 3 — Desarrollo de la aplicación

---

### [E3-01] Módulo de cálculo termodinámico — implementación y validación

**Fecha:** 29/04/2025  
**Etapa:** 3 — Paso 1: núcleo de cálculo sin interfaz

**Prompt (paráfrasis):**
> Implementar el módulo de cálculo termodinámico como funciones puras en JavaScript, siguiendo la especificación de la Etapa 2. Incluir calcularISA(), calcularCombustion(), calcularOtto(), calcularDiesel(), calcularSabathe() y calcularGeometria(). Agregar una suite de tests que valide cada función contra los valores del cálculo manual de referencia, con tolerancia ±0,5%.

**Respuesta obtenida:**
Archivo `modulo_calculo.html` con las 6 funciones puras implementadas y 17 tests automáticos. Al ejecutarse en el navegador muestra PASS/FAIL por cada test con el valor calculado, el valor de referencia y el porcentaje de diferencia.

**Decisiones:**
- ✅ Aceptado: todas las funciones implementadas como funciones puras sin acceso al DOM.
- ✅ Aceptado: 17/17 tests pasaron con tolerancia ±0,5%.
- ✅ Aceptado: comentarios en el código citan la fuente de cada ecuación (apuntes cátedra o derivación estándar).
- ✏️ Nota registrada: las pequeñas diferencias entre los tests y el cálculo manual (< 0,3%) se deben a que el código no redondea pasos intermedios, lo que lo hace más preciso que el cálculo manual.

**Justificación:** El enunciado establece explícitamente validar el módulo de cálculo contra el cálculo manual antes de construir la interfaz. Los 17 tests en verde son la evidencia formal de esa validación.

---

### [E3-02] Aplicación completa — interfaz sobre módulo validado

**Fecha:** 29/04/2025  
**Etapa:** 3 — Paso 2: interfaz completa

**Prompt (paráfrasis):**
> Construir la aplicación completa en un único archivo HTML siguiendo el wireframe de la Etapa 2 y usando las funciones puras del módulo validado. Incluir: panel de entradas con sliders y selects, diagrama p-v dinámico en SVG que se actualiza en tiempo real, panel de resultados con estados termodinámicos, KPIs y geometría calculada, panel de validación contra el O-235-L2C, y toggle entre escala lineal y logarítmica.

**Respuesta obtenida:**
Archivo `app_predimensionamiento.html` con la aplicación completa y funcional. Desplegada en GitHub Pages en: `https://ppalaciolv-design.github.io/propulsion_UTN/app_predimensionamiento.html`

**Decisiones:**
- ✅ Aceptado: layout de tres columnas coincide con el wireframe de la Etapa 2.
- ✅ Aceptado: diagrama p-v generado con curvas isoentrópicas calculadas punto a punto (60 puntos por curva).
- ✅ Aceptado: campos r_c y r_p se habilitan/deshabilitan automáticamente según ciclo seleccionado.
- ✅ Aceptado: toggle escala lineal/logarítmica en el diagrama p-v.
- ✅ Validado: con valores de la misión (5.000 ft, rv=8,5, λ=1,10, isoctano) la app produce η_th = 57,5%, PME = 1.739 kPa, T_max = 4.176 K — diferencia < 0,2% respecto al cálculo manual, atribuible a mayor precisión numérica del código.

**Justificación:** La pequeña diferencia entre los resultados de la app y el cálculo manual (0,17% en T_max, 0,23% en PME) es esperable y deseable: el código no redondea pasos intermedios mientras que el cálculo manual trabajó con 2-3 decimales en cada paso. La app es más precisa que el cálculo manual.

---

### [E3-03] Modificación de la app — análisis de casos límite

**Fecha:** 29/04/2025  
**Etapa:** 3 — Extensión para análisis paramétrico

**Prompt (paráfrasis):**
> Modificar la aplicación para permitir el análisis de casos límite. Primero: ampliar el slider de r_v para que llegue a 1 como mínimo. Segundo: ampliar el slider de λ hasta 10 para ver q_in → 0. Luego, al verificar que λ=10 no es suficiente para el caso límite, agregar en cambio una casilla tildable "Caso extremo λ = 1.000" que fuerce ese valor y deshabilite el slider, manteniendo el rango operativo normal en el slider.

**Respuesta obtenida:**
Se realizaron las modificaciones en dos pasos. Primero se amplió rv a mínimo 1 y λ a máximo 10, luego se revirtió λ a su rango operativo (0,7–1,4) y se agregó el checkbox que fuerza λ = 1.000, deshabilita el slider y muestra "1.000 ⚠️" en la etiqueta.

**Observaciones registradas durante el análisis:**

*Caso límite r_v = 1:* con relación de compresión unitaria el ciclo degenera completamente — el diagrama p-v muestra q_in = q_sal y w_neto = 0. Verificación directa de la fórmula: η_th = 1 − 1/1^(κ−1) = 0. Sin compresión no hay diferencia de temperatura entre los focos y el ciclo no puede producir trabajo. Caso límite validado físicamente.

*Caso límite λ = 1.000:* q_in → 2,6 kJ/kg ≈ 0. El ciclo se reduce a una compresión isoentrópica seguida de una expansión isoentrópica idéntica en sentido inverso — el diagrama p-v colapsa a una línea de área cero. Interpretación física: sin aporte de calor no hay conversión energética posible. El pistón comprime y expande sin producir trabajo neto, lo que constituye una demostración directa del Segundo Principio: un ciclo termodinámico requiere operar entre dos fuentes de temperatura distinta para generar trabajo útil.

**Decisiones:**
- ✅ Aceptado: checkbox de caso extremo con λ = 1.000 y deshabilitación del slider.
- ✅ Aceptado: rango operativo del slider λ revertido a 0,7–1,4.
- ✅ Aceptado: rango de r_v ampliado a mínimo 1 (permanente).
- ✅ Aceptado: interpretación física de ambos casos límite documentada para defensa oral.

**Justificación:** El análisis de casos límite es parte de la Etapa 5 (análisis y optimización). Tener la herramienta interactiva permite verificar el comportamiento del modelo en sus extremos y validar que las ecuaciones implementadas son físicamente consistentes.

---

*Documento generado con asistencia de Claude (Anthropic) — Modelo: claude-sonnet-4-6*  
*Última actualización: 29/04/2025*
