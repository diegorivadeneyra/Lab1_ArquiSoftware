# Evaluacion - Carlos Balbuena

**Proyecto evaluado:** Lab1_ArquiSoftware  
**Contexto:** Piloto UCI Essalud - Lima

## Resumen por persona

| Persona | Rol | Score | Estado | Justificacion breve |
|---|---|---:|---|---|
| Jose Atahualpa | Medico intensivista de turno | 8/10 | PASSED | Los FR cubren continuidad entre turnos, diagnosticos, tratamientos, emergencias y disponibilidad del personal; los vacios principales estan en precision de oportunidad y escalabilidad. |
| Juan Torres | Enfermero en jefe | 8/10 | PASSED | Los requerimientos cubren turnos, disponibilidad, tratamiento y alertas, alineados con el problema central de cobertura y coordinacion, aunque faltan criterios operativos para evitar cruces y escalar el piloto. |
| Anderson Carcamo | Enfermero | 5/10 | FAILED | El set cubre consulta de diagnosticos, planes y registro clinico, pero define de forma debil la rapidez de notificaciones y no detalla suficiente soporte para indicaciones operativas del flujo asistencial. |
| Beatriz Quiroz | Medico especialista | 8/10 | PASSED | La especificacion cubre consulta y actualizacion de resultados, diagnosticos y datos clinicos con buena alineacion a su trabajo, aunque sin criterios finos de integracion ni tiempos verificables por flujo. |
| Mauro Bobadilla | Interno de medicina | 3/10 | FAILED | Existe control general por roles y notificaciones, pero el alcance permitido para el interno no esta especificado con precision y su necesidad de recibir indicaciones claras queda solo indirectamente cubierta. |
| PROMEDIO | Global | 5/10 | FAILED | El set cubre el problema operativo principal de UCI de forma funcional, pero presenta vacios importantes de trazabilidad, medibilidad y precision en escalabilidad, oportunidad y permisos por perfil. |

## Evaluacion FR

| Requerimiento | Puntaje | Estado | Persona afectada | Evidencia | Juicio |
|---|---:|---|---|---|---|
| RF-01 | 5/10 | FAILED | Mauro Bobadilla | `ReqFunc.md` define "un rol por cada gerarquia de los usuarios" y `Personas/MauroBobadilla.md` exige acceso unicamente a informacion necesaria. | Cubre control base por jerarquia, pero la redaccion es ambigua, no define permisos concretos ni trazabilidad por persona critica. |
| RF-02 | 8/10 | PASSED | Juan Torres | `ReqFunc.md` exige registrar, consultar y modificar horarios y turnos del personal medico y de enfermeria; `Personas/JuanTorres.md` necesita gestionar horarios y disponibilidad. | Alineado con el problema central de cruces y cobertura de turnos, con vacio menor en reglas operativas de conflicto. |
| RF-03 | 8/10 | PASSED | Jose Atahualpa | `ReqFunc.md` exige registrar y actualizar diagnosticos por personal medico autorizado; `Personas/JoseAtahualpa.md` requiere registrar nuevos diagnosticos. | Bien alineado con continuidad clinica y rotacion de medicos, aunque sin criterios de completitud del diagnostico. |
| RF-04 | 8/10 | PASSED | Anderson Carcamo | `ReqFunc.md` permite consultar diagnosticos registrados; `Personas/AndersonCarcamo.md` necesita consultar diagnosticos e indicaciones medicas. | Cubre consulta clinica base para enfermeria y especialistas, aunque no detalla filtros, contexto ni rapidez de acceso. |
| RF-05 | 10/10 | PASSED | Jose Atahualpa | `ReqFunc.md` permite al turno siguiente consultar diagnosticos y planes de tratamiento de turnos anteriores; `Personas/JoseAtahualpa.md` necesita consultar informacion de turnos anteriores. | Es el requerimiento mas directamente alineado con el problema critico de continuidad asistencial y cambio de turno. |
| RF-06 | 8/10 | PASSED | Beatriz Quiroz | `ReqFunc.md` permite registrar resultados de pruebas y mediciones; `Personas/BeatrizQuiroz.md` debe revisar y actualizar resultados. | Cubre necesidad central de resultados clinicos, aunque no precisa origen, estructura ni validacion de registros. |
| RF-07 | 8/10 | PASSED | Jose Atahualpa | `ReqFunc.md` permite registrar, consultar y actualizar planes de tratamiento; `Personas/JoseAtahualpa.md` y `Personas/JuanTorres.md` requieren conocer planes actuales. | Resuelve el flujo principal de tratamiento de forma sustancial, con vacio menor en versionado y vigencia entre turnos. |
| RF-08 | 8/10 | PASSED | Jose Atahualpa | `ReqFunc.md` exige generar alertas ante emergencias; `Personas/JoseAtahualpa.md` y `Personas/JuanTorres.md` requieren actuar ante situaciones criticas. | Cubre respuesta ante emergencias a nivel funcional, pero no define disparadores, prioridad ni responsables. |
| RF-09 | 5/10 | FAILED | Anderson Carcamo | `ReqFunc.md` exige enviar notificaciones al personal correspondiente cuando ocurra un evento relevante; varias personas requieren recibir alertas o comunicar cambios. | El objetivo es correcto, pero "evento relevante" y "personal correspondiente" son terminos vagos que debilitan verificabilidad y utilidad operativa. |
| RF-10 | 5/10 | FAILED | Beatriz Quiroz | `ReqFunc.md` exige registrar, asignar y priorizar solicitudes de interconsulta; `Personas/BeatrizQuiroz.md` es la persona mas vinculada por rol especialista. | Agrega valor clinico, pero carece de contexto de flujo, tiempos de atencion y criterios de asignacion; su articulacion con el problema central es parcial. |
| RF-11 | 5/10 | FAILED | Beatriz Quiroz | `ReqFunc.md` exige recibir y registrar automaticamente resultados de sistemas o dispositivos integrados; `Personas/BeatrizQuiroz.md` necesita resultados actualizados. | La necesidad existe, pero el requerimiento es incompleto porque no define que sistemas, frecuencia, validacion ni manejo de errores. |
| RF-12 | 8/10 | PASSED | Juan Torres | `ReqFunc.md` permite consultar disponibilidad del personal durante un turno; `Personas/JuanTorres.md` y `Personas/JoseAtahualpa.md` necesitan conocer personal disponible. | Bien alineado con coordinacion operativa y emergencias, aunque no define granularidad de disponibilidad ni criterios de actualizacion. |

