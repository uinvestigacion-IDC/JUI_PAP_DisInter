# Generador del Plan del TAP · Diseño de Interiores · IDC

Aplicación web de un solo archivo (`index.html`) que genera en formato Word (.docx) el borrador del Plan del Trabajo de Aplicación Profesional (TAP) del Programa de Estudios de Diseño de Interiores del Instituto de Educación Superior Público "Diseño y Comunicación" (IDC), Lima, Perú.

El contenido sigue el *Manual para el desarrollo del Trabajo de Aplicación Profesional (TAP) – Diseño de Interiores* (Jefatura de la Unidad de Investigación, IDC, 2026).

Dirección de publicación indicada en el Manual: <https://uinvestigacion-idc.github.io/JUI_PAP_DisInter/>

## Naturaleza del documento generado

El archivo .docx es un informe preliminar del Plan, no la versión definitiva. Según la Orientación preliminar del Manual, no se presenta como Plan final sin:

1. la confirmación de la Coordinación Académica del Programa, y
2. la ampliación y aprobación del docente asesor.

Los límites del generador (300 palabras en la descripción técnica, 5 referencias como mínimo) son parámetros de admisibilidad del sistema, no estándares de suficiencia académica.

## Archivos

| Archivo | Uso |
|---|---|
| `index.html` | Página completa: HTML, CSS y JavaScript en línea. |
| `Logo_IDC.png` | Logotipo del formulario y del pie de página. |
| `Logo_IDC - copia.jpg` | Logotipo del encabezado. |
| `README.md` | Este documento. |

Los dos logotipos se referencian por ruta relativa y deben estar en la misma carpeta que `index.html`.

## Dependencias externas

Se cargan desde CDN; no requieren instalación:

- Bootstrap 5.3.3 (CSS y JS), desde `cdn.jsdelivr.net`.
- Chart.js 4.4.4, desde `cdn.jsdelivr.net`.
- Google Fonts: Bricolage Grotesque, Manrope y JetBrains Mono.

La generación del .docx no usa bibliotecas externas: el archivo ZIP y el XML de Word se construyen en JavaScript dentro de `index.html`.

## Publicación

1. Copiar `index.html` y los dos logotipos en la raíz de un repositorio.
2. En GitHub: Settings → Pages → Source: rama `main`, carpeta `/ (root)`.
3. Abrir la URL que asigna GitHub Pages.

Para uso local, basta con abrir `index.html` en un navegador. La instalación como aplicación (PWA) requiere servir la página por HTTPS.

## Secciones de la página

| N.° | Sección | Fuente en el Manual |
|---|---|---|
| 01 | Presentación institucional: Plan e Informe, máximo dos egresados | Parte II, 2.1–2.2 |
| 02 | Marco normativo: 17 normas | Base legal |
| 03 | Seis líneas transversales institucionales | 1.3 |
| 04 | Estructura oficial del Informe Final | 2.3 |
| 05 | Once secciones del Plan | Parte I |
| 06 | Verbos de Bloom por nivel cognitivo | 1.5 |
| 07 | Cuatro criterios de justificación | 1.6 |
| 08 | Plan frente a Informe y gráficos de extensión | 3.1 |
| 09 | Fichas de las líneas DI-L1 a DI-L5 | 1.3, 2.5 y Parte V |
| 10 | Formato ISO 690:2021 y jerarquía de encabezados | 6.3–6.4 |
| 11 | Anexos A a J | 6.5 |
| 12 | Niveles AIAS de uso de IA generativa | Parte IV, 4.1 |
| 13 | Checklist del Plan | Parte VII, 7.1 |
| 14 | Formulario generador del Plan | Parte I |

## Formulario

