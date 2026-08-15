# Evaluacion - Carlos Balbuena

**Proyecto evaluado:** Lab1_ArquiSoftware  
**Contexto:** Piloto UCI Essalud - Lima

## Resumen por persona

| Persona | Rol | Score | Estado | Justificacion breve |
|---|---|---:|---|---|
| Jose Atahualpa | Medico intensivista de turno | 8/10 | PASSED | Los requerimientos cubren continuidad diagnostica, consulta entre turnos, tratamientos, interconsultas y respuesta a emergencias, aunque faltan criterios de acceso en emergencia y consistencia operativa mas verificable. |
| Juan Torres | Enfermero en jefe | 8/10 | PASSED | El set cubre gestion de horarios, disponibilidad del personal, seguimiento de tratamientos y recepcion de alertas, con vacios menores en logistica y reglas de coordinacion fina del personal. |
| Anderson Carcamo | Enfermero | 8/10 | PASSED | Los requerimientos permiten consultar diagnosticos y tratamientos, registrar seguimiento y participar en alertas, aunque las notificaciones relevantes para enfermeria no estan diferenciadas con suficiente detalle operativo. |
| Beatriz Quiroz | Medico especialista | 8/10 | PASSED | Los requerimientos cubren consulta clinica, actualizacion de resultados, aprobacion de informacion oficial e interconsultas, con vacios menores sobre criterios de validacion manual y cierre de casos no urgentes. |
| Mauro Bobadilla | Interno de medicina | 8/10 | PASSED | RF-01 define con precision su perfil de visualizacion supervisada, restricciones y vigencia de anotaciones, aunque faltan flujos mas explicitos sobre tareas prioritarias e indicaciones del turno. |
| PROMEDIO | Global | 8/10 | PASSED | El set de requerimientos cubre de forma sustancial el problema de continuidad asistencial, turnos, alertas y acceso por roles, con brechas de precision y verificabilidad en algunos escenarios criticos. |

## Evaluacion FR

| Requerimiento | Puntaje | Estado | Persona afectada | Evidencia | Juicio |
|---|---:|---|---|---|---|
| RF-01 | 10/10 | PASSED | Mauro Bobadilla; Anderson Carcamo; Juan Torres; Beatriz Quiroz; Jose Atahualpa | Define cargos, perfiles, restricciones por sede, turno y pacientes, vigencia de anotaciones del interno, aprobacion obligatoria y auditoria. | Requerimiento preciso, trazable y directamente alineado con control por roles, supervision y privacidad clinica. |
| RF-02 | 8/10 | PASSED | Juan Torres; Jose Atahualpa | Exige registrar, consultar y modificar horarios y turnos del personal medico y de enfermeria. | Cubre el problema central de coordinacion de turnos, pero no define reglas para evitar cruces, faltas de cobertura o conflictos de reasignacion. |
| RF-03 | 8/10 | PASSED | Jose Atahualpa; Beatriz Quiroz | Exige registrar y actualizar diagnosticos por personal medico autorizado. | Cubre la necesidad clinica base, aunque no explicita validaciones, estructura minima ni criterios de versionado diagnostico. |
| RF-04 | 8/10 | PASSED | Anderson Carcamo; Beatriz Quiroz; Jose Atahualpa | Permite consultar diagnosticos registrados de un paciente por personal autorizado. | Bien alineado con consulta clinica rapida, pero sin precisar filtros, contexto temporal o acceso en escenarios de alta carga. |
| RF-05 | 10/10 | PASSED | Jose Atahualpa; Anderson Carcamo | Permite al turno siguiente consultar diagnosticos y planes de tratamiento de turnos anteriores. | Cubre de forma directa la continuidad asistencial, problema critico del piloto y necesidad principal del intensivista y enfermeria. |
| RF-06 | 8/10 | PASSED | Anderson Carcamo; Beatriz Quiroz | Permite registrar resultados de pruebas y mediciones realizadas a los pacientes. | Cubre la captura de resultados, pero aislado resulta menos preciso que RF-11 y no define autorizacion, origen ni tiempos de disponibilidad. |
| RF-07 | 8/10 | PASSED | Juan Torres; Anderson Carcamo; Jose Atahualpa | Permite registrar, consultar y actualizar planes de tratamiento de los pacientes. | Resuelve una necesidad central del flujo UCI, aunque requiere mayor detalle sobre aprobaciones, vigencia y trazabilidad clinica del plan. |
| RF-08 | 8/10 | PASSED | Jose Atahualpa; Juan Torres; Anderson Carcamo | Permite generar alertas ante situaciones de emergencia relacionadas con los pacientes. | Alineado con respuesta critica, pero el criterio de disparo y clasificacion de alertas queda incompleto sin mas condiciones operativas. |
| RF-09 | 10/10 | PASSED | Jose Atahualpa; Juan Torres; Anderson Carcamo; Mauro Bobadilla | Define jerarquia de escalamiento, tiempos de notificacion y confirmacion, disponibilidad, reintento y alerta masiva final. | Requerimiento exhaustivo y verificable para emergencias, con fuerte alineacion al problema de respuesta inmediata y coordinacion del personal. |
| RF-10 | 10/10 | PASSED | Beatriz Quiroz; Jose Atahualpa | Define solicitud de interconsulta, asignacion automatica por especialidad y disponibilidad, prioridad, tiempos y cierre visible en historia clinica. | Requerimiento robusto, operacional y bien conectado con continuidad clinica y trabajo entre especialistas. |
| RF-11 | 10/10 | PASSED | Beatriz Quiroz; Jose Atahualpa; Anderson Carcamo | Define integracion en tiempo real, tiempos maximos, cola de respaldo, validacion de identidad del paciente y manejo de resultados errados, incompletos, inconsistentes o duplicados. | Cobertura exhaustiva para disponibilidad oportuna de resultados y seguridad de asociacion clinica. |
| RF-12 | 8/10 | PASSED | Juan Torres; Jose Atahualpa | Permite consultar la disponibilidad del personal durante un turno determinado. | Util para coordinacion y emergencias, pero no define estados de disponibilidad ni relacion explicita con reasignaciones o cobertura. |

