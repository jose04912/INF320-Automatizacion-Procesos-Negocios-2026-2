# Guía docente — Configurar INF 320 en GitHub Classroom

Este curso usa **dos asignaciones separadas** en GitHub Classroom porque Classroom no permite mezclar
trabajo individual y trabajo en equipo dentro de una misma asignación: cada asignación crea **un repo
por estudiante** o **un repo por equipo**, nunca ambos a la vez.

| Asignación | Tipo | Repo plantilla (este árbol de carpetas) | Cuándo se abre |
|---|---|---|---|
| Asignaciones, quices y laboratorios individuales | Individual | `INF320-Automatizacion-Procesos-Negocios-2026-2` | Semana 1 |
| Proyecto integrador | Grupal (equipos de 4-5) | `INF320-Proyecto-Integrador-2026-2` | Semana 3 (kickoff) |

---

## 1. Requisitos previos (una sola vez por semestre)

1. Tener una **organización de GitHub** para la universidad/facultad (o una personal si aún no hay una institucional).
2. Activar [GitHub Classroom](https://classroom.github.com) con tu cuenta docente y conectarla a esa organización.
3. Crear el classroom del semestre, por ejemplo: `INF320-2026-2`.
4. Importar el roster de estudiantes (CSV o vínculo a Google Classroom/Canvas).

> Este curso es de la Licenciatura en Comercio Electrónico y muchos estudiantes usarán Git por primera vez. Dedica los primeros 20-30 minutos de la semana 1 (sección "Control de versiones" de `recursos/herramientas-setup.md`) a un recorrido guiado de crear cuenta → aceptar invitación → clonar → editar → `git add/commit/push`, no asumas que ya lo saben.

## 2. Subir los repos plantilla

Para cada uno de los dos repos (`INF320-Automatizacion-Procesos-Negocios-2026-2` y `INF320-Proyecto-Integrador-2026-2`):

```bash
cd INF320-Automatizacion-Procesos-Negocios-2026-2      # o INF320-Proyecto-Integrador-2026-2
git init
git add .
git commit -m "Plantilla inicial INF 320 — semestre 2026-2"
git branch -M main
git remote add origin https://github.com/<tu-organizacion>/<nombre-del-repo>.git
git push -u origin main
```

Luego, en GitHub → *Settings* del repo → activa **"Template repository"** (obligatorio para poder crear asignaciones desde él).

## 3. Crear la asignación individual

En Classroom → *New assignment*:

- **Nombre**: `Asignaciones y Laboratorios — INF 320`
- **Tipo**: *Individual assignment*
- **Repositorio plantilla**: `INF320-Automatizacion-Procesos-Negocios-2026-2`
- **Visibilidad**: *Private*
- **Autograding**: el repo incluye `.github/workflows/classroom.yml`, un checklist **informativo** (no bloqueante) que confirma en cada push si los archivos esperados de la semana ya existen en la ruta correcta — útil para que el estudiante vea de inmediato si olvidó guardar algo en la carpeta correcta, no reemplaza tu revisión con la rúbrica.
- Genera el enlace de invitación y publícalo la semana 1.

## 4. Crear la asignación del proyecto integrador (grupal)

En Classroom → *New assignment*:

- **Nombre**: `Proyecto Integrador — INF 320`
- **Tipo**: *Group assignment*
- **Tamaño de equipo**: 4-5 integrantes
- **Grouping**: crea uno nuevo, por ejemplo `Equipos-Proyecto-INF320`
- **Repositorio plantilla**: `INF320-Proyecto-Integrador-2026-2`
- **Visibilidad**: *Private*
- Genera el enlace de invitación y publícalo **en la semana 3**, después del kickoff. Los estudiantes que ingresan el mismo nombre de equipo comparten automáticamente un solo repo — coordina con ellos el nombre exacto de equipo antes de compartir el enlace, para evitar equipos duplicados por typos.

## 5. Flujo semanal del docente

1. *Classroom → assignment → ver todos los repos* te da un vistazo de quién ha hecho push, sin clonar cada repo manualmente.
2. Para retroalimentación puntual sobre un diagrama BPMN o un flujo, comenta directamente en el commit o abre un *Issue* — queda como registro permanente y es más rápido que corregir por correo.
3. Descarga masiva antes de calificar: `gh classroom clone student-repos` (requiere `gh extension install github/gh-classroom`).
4. Los diagramas BPMN (`.bpmn`, `.png`) y capturas de flujos son binarios/imágenes — recuérdales a los equipos nombrar los archivos según la convención de `README.md` (`semanaXX-bpmn-as-is-v1.png`) para poder revisarlos rápido en GitHub sin descargarlos.

## 6. Notas importantes

- El repo de trabajo individual y el del proyecto integrador son **independientes** — revísalos por separado.
- Recuerda la política de datos (`politicas/reglas-del-aula.md` — Manejo ético de datos): ningún dato real de clientes sube a un repo público ni a una plataforma de terceros sin anonimizar, ni siquiera en capturas de pantalla.
- Si un equipo cambia de integrantes a mitad de semestre, reasígnalo manualmente desde Classroom (*Manage repository access*).
