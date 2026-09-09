# PROJECT_STATUS — App Cursos

Última actualización: fase "Tokens y base visual".

## Stack instalado
- Next.js 16.3.4 (App Router) · React 19.2.8 · TypeScript 5
- Tailwind CSS v4 · ESLint 9
- Turbopack para dev y build

> **Decisión pendiente:** el brief exige Next.js 15. `create-next-app` instala hoy
> la 16.3.4. El App Router y todo lo construido es idéntico en ambas. Confirmar
> si se fija en 15 o se acepta la 16.

## Hecho
- [x] Base de datos saneada (proyecto Supabase `nexora-test`)
  - RPC `enroll_in_course`, `mark_lesson_complete`, `complete_mission`
  - Escritura directa revocada en `lesson_progress`, `enrollments`,
    `entitlements`, `quiz_attempts`, `user_missions`
  - Tabla `user_missions` creada con RLS
  - 3 cursos basura archivados · quedan 3 publicados con contenido real
- [x] Design System v2 "Taller de Resultados" definido (`docs/DESIGN_SYSTEM.md`)
- [x] Tokens implementados en `src/app/globals.css`
- [x] Fuentes Archivo + Newsreader vía `next/font/google` (self-hosted en build)
- [x] Ruta temporal `/dev/tokens` para verificación visual
- [x] Script `npm run verify` (typecheck + lint + build)

## Verificado
`npm run verify` en verde. Rutas generadas: `/`, `/_not-found`, `/dev/tokens`.

Nota: la verificación se hizo con un stub del layout porque el entorno de
construcción no tenía acceso a `fonts.googleapis.com`. El layout real con
`next/font` requiere red en tiempo de build — condición que Vercel cumple.
**Confirmar que el primer deploy compila.**

## Pendiente
- [ ] Conectar Supabase al frontend (cliente, server, middleware)
- [ ] Primera pantalla real: catálogo
- [ ] Restringir `enroll_in_course` antes de cualquier lanzamiento público:
      hoy cualquier usuario registrado puede darse acceso gratis a los 3 cursos
- [ ] Borrar `/dev/tokens` antes del lanzamiento
