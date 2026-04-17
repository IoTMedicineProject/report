# Guía de colaboración

Idiomas disponibles:
- [English](CONTRIBUTING.md)
- [Español](CONTRIBUTING.es.md)

Este repositorio contiene la **documentación principal del proyecto** en `README.md` junto con todos los recursos organizados en `assets/`.  
Esta guía define cómo trabajamos en equipo para mantener un flujo ordenado y consistente.

---

## 1) Introducción rápida

Esta sección explica cómo configurar el repositorio en local y comenzar a contribuir.

- **Clonar el repositorio**
    ```bash
    git clone <URL-DEL-REPOSITORIO>
    cd <NOMBRE-DEL-REPO>
    ```

- **Configurar tu usuario**
    Asegúrate de que Git tenga tu usuario configurado:
    ```bash
    git config --global user.name "Tu Nombre"
    git config --global user.email "tu.email`ejemplo.com"
    ```

- **Actualizar tus ramas locales**
    ```bash
    git fetch origin
    git checkout develop
    git pull origin develop
    ```

- **Crear tu rama de feature (desde `develop`)**
    Usa el naming acordado: `feature/<entregable>-<autor>`
    ```bash
    git checkout -b feature/tb1-nombre develop
    ```

- **Trabajar y hacer commits (Conventional Commits + scope opcional)**
    Formato: `<type>(<scope>): <message>`
    Ejemplos:
    - `docs(intro): add draft for TB1 introduction`
    - `fix(matrix): resolve typo in user-task-matrix v02`
    ```bash
    git add .
    git commit -m "docs(intro): add draft for TB1 introduction"
    ```

- **Mantener tu rama actualizada (fetch + merge)**
    ```bash
    git checkout feature/tb1-nombre
    git fetch origin
    git merge origin/develop
    # si hubo conflictos, resuélvelos y luego:
    git push origin feature/tb1-nombre
    ```

    > Consejo: `git fetch` no toca tu working tree; integras cuando haces `git merge`.

- **Subir tu rama al remoto**
    ```bash
    git push origin feature/tb1-nombre
    ```

- **Abrir un Pull Request (PR)**
    - Base: `develop` (nunca a `main`).
    - Usa la plantilla del PR y explica qué/por qué.
    - Si aplica, enlaza un Issue con `Closes #<número-del-issue>`.
    - Solicita la revisión de al menos un compañero.
    - Haz merge usando **Merge commit** (sin squash).

---

- Guía rápida de comandos básicos de Git
    - `git status` → ver archivos modificados y estado
    - `git add <archivo>` → preparar cambios
    - `git commit -m "mensaje"` → guardar cambios localmente
    - `git log --oneline` → historial corto de commits
    - `git fetch origin` → traer refs remotas sin mezclarlas
    - `git merge origin/develop` → integrar develop remoto en tu rama
    - `git push origin <rama>` → subir tu rama al remoto
    - `git pull origin <rama>` → traer y mezclar cambios del remoto

## 2) Flujo de trabajo con Git

- Repositorio central: GitHub. Rama principal: `main`.
- Modelo de ramas: **Gitflow**
    - `main`: código/documentación estable en producción.
    - `develop`: integración de nuevas funcionalidades o secciones.
    - Ramas de soporte:
        - `feature/<entregable>-<autor>`: desarrollo de nuevas secciones o aportes.  
          Ejemplo: `feature/tb1-salim`
        - `hotfix/<nombre>`: correcciones críticas en producción.  
          Ejemplo: `hotfix/c4-diagrams`
        - `release/<versión>`: preparación de una entrega estable antes de fusionar en `main`.  
          Ejemplo: `release/v1.0.0` (TB1 → v1.0.0, TP1 → v2.0.0, TB2 → v3.0.0, TF1 → v4.0.0)

- **Mantener ramas actualizadas**:
    - Hazlo de forma regular (no solo antes de un PR), especialmente después de merges en `develop`.
    - **Traer lo último de `develop` y mezclarlo en tu `feature`**:
      ```bash
      # Estar en tu rama de trabajo
      git checkout feature/tb1-nombre

      # Traer referencias remotas sin mezclar aún
      git fetch origin

      # Mezclar los cambios confirmados en develop dentro de tu feature
      git merge origin/develop

      # (si hubo conflictos, resuélvelos, haz commit y continúa)
      git push origin feature/tb1-nombre
      ```
      > Ventaja: `git fetch` no toca tu working tree; ves qué viene y **tú** decides cuándo mezclar (`merge`).

    - **Mantén tu `develop` local actualizado** periódicamente:
      ```bash
      git checkout develop
      git fetch origin
      git merge origin/develop
      ```
      
    - **Después de que otro PR se mergee a `develop`**, repite el proceso en tu `feature` para evitar conflictos tardíos.

