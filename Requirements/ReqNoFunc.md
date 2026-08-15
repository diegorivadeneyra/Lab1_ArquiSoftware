# Requerimientos No Funcionales

RNF-01 - El sistema deberá mostrar la pantalla principal operativa del usuario en un tiempo menor a 2 segundos desde el inicio de sesión exitoso, tanto en estaciones de trabajo de escritorio como en dispositivos móviles institucionales conectados a la red interna hospitalaria, soportando al menos 200 usuarios concurrentes por sede en condiciones normales de operación.

RNF-02 - El sistema deberá mostrar la ficha clínica completa de un paciente, incluyendo diagnóstico, plan de tratamiento, resultados recientes y alertas activas, en un tiempo menor a 2 segundos desde que un usuario autorizado selecciona al paciente, tanto en estaciones de trabajo de escritorio como en dispositivos móviles institucionales conectados a la red interna hospitalaria, bajo condiciones normales de operación.

RNF-03 -  El sistema deberá mantener una disponibilidad mínima del 99.9%.

RNF-04 - El sistema deberá recuperarse de una caída o interrupción del servicio en menos de 5 minutos.

RNF-05 - El sistema deberá soportar el crecimiento progresivo del piloto desde su despliegue inicial en Lima hasta una expansión nacional, escalando desde 1,000 usuarios institucionales en la etapa de lanzamiento, hasta 100,000 usuarios institucionales en los primeros 6 meses y hasta 10,000,000 de registros clínicos e históricos de atención en un horizonte de 2 años. Durante dicho crecimiento, el sistema deberá mantener la gestión de horarios sin cruces, la disponibilidad consistente de diagnósticos entre turnos y los tiempos de respuesta, disponibilidad y recuperación definidos en los demás requerimientos no funcionales.

RNF-06 - El sistema deberá garantizar que la información clínica registrada y sincronizada pueda ser consultada de forma consistente por los usuarios autorizados.

RNF-07 - El sistema deberá restringir el acceso a la información de los pacientes según el rol y los permisos asignados a cada usuario.

RNF-08 - El sistema deberá reflejar en la historia clínica u hoja de vida del paciente toda actualización aprobada de diagnósticos y tratamientos en un tiempo menor a 2 segundos desde su registro final. En el caso de emergencias o alertas críticas, la actualización y visibilidad para el personal autorizado deberá realizarse en menos de 1 segundo desde su generación. Si existiera sobresaturación del sistema, estas actualizaciones deberán procesarse mediante mecanismos de respaldo sin pérdida de información y con una demora máxima de 30 segundos.

RNF-09 - El sistema deberá contar con mecanismos de respaldo y recuperación que permitan preservar la información ante fallos del sistema.
