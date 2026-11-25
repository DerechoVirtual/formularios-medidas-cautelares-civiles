---
name: indice
description: "Índice de los 84 formularios de Medidas cautelares y diligencias preliminares. Úsala cuando el usuario pida un documento de esta materia y no esté claro qué formulario usar: propone el adecuado y lo abre. Requiere Jurisprudenciator."
---

# Medidas cautelares y diligencias preliminares: índice de formularios

> Plugin `formularios-medidas-cautelares-civiles` · 84 formularios · normativa revisada el 25-11-2026.

## Qué es

Para asegurar el pleito antes o durante el proceso: embargo preventivo, anotación preventiva de demanda, prohibiciones de disponer, administración judicial, diligencias preliminares, aseguramiento y anticipación de prueba, y oposición a las medidas.

## Cómo se usa

Cuéntale a Claude qué documento necesitas y para qué caso. Esta skill busca en la lista de abajo el formulario que mejor encaja (por tipo de documento y por su nombre) y lo abre. Si hay dos o tres que encajan, te los propone para que elijas.

Ejemplos de petición:

- «Solicitud de embargo preventivo antes de la demanda»
- «Diligencias preliminares de exhibición de documentos»
- «Oposición a una medida cautelar acordada sin audiencia»

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

### Cómo elegir

Busca por tipo de documento y por nombre. Cada formulario es una skill de este plugin (`/formularios-medidas-cautelares-civiles:<skill>`). Si dudas entre dos, elige el que mejor encaje con los hechos y dilo; si la petición es ambigua, propón al usuario los dos o tres formularios que mejor encajan y pregúntale cuál quiere. Las reglas del tema están en `marco.md`.

### Cómo usar el formulario elegido

Invoca su skill. Si esa skill no aparece en tu lista de skills disponibles (puede pasar cuando hay muchas skills instaladas), lee directamente su fichero `SKILL.md`: está en la carpeta hermana de esta (`../<skill>/SKILL.md`). Síguelo igual que si la hubieras invocado: el formulario que se rellena está en `../<skill>/assets/formulario.md` y la guía del tema es el `marco.md` de esta carpeta.

### Demandas, peticiones y solicitudes iniciales (3)

| Código | Formulario | Skill |
|---|---|---|
| CIV-1214 | Solicitud de medidas cautelares previas para prohibir una actividad | `solicitud-medidas-cautelares-previas-prohibir-actividad-civ-1214` |
| CIV-1222 | Solicitud de medidas cautelares previas a la demanda en parejas de hecho | `solicitud-medidas-cautelares-previas-demanda-parejas-civ-1222` |
| CIV-2792 | Demanda de reclamación por contrato de agencia con petición de embargo preventivo sin audiencia | `demanda-reclamacion-contrato-agencia-peticion-embargo-civ-2792` |

### Contestaciones, oposiciones y alegaciones (7)

| Código | Formulario | Skill |
|---|---|---|
| CIV-1206 | Escrito de oposición al embargo preventivo con petición subsidiaria de caución sustitutoria | `escrito-oposicion-embargo-preventivo-peticion-civ-1206` |
| CIV-1215 | Oposición a las medidas cautelares acordadas sin audiencia del demandado (embargo preventivo) | `oposicion-medidas-cautelares-acordadas-sin-audiencia-civ-1215` |
| CIV-1218 | Oposición a una medida cautelar solicitada tras la demanda | `oposicion-medida-cautelar-solicitada-tras-demanda-civ-1218` |
| CIV-1219 | Oposición a una medida cautelar con ofrecimiento de caución sustitutoria | `oposicion-medida-cautelar-ofrecimiento-caucion-civ-1219` |
| CIV-1223 | Escrito de oposición a la modificación de una medida cautelar | `escrito-oposicion-modificacion-medida-cautelar-civ-1223` |
| CIV-1242 | Oposición del demandado a la medida cautelar de embargo preventivo | `oposicion-demandado-medida-cautelar-embargo-preventivo-civ-1242` |
| CIV-1252 | Oposición de la persona requerida a las diligencias preliminares | `oposicion-persona-requerida-diligencias-preliminares-civ-1252` |

### Estatutos, actas, certificaciones y escrituras (1)

| Código | Formulario | Skill |
|---|---|---|
| CIV-1205 | Acta de la vista de medidas cautelares con audiencia previa de la parte contraria | `acta-vista-medidas-cautelares-audiencia-previa-parte-civ-1205` |

### Comunicaciones, requerimientos y cartas (31)