## Evaluacion NFR

| Requerimiento | Puntaje | Estado | Persona afectada | Evidencia | Juicio |
|---|---:|---|---|---|---|
| RNF-01 | 8/10 | PASSED | Todos | Exige pantalla principal en menos de 2 segundos tras login exitoso en escritorio y moviles institucionales, con 200 usuarios concurrentes por sede. | Medible y alineado con operacion UCI, aunque limitado a condiciones normales y sin criterio para degradacion en picos o contingencias. |
| RNF-02 | 10/10 | PASSED | Jose Atahualpa; Beatriz Quiroz; Anderson Carcamo | Exige ficha clinica completa en menos de 2 segundos para usuario autorizado. | Altamente alineado con consulta rapida de informacion clinica y continuidad entre turnos; es claro, medible y operativo. |
| RNF-03 | 5/10 | FAILED | Todos | Exige disponibilidad minima del 99.9%. | El objetivo es relevante, pero queda incompleto sin periodo de medicion, exclusiones, cobertura por sede o impacto en ventanas de mantenimiento. |
| RNF-04 | 8/10 | PASSED | Todos | Exige recuperacion de caida o interrupcion del servicio en menos de 5 minutos. | Relevante para continuidad asistencial y medible, aunque falta distinguir recuperacion parcial, total y preservacion de sesiones o colas criticas. |
| RNF-05 | 8/10 | PASSED | Todos | Define escalamiento desde Lima a expansion nacional con volumen de usuarios y registros, manteniendo los demas NFR y la gestion sin cruces ni perdida de continuidad. | Cubre de forma sustancial la escalabilidad operativa del piloto, aunque el salto a 100,000 usuarios en 6 meses exige supuestos de capacidad no explicitados. |
| RNF-06 | 5/10 | FAILED | Jose Atahualpa; Beatriz Quiroz; Anderson Carcamo | Exige que la informacion clinica registrada y sincronizada pueda consultarse de forma consistente por usuarios autorizados. | Necesario para continuidad de diagnosticos, pero demasiado abstracto: no define consistencia, latencia, conflictos, prioridad de escritura ni resolucion de divergencias. |
| RNF-07 | 8/10 | PASSED | Mauro Bobadilla; Todos | Exige restringir acceso a informacion de pacientes segun rol y permisos asignados. | Bien alineado con privacidad y acceso minimo necesario, aunque RF-01 aporta mas precision que este NFR por si solo. |
| RNF-08 | 10/10 | PASSED | Jose Atahualpa; Beatriz Quiroz; Anderson Carcamo | Define tiempos de visibilidad para actualizaciones aprobadas y emergencias, respaldo sin perdida y demora maxima bajo sobresaturacion. | Requerimiento claro, critico y verificable para continuidad clinica y disponibilidad oportuna de informacion en cambios de turno y emergencias. |
| RNF-09 | 5/10 | FAILED | Todos | Exige mecanismos de respaldo y recuperacion para preservar la informacion ante fallos. | Critico para UCI, pero insuficiente por falta de RPO, frecuencia, alcance, pruebas de restauracion y prioridades de datos clinicos. |

## Resultado global

| Metrica | Valor |
|---|---|
| Evaluador | Carlos Balbuena |
| Puntaje global | 8/10 |
| Estado global | PASSED |
| Diagnostico | El set de requerimientos es sustancialmente util, coherente y alineado con el problema del piloto UCI, especialmente en continuidad de diagnosticos, control por roles, emergencias e integracion de resultados, aunque mantiene brechas relevantes de precision en disponibilidad, consistencia y respaldo. |
| Riesgos criticos | Ambiguedad operacional en consistencia clinica sincronizada; respaldo y recuperacion sin RPO ni alcance verificable; gestion de turnos sin reglas explicitas de resolucion de cruces y cobertura. |
