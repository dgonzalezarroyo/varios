https://dgonzalezarroyo.github.io/varios/gestion_ausencias/index.html

# Generador de Partes de Ausencia de Personal

Aplicación web desarrollada en **HTML y JavaScript**, diseñada para ejecutarse **en local**, que permite registrar, gestionar y exportar **partes de ausencia de personal**. La aplicación almacena los datos automáticamente mediante **IndexedDB**, permite la **importación y exportación en CSV/Excel** y genera **partes mensuales en PDF** con el resumen de ausencias.

---

## 📌 Funcionalidades principales

- Ejecución **100 % local** (sin servidor ni conexión a Internet).
- Registro de ausencias con:
  - Nombre de la persona ausente (seleccionado desde un menú desplegable).
  - Fecha de inicio de la ausencia.
  - Fecha de fin de la ausencia.
  - Indicador de ausencia a tiempo parcial.
  - Indicador de entrega de justificación.
- **Edición y borrado** individual de cada apunte.
- **Guardado automático** de los datos usando IndexedDB.
- **Importación y exportación** de datos en formato:
  - CSV
  - Excel (`.xlsx`)
- Generación de **partes mensuales en PDF** con la relación de ausencias del mes seleccionado.
- Carga dinámica del listado de personal desde un **archivo CSV externo**.