| Paso | Campo | Obligatorio | Regla aplicada |
|---|---|---|---|
| 1 | Título del trabajo | Sí | Contador de 25 palabras |
| 2 | Programa, semestre o año de egreso, año de presentación | Semestre o año | Carrera bloqueada en "Diseño de Interiores" |
| 2 | Línea de investigación DI | Sí | DI-L1 a DI-L5 |
| 2 | Línea transversal | Sí | Una opción |
| 3 | Integrantes | Al menos uno | Máximo 2 (RVM N.° 049-2022-MINEDU, num. 15.2.1) |
| 3.5 | Docente asesor | Sí | — |
| 4 | Problema general y problemas específicos | General | Uno por línea |
| 5 | Objetivo general y objetivos específicos | General | Aviso si detecta verbos en pasado |
| 6 | Trascendencia, magnitud, vulnerabilidad, factibilidad | No | — |
| 7 | Descripción técnica | Sí | Contador de 300 palabras |
| 8 | Cronograma | No | Cada línea se convierte en una fila del Gantt |
| 9 | Presupuesto | No | Formato `Categoría – S/ monto`, una partida por línea |
| 10 | Referencias ISO 690:2021 | No | Contador con mínimo de 5 |
| 11 | Nivel AIAS de uso de IA | Sí | Niveles 1 a 4 |

Cada paso tiene un botón `?` que abre una ventana de diálogo (`<dialog>`) con la sección del Manual, la información que se debe ingresar, las reglas y un ejemplo. La ventana se cierra con el botón "Entendido", con la ×, con la tecla Esc o con un clic fuera del cuadro.

Botones del formulario:

- Cargar datos de DEMO: rellena el formulario con un ejemplo de la línea DI-L5.
- Generar documento en Word: valida los campos obligatorios y descarga `Plan_TAP_<línea>_<apellido>.docx`.
- Solo la Plantilla (en blanco): descarga `Plan_TAP_Diseño_Interiores_PLANTILLA_2026.docx` con textos guía en gris.
- Limpiar formulario: vacía los campos y borra el borrador guardado.

## Documento Word generado

- Portada: institución, título, programa, línea DI, línea transversal, autores, docente asesor, nivel AIAS, lugar y año.
- Nota institucional sobre el carácter preliminar del documento.
- Secciones 1 a 11 del Plan y tabla de firmas con DNI.
- Formato: Times New Roman 12 pt, interlineado 1,5, texto justificado, sangría de primera línea de 1,25 cm.
- Encabezado con el nombre de la institución y "PLAN DEL TRABAJO DE APLICACIÓN PROFESIONAL"; pie con número de página y nombre del programa.

## Almacenamiento en el navegador

| Clave de `localStorage` | Contenido |
|---|---|
| `idc_pap_di_borrador_v1` | Borrador del formulario, guardado 1 s después de cada cambio y borrado tras generar el Word. La clave conserva el prefijo `pap` para recuperar borradores de la versión anterior. |
| `idc_tap_di_checklist_v1` | Estado de las casillas del checklist de la sección 13. |

Los datos quedan solo en el navegador del usuario; la página no envía información a ningún servidor.

## Mantenimiento

Ubicación de los elementos editables dentro de `index.html`:

| Elemento | Ubicación |
|---|---|
| Textos de las ventanas de ayuda | Objeto `HELP` en el bloque "VENTANAS DE AYUDA DEL FORMULARIO" |
| Número máximo de integrantes | Constante `MAX_INTEGRANTES` |
| Campos obligatorios | Arreglo `required` en el manejador `submit` del formulario |
| Contenido del Word | Función `buildDocument(d)` |
| Datos de demostración | Función `cargarDemo()` |
| Datos de los gráficos | Bloques `chartCapitulos` y `chartCalidad` |
| Versión de caché de la PWA | Constante `CACHE_VERSION` dentro de `swCode`; se incrementa en cada publicación para que los dispositivos instalados descarguen la versión nueva |

## Recursos enlazados desde el formulario

- Bibliometría IDC: <https://uinvestigacion-idc.github.io/JUI_BiblioIA/>
- Guía institucional ISO 690, IA generativa y declaración de uso: <https://uinvestigacion-idc.github.io/JUI_Decla_IA2026/>
- Gem de consultas sobre el documento: <https://gemini.google.com/gem/1wyIeb21RSLUuvMK1C3C3ANWQqd1w4pdq?usp=sharing>

## Créditos

- Coordinación del Programa de Estudios de Diseño de Interiores: Dis. María Quintana Vera Tudela.
- Jefatura de la Unidad de Investigación: Mg. Mario Quiroz Martinez.

Instituto de Educación Superior Público "Diseño y Comunicación", Lima, Perú, 2026.
