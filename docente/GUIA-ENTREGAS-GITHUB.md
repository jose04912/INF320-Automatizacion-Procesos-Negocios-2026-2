# Guía docente — Entregas por GitHub (sin GitHub Classroom)

GitHub Classroom está en transición hacia soluciones de terceros y no está disponible para configurar
asignaciones nuevas en este momento. En vez de depender de ese servicio, este curso usa **la función
nativa de plantillas de GitHub** ("Template repository"), que ya está activada en los dos repositorios
del curso y no depende de ningún servicio externo:

| Repositorio | Tipo | URL |
|---|---|---|
| Asignaciones/laboratorios (individual) | 1 copia por estudiante | `https://github.com/avila-fiec-up/INF320-Automatizacion-Procesos-Negocios-2026-2` |
| Proyecto integrador (equipo) | 1 copia por equipo de 4-5 | `https://github.com/avila-fiec-up/INF320-Proyecto-Integrador-2026-2` |

Ambos son **privados** y están marcados como plantilla (*Template repository* activo).

---

## 1. Cómo obtiene su copia cada estudiante (instrucciones para ellos)

Comparte esto tal cual con la clase — también está en `README.md` de cada repo. Muchos estudiantes de
Comercio Electrónico usarán Git por primera vez: dedica los primeros 20-30 minutos de la semana 1 a
recorrer esto juntos en vivo, no asumas que ya lo saben.

1. Entra a la URL del repo individual (arriba).
2. Botón verde **"Use this template"** → **"Create a new repository"**.
3. **Owner**: tu propia cuenta de GitHub (no hace falta pertenecer a ninguna organización).
4. **Repository name**: puedes dejar el mismo nombre o poner `INF320-<tu-nombre>-2026-2`.
5. **Visibility**: **Private**.
6. Click **Create repository from template** — en segundos tienes tu propia copia completa bajo tu cuenta.
7. En **Settings → Collaborators** de tu repo nuevo, agrega al docente (`profangelavila671-spec`) con acceso de lectura como mínimo.
8. Si nunca usaste Git: la sección "Control de versiones" de `recursos/herramientas-setup.md` tiene el flujo básico (`clone`, `add`, `commit`, `push`) paso a paso.

Para el **proyecto integrador** (equipo de 4-5): un solo integrante repite los mismos pasos con el repo de proyecto, y luego agrega como colaboradores a sus compañeros de equipo **y** al docente desde **Settings → Collaborators**.

## 2. Cómo tú (docente) ves y sigues todas las entregas

En cuanto un estudiante/equipo te agrega como colaborador, su repo aparece en tu propia cuenta. Para
listarlos todos de una vez (con la GitHub CLI, `gh`, ya instalada y autenticada en esta máquina):

```bash
# Todos los repos donde eres colaborador (no propietario) — es decir, todas las entregas
gh api /user/repos --paginate -X GET -f affiliation=collaborator --jq '.[] | select(.name | test("INF320")) | .full_name'
```

Recomendación práctica: pide que cada estudiante/equipo te agregue **en las primeras 48 horas** de la
semana correspondiente y usa ese mismo comando como pase de lista.

## 3. Checklist automático (no calificador)

Cada copia hereda `.github/workflows/checklist-entregas.yml`: al hacer `git push`, confirma en la
pestaña **Actions** si los archivos esperados de la semana ya existen en la ruta correcta. Es
informativo, no reemplaza tu revisión con la rúbrica.

## 4. Si más adelante GitHub Classroom vuelve a estar disponible

Los dos repos ya cumplen todos los requisitos para usarlo (marcados como plantilla, en una
organización). Si quieres retomarlo, solo faltaría: entrar a classroom.github.com, vincular la
organización `avila-fiec-up`, y crear una asignación individual y una grupal apuntando a estos mismos
repos — el resto del curso no cambia.