| Código | Formulario | Skill |
|---|---|---|
| CIV-1200 | Solicitud de diligencia preliminar de exhibición de cosa mueble | `solicitud-diligencia-preliminar-exhibicion-cosa-mueble-civ-1200` |
| CIV-1203 | Solicitud de embargo preventivo de bienes presentada tras la demanda principal | `solicitud-embargo-preventivo-bienes-presentada-tras-civ-1203` |
| CIV-1207 | Solicitud de asociación de consumidores de medida cautelar de cese de conducta previa a la demanda | `solicitud-asociacion-consumidores-medida-cautelar-cese-civ-1207` |
| CIV-1208 | Solicitud de medida cautelar junto con la demanda principal, modelo general | `solicitud-medida-cautelar-junto-demanda-principal-civ-1208` |
| CIV-1209 | Solicitud de anticipación de prueba en juicio verbal | `solicitud-anticipacion-prueba-juicio-verbal-civ-1209` |
| CIV-1210 | Solicitud oficial de orden de protección de víctimas de violencia doméstica o de género | `solicitud-oficial-orden-proteccion-victimas-violencia-civ-1210` |
| CIV-1211 | Solicitud de embargo preventivo a instancia de parte en un procedimiento arbitral | `solicitud-embargo-preventivo-instancia-parte-civ-1211` |
| CIV-1217 | Solicitud de alzar medidas cautelares tras sentencia absolutoria firme y de indemnización de daños | `solicitud-alzar-medidas-cautelares-tras-sentencia-civ-1217` |
| CIV-1221 | Solicitud de embargo preventivo posterior a la demanda y sin audiencia del demandado | `solicitud-embargo-preventivo-posterior-demanda-sin-civ-1221` |
| CIV-1229 | Solicitud del demandante de mantener los embargos preventivos tras sentencia estimatoria | `solicitud-demandante-mantener-embargos-preventivos-civ-1229` |
| CIV-1230 | Solicitud de diligencias preliminares conforme al artículo 256.1.6 LEC | `solicitud-diligencias-preliminares-conforme-articulo-civ-1230` |
| CIV-1231 | Solicitud del demandado de continuar la obra o asegurarla, ofreciendo caución | `solicitud-demandado-continuar-obra-asegurarla-civ-1231` |
| CIV-1234 | Solicitud de embargo preventivo junto a la demanda, sin audiencia del demandado y con caución | `solicitud-embargo-preventivo-junto-demanda-sin-civ-1234` |
| CIV-1236 | Solicitud de diligencia preliminar de exhibición de cosa en poder del demandado | `solicitud-diligencia-preliminar-exhibicion-cosa-poder-civ-1236` |
| CIV-1237 | Solicitud de prueba pericial anticipada sobre defectos constructivos antes del proceso | `solicitud-prueba-pericial-anticipada-sobre-defectos-civ-1237` |
| CIV-1238 | Solicitud de aseguramiento de prueba para conservar el estado de una cosa mueble | `solicitud-aseguramiento-prueba-conservar-estado-cosa-civ-1238` |
| CIV-1239 | Solicitud de prueba anticipada de testigos antes del inicio del proceso | `solicitud-prueba-anticipada-testigos-antes-inicio-civ-1239` |
| CIV-1240 | Solicitud del demandado de alzar la medida cautelar por cambio de las circunstancias | `solicitud-demandado-alzar-medida-cautelar-cambio-civ-1240` |
| CIV-1243 | Solicitud del demandante de mantener la cautelar tras sentencia absolutoria en primera instancia | `solicitud-demandante-mantener-cautelar-tras-sentencia-civ-1243` |
| CIV-1244 | Solicitud de medida cautelar de prohibición de hacer al demandado, sin audiencia y con caución | `solicitud-medida-cautelar-prohibicion-hacer-demandado-civ-1244` |
| CIV-1246 | Solicitud previa a la demanda de depósito del vehículo en poder del demandado, con caución | `solicitud-previa-demanda-deposito-vehiculo-poder-civ-1246` |
| CIV-1247 | Solicitud de embargo preventivo de buque conforme al Convenio de 10 de mayo de 1952 | `solicitud-embargo-preventivo-buque-conforme-convenio-civ-1247` |
| CIV-1248 | Solicitud de embargo preventivo como medida cautelar previa a la demanda principal | `solicitud-embargo-preventivo-como-medida-cautelar-civ-1248` |
| CIV-1251 | Solicitud de embargo preventivo como medida cautelar en un procedimiento arbitral | `solicitud-embargo-preventivo-como-medida-cautelar-civ-1251` |
| CIV-1254 | Solicitud de diligencia preliminar para determinar los miembros de un grupo de afectados | `solicitud-diligencia-preliminar-determinar-miembros-civ-1254` |
| CIV-1255 | Solicitud de aplicar la caución prestada a los gastos de las diligencias preliminares | `solicitud-aplicar-caucion-prestada-gastos-diligencias-civ-1255` |
| CIV-1256 | Solicitud de depósito de la cosa exhibida u otra medida adecuada para su conservación | `solicitud-deposito-cosa-exhibida-u-otra-medida-civ-1256` |
| CIV-1257 | Solicitud de diligencia preliminar de exhibición del contrato de seguro de responsabilidad civil | `solicitud-diligencia-preliminar-exhibicion-contrato-civ-1257` |
| CIV-1258 | Solicitud de diligencia preliminar de exhibición de documento sucesorio (art. 256.1.3 LEC) | `solicitud-diligencia-preliminar-exhibicion-documento-civ-1258` |
| CIV-2789 | Solicitud de embargo preventivo para asegurar una sentencia extranjera pendiente de exequátur | `solicitud-embargo-preventivo-asegurar-sentencia-civ-2789` |
| CIV-2794 | Solicitud de diligencia preliminar de exhibición de la póliza del otro implicado en el accidente | `solicitud-diligencia-preliminar-exhibicion-poliza-otro-civ-2794` |

