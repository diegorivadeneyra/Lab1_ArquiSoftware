# Usuarios / Clientes

## Usuarios del sistema

- Medico intensivista de turno
- Medico especialista
- Enfermero
- Enfermero en jefe
- Interno de medicina

## Clientes

- ESSALUD

### Medico intensivista de turno

El medico intensivista de turno utiliza el sistema para consultar y actualizar informacion clinica critica de los pacientes, validar diagnosticos, coordinar la continuidad asistencial entre turnos y responder ante situaciones de emergencia.

### Medico especialista

El medico especialista utiliza el sistema para atender interconsultas, consultar el estado clinico del paciente, validar informacion oficial en la historia clinica y emitir conclusiones especializadas segun el caso.

### Enfermero

El enfermero utiliza el sistema para consultar indicaciones medicas y planes de tratamiento, registrar signos vitales y resultados manuales, y reportar situaciones relevantes del paciente durante el turno.

### Enfermero en jefe

El enfermero en jefe utiliza el sistema para coordinar horarios y turnos, supervisar la disponibilidad del personal de enfermeria, verificar cobertura minima de atencion y apoyar la respuesta operativa ante alertas criticas.

### Interno de medicina

El interno de medicina utiliza el sistema para consultar informacion clinica y operativa necesaria para su turno, registrar observaciones locales y ejecutar tareas asignadas por medicos bajo supervision.

### ESSALUD

ESSALUD es el cliente y organizacion responsable de implementar y utilizar el sistema para mejorar la gestion de horarios, diagnosticos, tratamientos, continuidad asistencial y respuesta ante emergencias dentro de las UCI.


# Definición del Problema

ESSALUD esta desarrollando un piloto para mejorar la gestion de los sistemas utilizados en las Unidades de Cuidados Intensivos (UCI).

El principal problema identificado es la dificultad para gestionar los horarios del personal medico y de enfermeria, especialmente debido a la alta rotacion de medicos internistas.

Esta situacion dificulta la continuidad de la atencion, debido a que los diagnosticos, resultados y planes de tratamiento registrados durante un turno deben estar disponibles de forma oportuna para el personal responsable del siguiente turno.

Adicionalmente, el sistema debe permitir controlar el acceso segun rol, conocer la disponibilidad real del personal, responder con rapidez ante emergencias clinicas y soportar una futura expansion regional y nacional del piloto.

## Problemas identificados

### 1. Cruce de horarios

Existe la necesidad de gestionar correctamente los horarios y turnos de medicos y enfermeros para evitar conflictos, garantizar la cobertura minima de la UCI y reducir errores de coordinacion operativa.

### 2. Transmisión de diagnósticos

Los diagnosticos, resultados y planes de tratamiento deben estar disponibles, visibles y trazables para el personal del siguiente turno sin depender de traspasos informales.

### 3. Gestión del personal de enfermería

Es necesario conocer la disponibilidad y asignacion del personal clinico para garantizar una adecuada atencion de los pacientes y una correcta reaccion ante emergencias o interconsultas.

### 4. Alertas de emergencia

Ante una situacion critica, el sistema debe detectar o registrar el evento, escalarlo segun jerarquia y facilitar la comunicacion con el medico o personal responsable en tiempos compatibles con un entorno UCI.

### 5. Actualizaciones en tiempo real

Los cambios importantes relacionados con diagnosticos, tratamientos, resultados y estado de los pacientes deben estar disponibles oportunamente para los usuarios autorizados, incluso en escenarios de sobresaturacion o cambio de turno.

## Prompt

### Prompt usado para evaluar requerimientos vs personas

**SYSTEM**

`@Agents/Spec/Eval-Spec.md`

**USER**

```text
Evalua este proyecto.
Lee los requerimientos funcionales y no funcionales definidos en Requirements/.
Lee las personas definidas en Personas/.
Inspecciona la implementacion actual del repositorio y genera la evaluacion completa en el formato Markdown definido.
```
