# CLAUDE.md — alc-homes-historial-web

## Qué es este proyecto
Panel de administración/historial para el hostal ALC Homes San Blas. Muestra el registro de interacciones del sistema de check-in (quién hizo check-in, cuándo, qué pasó).

## Repos relacionados (organización alchomes2025-afk)
- Este repo: `alc-homes-historial-web` — Firebase Hosting: https://alc-homes-historial.web.app
- Check-in de huéspedes: `alc-homes-checkin-web`
- Backend: API pública del hostal (Render) — confirmar nombre exacto del repo

## Comportamiento clave
- Los registros de interacción se respaldan en **Firestore**.
- **Login con Google Sign-In implementado (septiembre 2026)**: Firebase Auth (proyecto `alc-homes-checkin`, mismo que el frontend de check-in), restringido a `alchomes2025@gmail.com` por comparación de email en el cliente. Es solo un filtro visual: tras el login de Google, sigue apareciendo el paso del token de administración de siempre (`API_TOKEN`/`TEST_TOKEN`), porque el backend (`/historial`) no verifica la sesión de Firebase — sigue exigiendo ese mismo token compartido. Si se quiere que el backend también valide el login de Google, hay que tocar `routes/historial.py` en `hostal-pdf-extractor` (avisar antes, según su propio claude.md).

## Estilo de trabajo de Adrián
- Sin entorno local hasta ahora — viene de trabajar 100% desde GitHub web UI, commits directos a `main` con auto-deploy. Verificar en local con Claude Code antes de hacer push.
- Es un panel de administración interno (no lo ven huéspedes), así que el nivel de precaución ante cambios es menor que en el frontend de check-in — aun así, avisar antes de tocar la lógica de Firestore que alimenta el historial.
