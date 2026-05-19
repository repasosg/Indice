# Portal de Repàs 5è de Primària

Portal web sencillo para preparar exámenes de **5º de Primaria** con ejercicios interactivos, corrección automática, modo de repaso de verano y seguimiento local del progreso.

Está pensado para que una niña o niño pueda usarlo desde una **tablet de unas 10 pulgadas**, con botones grandes, tarjetas visuales, iconos, mensajes motivadores y navegación sencilla.

## Qué incluye

El proyecto funciona como una colección de páginas HTML independientes enlazadas desde `index.html`.

### Página principal

Archivo principal:

```text
index.html
```

Incluye:

- Portal de selección de ejercicios.
- Bloque destacado de **Proper examen**.
- Acceso por asignaturas.
- Acceso al **Mode Vacances d'Estiu**.
- Sección común **🏆 El meu progrés**.
- Asistente/chatbot local de recomendación de ejercicios.

### Mode Vacances d'Estiu

Archivo:

```text
mode_vacances_estiu.html
```

Modo de repaso aleatorio con ejercicios mezclados de:

- Català
- Castellà
- Matemàtiques
- Medi
- Anglès

Permite elegir:

- asignatura,
- número de preguntas,
- dificultad.

También incluye:

- barra de progreso,
- trofeos de verano,
- sonidos opcionales,
- mascota del mussol,
- guardado local de estadísticas.

### Examen destacado de Català

Archivo:

```text
catala_pb_td_cg_polisemia_descriptius.html
```

Repaso interactivo de:

- P/B, T/D y C/G a final de palabra,
- excepciones ortográficas,
- palabras primitivas y derivadas,
- familias de palabras,
- palabras polisémicas,
- partes del texto descriptivo.

Incluye:

- corrección automática,
- mascota fija,
- microanimaciones,
- sonidos suaves opcionales,
- sala de trofeos,
- simulacro final.

## Estructura de archivos

```text
Indice-main/
├── index.html
├── mode_vacances_estiu.html
├── catala_pb_td_cg_polisemia_descriptius.html
├── castellano_invitaciones_sinonimos_laH_tecnicismo_adjetivos.html
├── castellano_z_s_CC_texto_instructivo.html
├── catalan_adjectiu_noticia_s_sorda_sonora.html
├── catalan_determinantes_V_B_comic.html
├── catalan_plural_singular_tipusnoms_concret_abstracte_indivudual_article.html
├── catalan_verbs.html
├── ingles_presentsimple_continuos.html
├── mates_decimales_sumas_conversiones_multiplicaciones_divisiones.html
├── mates_diciembre.html
├── mates_fracciones_media_rango.html
├── mates_sumas_y_restas_rapidas.html
├── Mates_primer_examen_segundo_trimestre.html
├── medi_activitat_politica_recursos.html
├── repas_ciencies.html
└── README.md
```

## Cómo usarlo en local

1. Descarga o clona el repositorio.
2. Abre `index.html` con un navegador moderno.
3. Desde la página principal, entra en la misión o asignatura que quieras repasar.

No requiere instalación, servidor ni base de datos.

## Cómo publicarlo en GitHub Pages

1. Crea un repositorio en GitHub.
2. Sube todos los archivos del proyecto.
3. Ve a:

```text
Settings → Pages
```

4. En **Build and deployment**, selecciona:

```text
Deploy from a branch
```

5. Selecciona la rama principal, normalmente:

```text
main / root
```

6. Guarda los cambios.
7. GitHub generará una URL pública para el portal.

La página de entrada será:

```text
index.html
```

## Guardado del progreso

El portal usa `localStorage` del navegador.

Esto significa que el progreso:

- se guarda en la misma tablet, ordenador y navegador,
- no necesita cuenta de usuario,
- no se sube a internet,
- no se comparte con terceros.

Limitaciones:

- Si se borra la caché o los datos del navegador, se pierde el progreso.
- Si se abre desde otro dispositivo, el progreso no aparece.
- No hay sincronización con Gmail, Google Drive ni base de datos externa.

### Datos guardados actualmente

La página principal lee los datos de:

```text
catala_pb_td_cg_trofeus
portal_estiu_stats
```

Con eso construye la sección común:

```text
🏆 El meu progrés
```

Ahí se muestra:

- número total de trofeos,
- partidas del modo verano,
- mejor puntuación,
- insignias globales activadas.

## Privacidad

El portal no recoge datos personales.

No hay login, cookies de seguimiento ni conexión a una base de datos externa. El progreso se guarda únicamente en el navegador mediante `localStorage`.

Si se publica en GitHub Pages, cualquier persona con el enlace podrá ver y usar las páginas, pero no podrá acceder al progreso local de otro dispositivo.

## Cómo añadir un nuevo examen

1. Crea una nueva página HTML, por ejemplo:

```text
catala_nou_tema.html
```

2. Añade un enlace en `index.html` dentro de la asignatura correspondiente:

```html
<a href="catala_nou_tema.html" class="lbtn">Nuevo tema</a>
```

3. Si quieres que aparezca como próximo examen, cambia el bloque principal de `index.html`:

```html
<section class="banner">
  ...
</section>
```

4. Si el nuevo examen tiene trofeos y quieres que aparezcan en el progreso global, añade una nueva clave de `localStorage` y actualiza la función `readGlobalProgress()` en `index.html`.

## Recomendaciones de uso

Para estudiar sin saturar:

- 10 minutos de **Mode Vacances** al día.
- 1 misión específica cuando haya examen próximo.
- Repetir solo los ejercicios fallados.
- Usar los trofeos como motivación, no como presión.

## Tecnologías usadas

- HTML
- CSS
- JavaScript puro
- `localStorage` para progreso local

No usa frameworks ni dependencias externas obligatorias. La página principal carga una fuente de Google Fonts para mejorar la estética, pero el portal sigue siendo funcional aunque esa fuente no cargue.

## Estado del proyecto

Proyecto familiar/educativo en evolución.

Ideas futuras posibles:

- exportar/importar progreso,
- añadir más asignaturas,
- añadir más preguntas al modo verano,
- sincronización opcional con Firebase,
- perfiles para varios niños,
- estadísticas por asignatura.
