# Instrucciones generales del proyecto — Yoga Studio

## Objetivo
Construir una aplicación sencilla para que Andrea gestione alumnas, bonos de 10 clases, sesiones, reservas, aforo y listas de espera.

## Principios de trabajo
- Trabaja mediante Spec Driven Development: consulta la spec antes de implementar y actualízala si cambia una regla.
- No inventes requisitos de negocio. Si falta una regla no crítica, adopta un valor por defecto explícito y configurable.
- Prioriza flujos funcionales y accesibles frente a elementos decorativos.
- Interfaz en español, responsive y mobile-first.
- Mantén el código modular, legible y fácil de probar.
- No incluyas vídeos, rutinas, tienda ni pagos online en este MVP.
- Nunca simules persistencia o notificaciones reales sin indicarlo claramente.

## Reglas de negocio base
- Un bono nuevo contiene 10 clases.
- Reservar no descuenta una clase; registrar asistencia sí.
- Una asistencia consume exactamente una clase y no puede duplicarse.
- Aforo predeterminado: 12 plazas por sesión.
- Si no hay plazas, la alumna entra en lista de espera por orden de llegada.
- Una plaza liberada se ofrece a la primera persona elegible de la lista.
- Las operaciones de aforo y consumo deben ser atómicas en producción.
- Los cambios relevantes deben dejar trazabilidad.

## Calidad y entrega
- Define criterios de aceptación verificables antes de implementar.
- Ejecuta pruebas de los criterios de aceptación y documenta resultados.
- Mantén README con instalación, uso, limitaciones y próximos pasos.
- No expongas secretos; usa variables de entorno para credenciales.