### Escritos de trámite y otros (42)

| Código | Formulario | Skill |
|---|---|---|
| CIV-1199 | Escrito del solicitante para que el LAJ requiera la exhibición a la persona obligada | `escrito-solicitante-laj-requiera-exhibicion-persona-civ-1199` |
| CIV-1201 | Escrito del demandado vencedor en primera instancia contra mantener la cautelar en apelación | `escrito-demandado-vencedor-primera-instancia-contra-civ-1201` |
| CIV-1202 | Escrito del demandante vencido en primera instancia para mantener la cautelar en apelación | `escrito-demandante-vencido-primera-instancia-mantener-civ-1202` |
| CIV-1204 | Escrito del demandado parcialmente vencido para alzar la caución sustitutoria del embargo preventivo | `escrito-demandado-parcialmente-vencido-alzar-caucion-civ-1204` |
| CIV-1212 | Otrosí que pide medidas cautelares sin audiencia del demandado | `otrosi-pide-medidas-cautelares-sin-audiencia-demandado-civ-1212` |
| CIV-1213 | Otrosí que pide una medida cautelar junto con la demanda | `otrosi-pide-medida-cautelar-junto-demanda-civ-1213` |
| CIV-1216 | Medidas cautelares previas a un proceso ante tribunal de otro Estado de la Unión Europea | `medidas-cautelares-previas-proceso-ante-tribunal-otro-civ-1216` |
| CIV-1220 | Escrito del demandante pidiendo mantener las medidas cautelares tras sentencia absolutoria no firme | `escrito-demandante-pidiendo-mantener-medidas-civ-1220` |
| CIV-1224 | Otrosí que pide el cese provisional de una actividad con proposición de prueba | `otrosi-pide-cese-provisional-actividad-proposicion-civ-1224` |
| CIV-1225 | Otrosí que pide embargo preventivo sin audiencia de los demandados con proposición de prueba | `otrosi-pide-embargo-preventivo-sin-audiencia-civ-1225` |
| CIV-1226 | Otrosí de medidas cautelares que propone la práctica de prueba | `otrosi-medidas-cautelares-propone-practica-prueba-civ-1226` |
| CIV-1227 | Escrito pidiendo la exhibición de la historia clínica | `escrito-pidiendo-exhibicion-historia-clinica-civ-1227` |
| CIV-1228 | Otrosí que pide la anotación preventiva de la demanda como medida cautelar | `otrosi-pide-anotacion-preventiva-demanda-como-medida-civ-1228` |
| CIV-1232 | Otrosí de demanda que pide intervenir una explotación agraria como cautelar (art. 727.2 LEC) | `otrosi-demanda-pide-intervenir-explotacion-agraria-civ-1232` |
| CIV-1233 | Otrosí de demanda que pide anotación preventiva en acción reivindicatoria, con caución | `otrosi-demanda-pide-anotacion-preventiva-accion-civ-1233` |
| CIV-1235 | Otrosí de la demanda que pide incorporar prueba anticipada | `otrosi-demanda-pide-incorporar-prueba-anticipada-civ-1235` |
| CIV-1241 | Ofrecimiento de caución para sustituir la medida de paralización de actividad | `ofrecimiento-caucion-sustituir-medida-paralizacion-civ-1241` |
| CIV-1245 | Otrosí de la demanda que pide mantener las medidas cautelares decretadas con carácter previo | `otrosi-demanda-pide-mantener-medidas-cautelares-civ-1245` |
| CIV-1249 | Otrosí de la demanda de impugnación de acuerdos comunitarios que pide su suspensión cautelar | `otrosi-demanda-impugnacion-acuerdos-comunitarios-pide-civ-1249` |
| CIV-1250 | Otrosí de la demanda principal que pide anotación preventiva de demanda con audiencia del demandado | `otrosi-demanda-principal-pide-anotacion-preventiva-civ-1250` |
| CIV-1253 | Diligencia preliminar de exhibición de la cosa a que se refiera el juicio (art. 256.1.2 LEC) | `diligencia-preliminar-exhibicion-cosa-refiera-juicio-civ-1253` |
| CIV-1259 | Escrito pidiendo diligencias preliminares por responsabilidad de un accidente de circulación | `escrito-pidiendo-diligencias-preliminares-civ-1259` |
| CIV-1260 | Escrito de quien pidió la exhibición de una cosa solicitando su depósito u otra medida conservativa | `escrito-quien-pidio-exhibicion-cosa-solicitando-civ-1260` |
| CIV-1261 | Escrito pidiendo como diligencia preliminar que el consocio o condueño exhiba documentos y cuentas | `escrito-pidiendo-como-diligencia-preliminar-consocio-civ-1261` |
| CIV-1262 | Escrito pidiendo como diligencia preliminar la exhibición de testamento, codicilo o memoria | `escrito-pidiendo-como-diligencia-preliminar-exhibicion-civ-1262` |
| CIV-1263 | Escrito pidiendo declaración jurada como diligencia preliminar y ofreciendo caución | `escrito-pidiendo-declaracion-jurada-como-diligencia-civ-1263` |
| CIV-1264 | Escrito del perjudicado pidiendo la exhibición del contrato de seguro de responsabilidad civil | `escrito-perjudicado-pidiendo-exhibicion-contrato-civ-1264` |
| CIV-1265 | Escrito del futuro demandante pidiendo medidas de aseguramiento de la prueba antes del proceso | `escrito-futuro-demandante-pidiendo-medidas-civ-1265` |
| CIV-1266 | Escrito de parte pidiendo medidas de aseguramiento de la prueba durante el proceso | `escrito-parte-pidiendo-medidas-aseguramiento-prueba-civ-1266` |
| CIV-1267 | Escrito de parte pidiendo prueba anticipada durante el proceso | `escrito-parte-pidiendo-prueba-anticipada-durante-civ-1267` |
| CIV-1268 | Escrito de parte pidiendo prueba anticipada antes del inicio del proceso | `escrito-parte-pidiendo-prueba-anticipada-antes-inicio-civ-1268` |
| CIV-2782 | Escrito que pide atenuar las medidas cautelares ya acordadas | `escrito-pide-atenuar-medidas-cautelares-ya-acordadas-civ-2782` |
| CIV-2783 | Escrito que pide alzar la medida cautelar porque no se instó la ejecución de la condena firme | `escrito-pide-alzar-medida-cautelar-porque-no-insto-civ-2783` |
| CIV-2784 | Escrito preventivo del posible afectado para que no se adopte una cautelar sin oírle | `escrito-preventivo-posible-afectado-no-adopte-cautelar-civ-2784` |
| CIV-2785 | Escrito que pide agravar las medidas cautelares ya acordadas | `escrito-pide-agravar-medidas-cautelares-ya-acordadas-civ-2785` |
| CIV-2786 | Escrito que pide fijar judicialmente los daños y perjuicios causados por una medida cautelar | `escrito-pide-fijar-judicialmente-danos-perjuicios-civ-2786` |
| CIV-2787 | Escrito que pide alzar la medida cautelar previa porque el proceso principal está suspendido | `escrito-pide-alzar-medida-cautelar-previa-porque-civ-2787` |
| CIV-2788 | Escrito que pide hacer efectiva la medida cautelar concedida tras prestar la caución | `escrito-pide-hacer-efectiva-medida-cautelar-concedida-civ-2788` |
| CIV-2790 | Petición del afectado de dejar sin efecto el embargo preventivo por no prestarse caución en plazo | `peticion-afectado-dejar-sin-efecto-embargo-preventivo-civ-2790` |
| CIV-2791 | Petición del afectado de dejar sin efecto la medida cautelar previa por falta de caución en plazo | `peticion-afectado-dejar-sin-efecto-medida-cautelar-civ-2791` |
| CIV-2793 | Otrosí de la demanda de medidas de apoyo que pide cautelares sobre el patrimonio del afectado | `otrosi-demanda-medidas-apoyo-pide-cautelares-sobre-civ-2793` |
| CIV-2795 | Petición de práctica anticipada de prueba en un proceso ya iniciado | `peticion-practica-anticipada-prueba-proceso-ya-iniciado-civ-2795` |
