---
name: otrosi-demanda-medidas-apoyo-pide-cautelares-sobre-civ-2793
description: "Otrosí de la demanda de medidas de apoyo que pide cautelares sobre el patrimonio del afectado. Lo redacta con los datos del caso y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Otrosí de la demanda de medidas de apoyo que pide cautelares sobre el patrimonio del afectado

> Formulario **CIV-2793** del plugin **Medidas cautelares y diligencias preliminares** (`formularios-medidas-cautelares-civiles`) · Civil › Medidas cautelares y diligencias preliminares · normativa revisada el 25-11-2026.

## Qué es

Otrosí digo en demanda de adopción de medidas judiciales de apoyo a personas con discapacidad, por el que se solicita, como medida cautelar simultánea a la presentación de la demanda, el nombramiento de un administrador para el patrimonio del presunto discapacitado, mientras se tramita el procedimiento.

Es un modelo de tipo **escritos de trámite y otros**, en su versión revisada y actualizada a la normativa vigente.

## Para qué sirve

Para obtener, en pocos minutos, un borrador completo de «Otrosí de la demanda de medidas de apoyo que pide cautelares sobre el patrimonio del afectado» adaptado a tu caso y a la normativa vigente, en Word y listo para revisar. Claude no se limita a copiar el modelo: te pide los datos, decide contigo las opciones, redacta las partes que dependen de los hechos y comprueba en el BOE cada norma que cita.

## Cómo se usa

1. **Pídelo con tus palabras**, por ejemplo: «Prepárame el documento “Otrosí de la demanda de medidas de apoyo que pide cautelares sobre el patrimonio del afectado” para mi caso». También puedes invocarla directamente con `/formularios-medidas-cautelares-civiles:otrosi-demanda-medidas-apoyo-pide-cautelares-sobre-civ-2793`.
2. **Dale los datos del caso** cuando te los pida (abajo tienes la lista para tenerlos a mano). Lo que no sepas queda como hueco visible.
3. **Resuelve las opciones** que te plantee (las marcadas [ELEGIR] y [OPCIONAL] en el modelo).
4. **Recibe el documento en Word, tal cual es el formulario**: empieza por su primera línea (por ejemplo «En [LOCALIDAD], a [FECHA]» o «A LA SECCIÓN…»), sin títulos ni notas añadidas, en Times New Roman 11, interlineado 1,15 y texto justificado. Lo pendiente, las normas comprobadas y el plazo te los dice en el chat.

Si no estás seguro de que este sea el formulario que necesitas, usa el índice del plugin: `/formularios-medidas-cautelares-civiles:indice`.

## Qué contiene esta skill

- `SKILL.md` (este fichero): qué es el formulario, para qué sirve, cómo se usa, los datos que pide, las normas que cita, los avisos de actualización y las instrucciones para Claude.
- `assets/formulario.md`: el formulario seco, tal cual, desde su primera línea hasta la firma, con sus campos [EN MAYÚSCULAS] y sus opciones [ELEGIR…] / [OPCIONAL…]. Es el texto que se rellena; no lleva explicaciones.
- `../indice/marco.md` (en la skill `indice` del plugin): la guía del tema (Medidas cautelares y diligencias preliminares) con las normas, órganos y plazos vigentes que Claude lee antes de redactar.

## Datos que conviene tener a mano

- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] CALLE
- [ ] FECHA
- [ ] LUGAR
- [ ] NÚMERO

## Normas que cita el formulario

- No cita artículos concretos; Claude localizará las normas aplicables con Jurisprudenciator si el documento las necesita.

## Instrucciones para Claude

### Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

### Avisos de actualización (1) — se aplican en el texto, nunca se copian en el documento

- Al principio del formulario: El proceso contencioso de medidas de apoyo presupone un expediente previo de jurisdicción voluntaria con oposición o sin resolver (art. 756.1 LEC); no exige MASC (art. 5.2.c LO 1/2025). Conoce la Sección de Familia, Infancia y Capacidad donde exista (art. 86.5.g LOPJ).

### Notas de uso del formulario — orientan la redacción, nunca se copian en el documento

Notas al pie del formulario original:
(1) Sin perjuicio de que en el curso del proceso principal se determine con plenitud de garantías procesales si, en efecto, la persona demandada precisa medidas de apoyo y con qué alcance, se autoriza al Juez a dispensar una rápida e interina defensa de las esferas jurídicas patrimonial y extrapatrimonial de la persona con discapacidad, análogamente a como hicieran los arts. 203 y 209 C.C. Y al igual que éstos, la norma de la LEC 1/2000 tampoco concreta cuáles sean las «medidas» que pueden acordarse.

