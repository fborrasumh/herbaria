# HerbarIA

Aplicación web de un solo fichero para **aprender a identificar plantas con una clave dicotómica**, razonando cada decisión. Incluye la clave de 31 taxones mediterráneos de Joaquín Moreno Compañ y permite cargar la propia.

**Usar la app:** https://fborrasumh.github.io/herbaria/

## Origen de la idea

HerbarIA parte del cuaderno **«IA generativa aplicada a la identificación de especies vegetales mediterráneas»**, de **Joaquín Moreno Compañ** (Botánica, 1.º del Grado en Ciencias Ambientales): un tutor de IA que acompaña el uso de una clave dicotómica sin sustituir la observación de la planta ni la clave, que es la referencia científica. Esta app mantiene ese principio y lo convierte en una herramienta de estudio para todo el curso.

## Qué hace

- **Ficha de observación** con vocabulario controlado y fotos opcionales. La app avisa cuando una decisión de la clave contradice la propia ficha del estudiante.
- **Identificación con la clave:** en cada decisión se elige entre dos alternativas, se escribe una justificación y se indica la seguridad (seguro, dudo, al azar). Hay un mapa del árbol con el recorrido.
- **Pistas por niveles** (qué carácter mirar, glosario con esquemas y, con IA, una pregunta socrática) y **chat con el tutor**.
- **Glosario ilustrado** de más de 50 términos con esquemas generados por código, subrayados en los textos de la clave.
- **Practicar sin IA:** identificar una especie a partir de su descripción (con corrección inmediata opcional), retos de términos, especies y decisiones, y **repaso espaciado** (cajas de Leitner: 1, 3, 7, 14 y 30 días).
- **Rúbrica orientativa** con los criterios y pesos del cuaderno (uso de la clave 35 %, interpretación de caracteres 25 %, justificación 20 %, identificación final 10 %, terminología 10 %).
- **Mi progreso:** mapa de especies, términos y decisiones que más cuestan, historial; exportable e importable.
- **Profesorado:** importar la clave tal como está en el cuaderno (diccionario de Python o JSON), validarla (destinos inexistentes, nodos inalcanzables, caminos repetidos), definir una actividad, generar una **página para el alumnado** con la actividad incrustada y cargar los resultados del grupo (decisiones más falladas, CSV).
- **Salidas:** portafolio en Word, resultado en JSON con huella de integridad para el profesor.

## Cómo se usa la IA

Es **opcional** y con la clave de cada persona (OpenAI, Google Gemini o Anthropic Claude). Todo lo anterior funciona sin ella. Cuando se usa, la IA ayuda, pero **la clave decide** y el código comprueba:

- Las pistas y respuestas del tutor pasan por un filtro que elimina cualquier frase con nombres de especies, géneros o nombres comunes, o con indicaciones de qué alternativa elegir. La IA tampoco recibe la especie del ejemplar ni la ruta correcta.
- Las valoraciones de las justificaciones se verifican: los términos que la IA da por usados deben aparecer en el texto del estudiante y en el glosario.
- Los comentarios finales parten de un diagnóstico calculado por código; se eliminan las frases con especies que no están en la clave.
- Las propuestas desde una foto solo pueden usar los valores de la ficha, y el estudiante decide cuáles acepta.

## Privacidad

La ficha, las fotos, el recorrido y el progreso se guardan solo en el navegador. Si se usa la IA, se envía lo mínimo (la decisión actual de la clave, la pregunta, las justificaciones o las fotos), nunca el nombre, con un aviso previo que muestra qué sale. **Las fotos no se pueden anonimizar.**

## Límites

- La clave solo cubre sus 31 taxones: una planta que no esté en ella acabará en una especie equivocada, y la herramienta no lo detecta.
- La IA puede equivocarse; sus respuestas son apoyo y no una autoridad taxonómica.
- Los nombres comunes, las etiquetas de caracteres de cada alternativa y las definiciones del glosario están pendientes de revisión por el autor de la clave. Los esquemas son didácticos, no láminas botánicas.
- La nota orientativa no sustituye a la calificación del profesorado. En la página para el alumnado, la especie de referencia viaja dentro del fichero: úsalo como entrenamiento y evaluación formativa, no como examen sin supervisión.

## Autoría

Fernando Borrás Rocher y Joaquín Moreno Compañ, ambos de la Universidad Miguel Hernández de Elche.

ORCID: Fernando Borrás Rocher [0000-0002-5519-4573](https://orcid.org/0000-0002-5519-4573) · Joaquín Moreno Compañ [0000-0002-5483-3417](https://orcid.org/0000-0002-5483-3417)

## Cómo citar

Borrás Rocher, F. y Moreno Compañ, J. (2026). *HerbarIA* (v1.0.0) [Software]. (DOI en trámite)

## Licencia

MIT. Véase [LICENSE](LICENSE).
