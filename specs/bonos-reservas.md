# Spec: Reservas de clases con control de bonos y aforo

## Estado
Validada para MVP — alcance de demostración local.

## Problema
Andrea usa tarjetas de papel para bonos de 10 clases y gestiona manualmente las plazas. Las tarjetas se pierden, el saldo genera disputas y las sesiones de tarde se llenan sin una lista de espera ordenada. Necesita una fuente única y verificable para reservas, asistencia y clases restantes.

## Solución
Una vista de gestión permite:
- consultar sesiones, aforo y plazas libres;
- reservar a una alumna si hay plaza y bono activo con saldo;
- añadirla a una lista de espera si la sesión está completa;
- registrar asistencia y descontar una clase una sola vez;
- cancelar una reserva y liberar plaza;
- promocionar a la primera persona de la lista de espera;
- mostrar el saldo de cada bono y un historial básico.

## Reglas
- Cada bono comienza con 10 clases.
- Una reserva no consume saldo.
- La asistencia consume 1 clase.
- No se puede reservar con bono agotado.
- Una alumna no puede reservar dos veces la misma sesión.
- El aforo por defecto es 12, configurable por sesión.
- Lista de espera FIFO (primero en entrar, primero en salir).
- La demo usa datos en memoria/local; no equivale a backend multiusuario de producción.

## Criterios de aceptación verificables
1. **Saldo:** al crear un bono, la alumna ve 10 clases disponibles; al marcar asistencia, el saldo baja a 9 exactamente una vez.
2. **Aforo:** con 12 reservas confirmadas, una nueva reserva no aumenta el aforo y se incorpora a la lista de espera.
3. **Lista de espera:** al cancelar una reserva confirmada, la primera alumna en espera pasa a ocupar la plaza liberada.
4. **Duplicados:** el sistema impide que una alumna tenga dos reservas activas para la misma sesión y evita descontar dos veces una asistencia.
5. **Transparencia:** la interfaz muestra plazas ocupadas/libres, estado de reserva y saldo restante sin necesidad de consultar tarjetas físicas.

## Fuera de alcance
Pagos, tienda, vídeos, contenido de yoga, WhatsApp/SMS, autenticación real y persistencia de servidor.