- **Commits**:
    - Mensajes descriptivos, concisos y consistentes en inglés.
    - Usamos el estándar **Conventional Commits** con **scope opcional** para indicar la parte del proyecto afectada.
    - Formato: `<type>(<scope>): <message>`
    - Ejemplos:
        - `feat(requirements): add enrollment journey map as-is`
        - `fix(matrix): resolve typo in user-task-matrix v02`
        - `docs(intro): add introduction draft for TB1`
        - `docs(bibliography): correct APA references`

- **Versionado**:
    - Seguimos **Semantic Versioning 2.0 (semver)** para los tags de release.
        - Formato: `MAJOR.MINOR.PATCH`
        - Ejemplos: `1.0.0`, `1.1.0`, `1.1.1`

- **Pull Requests (PR)**:
    - Todos los cambios deben pasar por un PR desde una rama `feature/*` hacia `develop` (nunca hacer commits directos a `develop` o `main`).
    - Incluir un resumen del cambio y captura(s) de pantalla si aplica.
    - Asegurarse de que los archivos exportados estén sincronizados con sus fuentes (ver Sección 4).
    - Se requiere la revisión de al menos un compañero antes de hacer merge.
    - Usar **Merge commit** (no squash) para preservar el historial completo de commits.

---

## 3) Estructura de carpetas

```
assets/
├── requirements/        # Artefactos de requerimientos
│   ├── personas/
│   ├── scenarios/
│   ├── maps/            # empathy-maps, journey-maps, impact-maps
│   └── matrices/        # task-matrices
│
├── lean-ux/             # canvas, problem statements, hypothesis
│
├── ux-ui/               # wireframes, mockups, prototypes
│
├── diagrams/            # C4, UML, DDD, DB (con src/ y out/)
│   ├── c4/
│   ├── uml/
│   ├── ddd/
│   └── db/
│
├── images/              # screenshots, figures, photos
│   ├── screenshots/
│   ├── figures/
│   └── photos/
│
├── logos/               # Logos oficiales (preferir .svg)
└── icons/               # Íconos reutilizables (.svg recomendado)
```

---

## 4) Convenciones de nombres

- **lowercase + kebab-case**: palabras en minúsculas, separadas por guiones.
- **Solo ASCII**: sin acentos, ñ, espacios ni caracteres especiales.
- Orden de los tokens: **general → específico** (ejemplo: `diagram-c4-container-v01.svg`).
- **Versionado**: sufijo `-vNN` (ejemplo: `-v01`, `-v02`).
- **Fecha ISO opcional**: `-YYYY-MM-DD` cuando se requiera trazabilidad.
- Mantener el **mismo nombre base** entre el archivo fuente y el exportado:
    - `academy-l2-container.drawio` ↔ `academy-l2-container.svg`
- Preferir nombres de archivo en inglés (consistencia entre todos los miembros del equipo).

**Patrón sugerido**  
```
<área>-<dominio>-<tipo>-<detalle>[-<nivel>][-<estado>][-<idioma>][-vNN][-YYYY-MM-DD].<ext>
```

**Ejemplos**
- `academy-enrollment-journey-map-as-is-v01.svg`
- `iam-domain-class-diagram-v02.puml`
- `academy-user-task-matrix-v03.xlsx`
- `lean-ux-canvas-academy-es-v02.svg`

---

## 5) Recursos editables (`src/`) y exportados (`out/`)

- En `diagrams/`, cada tipo (C4, UML, DDD, DB) usa dos carpetas:
    - `src/` → archivos **editables**: `.drawio`, `.puml`, `.mmd`, `.bpmn`
    - `out/` → **exportados** para insertar en `README.md`: `.svg` (preferido) o `.png`
- `images/`, `logos/` e `icons/` contienen archivos finales (no requieren `src/out`).
- **Exportar a .svg** cuando sea posible (vectorial, nítido en PDF).
- Mermaid se puede embeber en el README directamente, pero si exportas para PDF estable, guarda el `.svg` en `out/` con la misma raíz de nombre.