Conviene la doctrina en que las facultades del Juez revisten una extraordinaria vastedad, justificada a fortiori por el amplísimo margen de discrecionalidad con el que puede determinar el alcance de las medidas de apoyo. Basta con que satisfagan la exigencia de proporcionar una «adecuada protección» de la persona y bienes del sujeto concernido, en atención a las circunstancias concurrentes (FERNÁNDEZ-BALLESTEROS, RIFA y VALLS; REVERTE NAVARRO). Entre las patrimoniales se insinúan: el depósito de bienes muebles o la indisponibilidad de cuentas corrientes o valores mobiliarios (O"CALLAGHAN); controles sobre la gestión desarrollada por el guardador de hecho (hoy, art. 265 C.C.) (REVERTE NAVARRO); anotaciones registrales. En el ámbito personal se han sugerido, entre otras: reconocimientos facultativos; el internamiento en un centro asistencial; la observación ambulatoria de su salud mental (ROCA GUILLAMÓN); nombramiento interino de defensor judicial o curador (DÍEZ-PICAZO; FERNÁNDEZ-BALLESTEROS, RIFA y VALLS; REVERTE NAVARRO).

Como quiera que la sentencia que recae en esta clase de procesos tiene naturaleza constitutiva y, por lo mismo, es únicamente susceptible de ejecución «impropia», estas actuaciones sólo pueden ser homogéneas o semejantes, en mayor o menor proporción, a las derivaciones complementarias de la provisión de medidas de apoyo.

En cuanto a los requisitos de la actividad, la adopción de estas medidas puede producirse: a) ex officio, en cualquier momento, aún antes de promoverse el proceso, tan pronto el Juez competente tenga noticia, por cualquier medio, de la existencia de una persona en una situación de discapacidad que requiera medidas de apoyo, en cuyo caso pondrá además el hecho en conocimiento del Ministerio Fiscal para que inicie, si lo estima procedente, un expediente de jurisdicción voluntaria (art. 762.1). Sin embargo, se le impide iniciar de oficio el proceso, actuación con la que se ampararía inmediatamente el interés público. Obsérvese que, en rigor, su imparcialidad no puede verse comprometida ya que otros sujetos adoptan la posición de parte, y la intervención del Ministerio Fiscal es suficiente garantía de incluso cabría advertir que la adopción de medidas comporta un «prejuicio» mayor; b) a instancia de parte, una vez promovido el proceso de provisión de medidas de apoyo a las personas con discapacidad, también en cualquier instante del mismo.

El apdo. 3 subviene a la omisión de los arts. 203 y 209 C.C. a propósito del procedimiento para la adopción de las medidas, estableciendo, siempre que la urgencia de la situación no lo impida, la audiencia previa de la persona con discapacidad y la aplicación directa de los arts. 734 a 736 LEC 1/2000.


### Flujo

1. **Paso 0**: comprueba Jurisprudenciator (arriba).
2. Lee entero `assets/formulario.md` (el formulario que vas a rellenar, en la carpeta de esta skill) y la parte de `../indice/marco.md` que afecte al caso. Limítate a la materia de este formulario: no añadas contenido ajeno a él.
3. Pide los datos de la lista en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez. Lo que el usuario no sepa se queda como hueco visible con su etiqueta (p. ej. [FECHA]).
4. Resuelve cada [ELEGIR …] y cada [OPCIONAL …] según los hechos, y sustituye cualquier indicación entre paréntesis del formulario («(se describirá…)», «(indicar…)») por el contenido que corresponda. Redacta las partes que dependen del caso (hechos, motivos, descripción de bienes).
5. Aplica los avisos de actualización en el lugar que indican. Comprueba con `buscar_articulo` cada norma citada; si alguna ha cambiado, usa la redacción vigente. Si citas jurisprudencia, localízala con `buscar_sentencias` o `buscar_por_cita` y léela con `leer_sentencias`.
6. Antes de entregarlo, pasa `verificar_escrito` con las frases que citan normas o sentencias y corrige lo que señale.
7. **Documento final = el formulario tal cual, rellenado y limpio.**
   - Empieza exactamente por la primera línea de `assets/formulario.md` y sigue su estructura y su orden hasta la firma.
   - No pongas en el documento título, nombre del formulario o de la skill, código, encabezados, «Para qué sirve», leyendas, avisos, notas de uso, comentarios ni explicaciones. Tampoco marcas [ELEGIR…] u [OPCIONAL…]: ya están resueltas.
   - Formato Word (.docx, con la skill de Word disponible): **Times New Roman 11 pt** en todo el documento, **interlineado 1,15**, **texto justificado**, márgenes de 2,5 cm. Los rótulos del formulario (REUNIDOS, CLÁUSULAS, HECHOS, SUPLICO…) en su propia línea y en negrita, sin cambiar su texto.
8. En el chat (nunca dentro del documento): datos pendientes, partes redactadas por ti, normas y sentencias comprobadas con Jurisprudenciator (y, si algún dato sale de internet, cuál y su enlace) y, si es un escrito judicial o administrativo, el plazo y el órgano ante el que se presenta.

El resultado es un borrador para que lo revise un profesional antes de usarlo.
