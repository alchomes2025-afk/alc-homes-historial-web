# CLAUDE.md — alc-homes-historial-web

## Qué es este proyecto
Panel de administración/historial para el hostal ALC Homes San Blas. Muestra el registro de interacciones del sistema de check-in (quién hizo check-in, cuándo, qué pasó).

## Repos relacionados (organización alchomes2025-afk)
- Este repo: `alc-homes-historial-web` — Firebase Hosting: https://alc-homes-historial.web.app
- Check-in de huéspedes: `alc-homes-checkin-web`
- Backend: API pública del hostal (Render) — confirmar nombre exacto del repo

## Comportamiento clave
- Los registros de interacción se respaldan en **Firestore**.
- Login con Google Sign-In estaba planeado en su momento — **verificar el estado real en el código** antes de asumir que está implementado o no.

## Estilo de trabajo de Adrián
- Sin entorno local hasta ahora — viene de trabajar 100% desde GitHub web UI, commits directos a `main` con auto-deploy. Verificar en local con Claude Code antes de hacer push.
- Es un panel de administración interno (no lo ven huéspedes), así que el nivel de precaución ante cambios es menor que en el frontend de check-in — aun así, avisar antes de tocar la lógica de Firestore que alimenta el historial.
