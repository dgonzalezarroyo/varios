https://dgonzalezarroyo.github.io/varios/gestion_economica_v2/index.html 

# Gestión económica (local, IndexedDB)

Esta aplicación HTML funciona **100% en local** y guarda automáticamente en **IndexedDB** del navegador.

## Características
- Apuntes con 6 campos: fecha, descripción, cantidad (admite negativas), tipo (caja/banco), partida (funcionamiento, auxiliares, accede, 1038, seguro escolar, europa) y movimiento (ingreso/pago).
- **Traspasos** caja↔banco sin partida.
- **Saldos iniciales** para caja, banco y cada partida (las partidas no están ligadas a caja/banco).
- Suma de **saldos iniciales**: (caja+banco) y (todas las partidas).
- **Balances**: caja, banco, por partida. Suma de **balances**: (caja+banco) y (todas las partidas).
- **Historial** con filtros por tipo (caja/banco) y por partida, y búsqueda por texto.
- **Exportar/Importar** CSV por defecto; **Excel (.xlsx)** si añades la librería opcional.
- Botones para **generar PDF** por sección (usa la impresión del navegador).

## Uso
1. Descomprime el ZIP en una carpeta de tu disco.
2. Abre `index.html` con tu navegador (Chrome, Edge, Firefox o Safari).
3. Define saldos iniciales, añade apuntes (normales o traspasos), consulta balances y filtra el historial.
4. Para PDF, pulsa "Generar PDF" en la sección que te interese.

## Exportar/Importar
- **CSV**: funciona sin dependencias y es compatible con Excel.
- **Excel (.xlsx)**: descarga `xlsx.full.min.js` (SheetJS) y colócala junto a `index.html`; luego **descomenta** la línea del script en el `<head>`:
  ```html
  <!-- <script src="xlsx.full.min.js"></script> -->
  ```
  dejando:
  ```html
  <script src="xlsx.full.min.js"></script>
  ```

## Copia de seguridad
- Exporta los **apuntes** y los **saldos** a CSV/Excel para respaldo.

## Notas
- IndexedDB guarda los cambios inmediatamente; no necesitas acciones al cerrar.
- Los datos quedan asociados al navegador donde usas la aplicación.
