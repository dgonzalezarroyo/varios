https://dgonzalezarroyo.github.io/varios/gestion_economica_erasmus/index.html

# Gestión Económica — Erasmus+

Aplicación web de un solo archivo (`index.html`) para llevar el **libro de cuentas** de un proyecto Erasmus+: registrar apuntes de pago, controlar el presupuesto disponible por finalidad y exportar los datos a CSV o Excel.

Funciona **sin servidor y sin conexión a internet** una vez cargada: basta con abrir el archivo en el navegador. Los datos se guardan en el propio navegador y no se envían a ningún sitio.

## Características

- **Resumen presupuestario** con una tarjeta por finalidad: presupuesto, gastado y disponible, con barra de progreso y código de color:
  - 🟢 verde: dentro del presupuesto
  - 🟠 ámbar: se ha consumido el 85 % o más
  - 🔴 rojo: presupuesto superado (disponible negativo)
- **Alta, edición y borrado de apuntes** (descripción, cantidad en €, finalidad y fecha).
- **Historial de apuntes** con filtro por finalidad.
- **Cantidades presupuestadas** editables para cada finalidad.
- **Importación y exportación** de apuntes y presupuestos en CSV y Excel (`.xlsx`/`.xls`).
- **Informe completo** con el resumen presupuestario y el historial de apuntes.
- **Guardado automático** en el navegador (IndexedDB) cada vez que se añade, edita o elimina un dato.

## Finalidades

| Finalidad |
|---|
| Apoyo organizativo |
| Visitas preparatorias |
| Movilidad de grupos |
| Aprendizaje por observación |
| Movilidad de larga duración |

Para añadir, quitar o renombrar finalidades, edita la constante `FINALIDADES` al inicio del script del HTML.

## Uso

1. Descarga `gestion_economica_erasmus.html`.
2. Ábrelo con cualquier navegador moderno (Chrome, Firefox, Edge…).
3. En **Cantidades presupuestadas**, introduce el presupuesto de cada finalidad.
4. Registra los pagos en **Nuevo apunte**.
5. Consulta el estado de cada partida en el **Resumen presupuestario**.

> También puedes publicarla como página web con **GitHub Pages** (Settings → Pages) renombrando el archivo a `index.html`.

## Importar datos

Los archivos CSV o Excel deben incluir estas columnas:

- **Apuntes:** `Fecha`, `Descripción`, `Cantidad`, `Finalidad`
- **Presupuestos:** `Finalidad`, `Cantidad presupuestada`

El valor de `Finalidad` debe coincidir con una de las finalidades de la tabla anterior. Los importes admiten formato español (por ejemplo, `1.234,56`).

## Exportar datos

| Opción | Archivo generado |
|---|---|
| Apuntes | CSV o Excel |
| Presupuestos | CSV o Excel |
| Informe completo (Excel) | `informe_completo.xlsx` (hojas *Resumen* e *Historial*) |
| Informe completo (CSV) | `informe_resumen.csv` e `informe_historial.csv` |

## Privacidad y copia de seguridad

Los datos se almacenan **únicamente en el IndexedDB del navegador** y equipo donde se usa la aplicación. Esto implica que:

- no se comparten entre dispositivos ni entre navegadores;
- se pierden si se borran los datos del sitio o se usa una ventana privada.

Se recomienda **exportar periódicamente** una copia de seguridad en Excel o CSV.

## Dependencias

Todo está en un único archivo HTML. Se cargan desde CDN:

- [SheetJS (xlsx 0.18.5)](https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js), para importar y exportar Excel/CSV.
- [Google Fonts](https://fonts.google.com/): Fraunces, IBM Plex Sans e IBM Plex Mono (opcionales; si no cargan, se usan fuentes del sistema).

Sin conexión, las fuentes usan la alternativa del sistema y la importación/exportación depende de que SheetJS se haya podido cargar al menos una vez en caché.

## Licencia

Añade aquí la licencia que prefieras (por ejemplo, MIT).