## Evaluacion NFR

| Requerimiento | Puntaje | Estado | Persona afectada | Evidencia | Juicio |
|---|---:|---|---|---|---|
| RNF-01 | 3/10 | FAILED | Todos | `ReqNoFunc.md` exige iniciar la aplicacion en menos de 1 segundo. | Es medible, pero esta aislado del contexto clinico real, no define condiciones de carga, red o dispositivo, y no asegura por si solo consulta oportuna. |
| RNF-02 | 0/10 | FAILED | Todos | `ReqNoFunc.md` exige completar la configuracion de la aplicacion en menos de 5 segundos. | Es irrelevante o insuficientemente contextualizado frente al problema de UCI; no se define que configuracion impacta al negocio ni a las personas criticas. |
| RNF-03 | 8/10 | PASSED | Todos | `ReqNoFunc.md` exige disponibilidad minima de 99.9%; el caso requiere continuidad de atencion y acceso oportuno. | Alineado con continuidad asistencial y uso regional, aunque faltan ventanas, exclusiones y alcance exacto del servicio. |
| RNF-04 | 8/10 | PASSED | Todos | `ReqNoFunc.md` exige recuperarse de una caida en menos de 5 minutos. | Relevante para operacion critica UCI y preservacion de continuidad, con vacio menor en estrategia durante degradacion. |
| RNF-05 | 3/10 | FAILED | Todos | `ReqNoFunc.md` solo indica "soportar el crecimiento proyectado del piloto". | Trata un riesgo clave de escalabilidad regional, pero esta incompleto y no es verificable porque no define volumen, usuarios, sedes ni horizonte. |
| RNF-06 | 8/10 | PASSED | Jose Atahualpa | `ReqNoFunc.md` exige que la informacion clinica registrada y sincronizada pueda consultarse de forma consistente por usuarios autorizados. | Cubre de forma sustancial la continuidad de diagnosticos y tratamientos entre turnos, aunque sin metricas de consistencia o latencia. |
| RNF-07 | 8/10 | PASSED | Mauro Bobadilla | `ReqNoFunc.md` exige restringir acceso segun rol y permisos asignados; `Personas/MauroBobadilla.md` necesita acceso limitado. | Bien alineado con privacidad clinica y minimo privilegio, pero requiere mayor definicion de niveles y excepciones supervisadas. |
| RNF-08 | 5/10 | FAILED | Anderson Carcamo | `ReqNoFunc.md` exige actualizar informacion relevante de diagnosticos, tratamientos y emergencias de manera oportuna. | La direccion es correcta para cambios de turno y emergencias, pero "de manera oportuna" no es medible ni verificable. |
| RNF-09 | 8/10 | PASSED | Todos | `ReqNoFunc.md` exige mecanismos de respaldo y recuperacion para preservar la informacion ante fallos. | Requerimiento pertinente para continuidad clinica y seguridad de datos, aunque faltan objetivos concretos de respaldo y restauracion. |

## Resultado global

| Metrica | Valor |
|---|---|
| Evaluador | Carlos Balbuena |
| Puntaje global | 5/10 |
| Estado global | FAILED |
| Diagnostico | El set de requerimientos cubre el nucleo funcional del problema UCI y varias necesidades criticas de continuidad diagnostica, turnos, tratamiento y emergencias, pero su calidad global queda limitada por ambiguedades, baja verificabilidad y definiciones incompletas en permisos, oportunidad y escalabilidad. |
| Riesgos criticos | permisos por perfil insuficientemente definidos; escalabilidad regional no verificable; oportunidad de actualizacion y notificacion sin metricas operativas |