**Ejemplos de referencia en el README**
```
![Journey Map](./assets/requirements/maps/journey-maps/enrollment-journey-map-as-is-v01.svg)
![C4: Container](./assets/diagrams/c4/out/academy-L2-container.svg)
```

---

## 6) Edición de `README.md`

- `README.md` es el **documento principal**.
- Inserta recursos **solo** desde `assets/` (no subas imágenes al raíz).
- Mantén encabezados coherentes y consistentes.
- Cuando actualices un diagrama:
    1) Edita la fuente en `src/`
    2) Exporta a `out/` con el mismo nombre base y versión
    3) Actualiza la referencia si cambia la versión

---

## 7) Issues
- Usa Issues para reportar problemas, contenido faltante o sugerir mejoras.
- Al abrir un Issue, sigue la plantilla de Issue.
- Formato del título: "[Docs] Título corto y descriptivo" (ejemplo: "[Docs] Corregir referencias APA en el Capítulo 3").
- Asígnate el Issue si planeas trabajarlo.
- Enlaza Issues con PRs siempre que sea posible escribiendo `Closes #<número-del-issue>` en la descripción del PR.

---

## 8) Pull Requests
- Todos los cambios deben pasar por un Pull Request (PR) desde una rama `feature/*` hacia `develop` (nunca hacer commits directos a `develop` o `main`).
- Formato del título: corto y descriptivo (ejemplo: "TB1 – Agregar sección de Introducción").
- Descripción: explica **qué** cambiaste y **por qué**. Usa la plantilla de PR.
- Si el PR resuelve un Issue, incluye `Closes #<número-del-issue>` en la descripción.
- Antes de abrir el PR, asegúrate de que tu rama `feature` esté actualizada con `origin/develop`.
- Se requiere la revisión de al menos un compañero antes de hacer merge (usa la pestaña *Files changed* y la opción **Review → Approve**).
- Mantén los commits pequeños y con sentido (evita “big dump commits”).
- **Recordatorio:** No uses squash. Usa la opción por defecto **Merge commit** en GitHub para preservar el historial completo de commits.

---

## 9) Lista de verificación antes de abrir un PR

- [ ] Los nombres de archivo siguen la convención (kebab-case, versión, idioma si aplica).
- [ ] Los archivos exportados (`out/`) están sincronizados con sus fuentes (`src/`).
- [ ] `README.md` se renderiza correctamente (rutas relativas correctas).
- [ ] No hay archivos temporales, de respaldo ni binarios innecesarios.
- [ ] Los diagramas fueron exportados a `.svg` siempre que sea posible (para calidad en PDF).
- [ ] El texto fue revisado (ortografía/estilo).
- [ ] El PR enlaza un Issue en la descripción si aplica.

---

## 10) Buenas prácticas

- Commits pequeños y temáticos.
- Un cambio lógico por PR (evitar PRs gigantes).
- Adjunta vista previa (imagen) en el PR cuando edites diagramas relevantes.
- Para capturas: usar nombres secuenciales con cero a la izquierda (ej. `...-screenshot-01.png`, `...-screenshot-02.png`).

---

## 11) Resolución de conflictos

- Actualiza tu rama con `main` frecuentemente: `git pull origin main`
- Si hay conflictos en `README.md`:
    - Coordina por el canal del equipo antes de resolver.
    - Mantén la versión más reciente de exportados y elimina duplicados obsoletos.

---

## 12) Seguridad y privacidad

- No subir datos sensibles (PII, credenciales, tokens, variables de entorno).
- No subir materiales con licencias restrictivas sin autorización.
- Logos institucionales: usar versiones aprobadas (preferir `.svg`).

---

## 13) Comunicación

- Usa el canal acordado (Discord/WhatsApp) para coordinar PRs y revisiones.
- En el PR, describe **qué cambiaste y por qué**.
- Etiqueta a quien corresponda para revisión.

---

## 14) Reconocimiento de autores

Los autores principales de este proyecto están listados en [AUTHORS.md](./AUTHORS.md).  
Este repositorio es un **proyecto de equipo cerrado**; no se aceptan contribuciones externas.  
Si fuera necesario, los colaboradores adicionales pueden documentarse en un archivo separado `CONTRIBUTORS.md`.

---