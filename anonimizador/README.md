https://dgonzalezarroyo.github.io/varios/anonimizador/index.html

# Anonimizador y desanonimizador de textos

Aplicación web local para sustituir nombres de personas por códigos y códigos por sus nombres, usando una tabla de correspondencias en CSV. El resultado previsto es un único archivo `index.html` autónomo: se abre en el navegador y permite trabajar con los archivos sin instalar software ni configurar un servidor.

## Características previstas

- Carga una tabla de correspondencias en formato CSV y un texto de entrada en formato TXT.
- Reemplaza en una sola operación nombres por códigos y códigos por nombres, incluso cuando ambos tipos aparecen en el mismo texto.
- Prioriza las coincidencias más largas para reducir sustituciones parciales cuando un nombre está contenido en otro.
- Considera los límites de palabra al buscar coincidencias, para evitar reemplazar una cadena solo porque aparece dentro de otra palabra.
- Advierte sobre duplicados o correspondencias ambiguas que podrían producir resultados inciertos.
- Conserva el texto que no coincide y, en la medida prevista, sus saltos de línea y formato.
- Ofrece una vista previa del resultado y controles para descargarlo y restablecer la interfaz.
- Procesa los datos localmente en el navegador, conforme a la especificación de privacidad descrita abajo.

## Cómo usar

1. Abre `index.html` con un navegador moderno.
2. Selecciona el CSV con las correspondencias.
3. Selecciona o carga el archivo TXT que quieres transformar.
4. Revisa las advertencias que muestre la aplicación, en particular las relativas a datos duplicados o ambiguos.
5. Genera y revisa la vista previa del resultado.
6. Descarga el TXT resultante si es correcto. Usa la opción de restablecer para iniciar otro proceso.

Los nombres y códigos se intercambian en ambos sentidos durante el mismo procesamiento. Por ello, revisa el resultado y la tabla si un nombre también coincide con un código, o si hay entradas que se solapan.

## Formato del CSV

El CSV debe incluir una fila de encabezados y una columna para el nombre y otra para el código. Se prevé admitir UTF-8 con o sin BOM, y separador coma o punto y coma. Los encabezados y las filas deben ser coherentes entre sí.

Ejemplo con comas:

```csv
nombre,codigo
Juan Pérez García,alumno01
María López Sánchez,alumno02
Pedro Fernández Ruiz,alumno03
```

Ejemplo con punto y coma:

```csv
nombre;codigo
Juan Pérez García;alumno01
María López Sánchez;alumno02
Pedro Fernández Ruiz;alumno03
```

Los nombres pueden contener varias palabras. Si los datos incluyen comas o punto y coma dentro de un campo, deben estar correctamente entrecomillados según las reglas del CSV y la aplicación debe admitir ese caso para que pueda interpretarse sin ambigüedad. No uses nombres o códigos repetidos salvo que la aplicación documente cómo resuelve esa situación.

## Privacidad

La aplicación está especificada para procesar el CSV y el texto directamente en el navegador, sin servidor, conexión a Internet ni dependencias externas. Según ese diseño, los archivos no necesitan enviarse a un servicio remoto para transformarse.

Esta descripción se basa en la especificación y no en una auditoría del código. Antes de usar datos personales o sensibles, verifica que el `index.html` realmente no realice solicitudes de red ni guarde los datos fuera del navegador. Mantén el CSV de correspondencias bajo acceso controlado: contiene la relación que permite revertir la anonimización.

## Ejecución local

No se prevé instalación ni compilación. Descarga o clona el repositorio y abre `index.html` directamente en el navegador. La aplicación debe funcionar sin servidor local y sin conexión a Internet, de acuerdo con la especificación.

## Notas y limitaciones

- La sustitución solo puede reconocer los nombres y códigos que estén incluidos en el CSV.
- Las coincidencias parciales, los límites de palabra y la selección de la coincidencia más larga deben seguir las reglas concretas de `index.html`; revisa la vista previa antes de guardar el resultado.
- Los duplicados, valores vacíos, códigos que también aparezcan como nombres y otras correspondencias conflictivas pueden ser ambiguos. Atiende las advertencias y corrige la tabla cuando sea necesario.
- La conservación de espacios, saltos de línea y otros detalles depende de la implementación. Comprueba el TXT descargado si el formato exacto es importante.
- Esta herramienta realiza reemplazos de texto; no garantiza anonimización irreversible ni elimina otros datos identificativos presentes en el documento.
- Los formatos indicados son CSV para la tabla y TXT para el texto de entrada y salida.

## Estructura esperada

```text
.
└── index.html   # Aplicación web autónoma
```
