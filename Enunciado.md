# 🧩 Práctica: Colaboración con ramas y fusiones (con conflictos) en GitHub

## Objetivo

Practicar flujo de trabajo con Git en equipo: clonado, ramas por persona, commits atómicos, fusiones a `main` y **resolución de conflictos**.

## Reglas de trabajo

* Cada alumno crea **su propia rama** desde `main` con su inicial: `feat/A`, `feat/B`, `feat/C`, `feat/D`.
* Cada alumno hace **sus commits en su rama** y **fusiona directamente a `main`** (desde local) usando `git merge` (sin pull request).
* Para asegurar conflictos, **todas las personas deben editar las mismas líneas indicadas** más abajo **antes** de que se hagan los primeros merges. No coordinéis la edición de esas líneas on-line: se busca el choque.

---

## Tareas por alumno (generan conflictos y cambios reales)

> Haz los pasos en el orden indicado. No hagas `git pull` de `main` hasta terminar los 3 primeros commits individuales de tu rama: así fuerza conflictos al fusionar.

### Tareas comunes

> Realiza estos pasos haciendo un commit después de cada uno, y subiendo los cambios al repositorio.

- Crea en la carpeta textos un archivo .txt con tu nombre y escribe dentro como te llamas.
- Añade cual es tu color favorito.
- Añade cual es tu deporte favorito.
- Borra tu color favorito.

### Alumno A

1. **README.md** – Cambia estas dos líneas exactas:

   * `Estado: borrador` → `Estado: en progreso`
   * `Lema: _Por definir_` → `Lema: _Haciendo equipo_`
2. **config/app.json** – Cambia:

   * `"puerto": 3000` → `"puerto": 8080`
   * Añade `"caracteristicas": ["base","cli"]` (mismo orden que ves).
3. **equipo.md** – Sustituye `- A: sin bio` por tu bio en una línea.
4. **Fusiona tu rama a `main`** con `--no-ff`. Si hay conflicto, resuélvelo manteniendo **tu cambio de puerto** a 8080 **y** añadiendo cualquier nueva clave que exista en la versión de `main`.

### Alumno B

1. **README.md** – Cambia estas dos líneas exactas:

   * `Estado: borrador` → `Estado: listo para revisión`
   * `Lema: _Por definir_` → `Lema: _Calidad ante todo_`
2. **config/app.json** – Cambia:

   * `"puerto": 3000` → `"puerto": 5000`
   * Añade una nueva clave `"entorno": "desarrollo"` al final del JSON.
3. **textos/cita.txt** – Añade al final **otra línea** con tu cita.
4. **Fusiona tu rama a `main`** con `--no-ff`. Si hay conflicto, resuélvelo manteniendo **la clave `entorno`** y **el puerto que acuerde el equipo** (ver “Normas de resolución”).

### Alumno C

1. **README.md** – Cambia estas dos líneas exactas:

   * `Estado: borrador` → `Estado: estable`
   * `Lema: _Por definir_` → `Lema: _Iterar y mejorar_`
2. **config/app.json** – Cambia:

   * `"modo": "borrador"` → `"modo": "produccion"`
   * Reordena el array `"caracteristicas"` alfabéticamente.
3. **CHANGELOG.md** – Añade sección `## [0.2.0] - Cambios de configuración` con 2 bullets reales.
4. **Fusiona tu rama a `main`** con `--no-ff`. Si hay conflicto en JSON, resuélvelo **manteniendo todas las claves añadidas por otros** y dejando **ordenadas por clave** (A-Z).

### Alumno D

1. **README.md** – Cambia estas dos líneas exactas:

   * `Estado: borrador` → `Estado: en test`
   * `Lema: _Por definir_` → `Lema: _Fallando rápido_`
2. **config/app.json** – Cambia:

   * `"version": "0.1.0"` → `"version": "0.2.0"`
   * Añade `"monitorizacion": true`.
3. **equipo.md** – Sustituye `- D: sin bio` por tu bio en una línea.
4. **Fusiona tu rama a `main`** con `--no-ff`. Si hay conflicto, resuélvelo **conservando la versión más alta**, todas las nuevas claves y el array de características **sin duplicados**.

---

## Normas de resolución de conflictos (obligatorias)

Cuando surja conflicto en **README.md** (líneas Estado y Lema):

1. **Estado** final en `main`: `Estado: listo para revisión`
2. **Lema** final en `main`: `Lema: _Iterar y mejorar_`

Cuando surja conflicto en **config/app.json**:

* Deben **convivir todas las claves nuevas** aportadas por cualquiera (p. ej., `entorno`, `monitorizacion`).
* La **versión** debe ser la **más alta** propuesta.
* El **puerto** final debe ser **8080**.
* El **modo** final debe ser **"produccion"**.
* Ordena las **claves del JSON alfabéticamente** y el array `caracteristicas` sin duplicados y ordenado.

## Resultado esperado (estado final de `main`)

* `README.md` con:

  * `Estado: listo para revisión`
  * `Lema: _Iterar y mejorar_`
  * Actualiza los contadores a **líneas totales > 0** y **colaboradores: 4**.
* `config/app.json` con:

  * Todas las claves combinadas (`version` más alta, `modo: "produccion"`, `puerto: 8080`, `entorno`, `monitorizacion`, etc.).
  * Claves ordenadas A-Z y arrays sin duplicados.
* `CHANGELOG.md` con **[0.2.0]** incorporado.
* `equipo.md` con 4 bios.
* `textos/cita.txt` con varias líneas (una por alumno).

## Qué entregar

1. **URL del repositorio**.
2. **Captura(s)** de al menos **un conflicto** y su resolución (vista diff).
3. Salida de:

   * `git log --oneline --graph --decorate --all` (en texto o captura).
   * `git shortlog -sne`.
4. Contenido final de `config/app.json` (pegado en el envío o como archivo).
5. Etiqueta nueva `v0.2.0` creada en `main`.
