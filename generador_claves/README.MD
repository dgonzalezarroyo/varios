# 🔐 Generador de Claves (HTML)

Este repositorio contiene **dos versiones en HTML** de un generador de claves a partir de nombres completos, pensado para uso educativo o administrativo.
Ambas versiones funcionan **directamente en el navegador**, sin instalación ni servidor.

## 📂 Archivos incluidos

* **`Generador de Claves.html`**
  Versión original del generador.

* **`Generador de Claves v2.html`**
  Versión mejorada con generación de **dos claves por persona** (o un usuario y una contraseña, según quieras verlo).

## ✨ Funcionalidades comunes

Ambas versiones permiten:

* Cargar archivos **CSV** o **ODS**
* Leer nombres completos desde la **primera columna**
* Ignorar filas vacías y encabezados
* Generar claves automáticamente
* Descargar los resultados en un archivo **CSV**
* Funcionamiento 100 % local (los datos no salen del navegador)

## 🧩 Diferencias entre versiones

### 🔹 Generador de Claves.html (v1)

* Genera **una única clave por persona**
* La clave se compone de:

  * Nombre o apellido (seleccionado aleatoriamente)
  * 4 dígitos numéricos aleatorios
* Muestra:

  * Nombre completo
  * Parte usada (Nombre / Apellido 1 / Apellido 2)
  * Clave generada

### 🔹 Generador de Claves v2.html (v2)

* Genera **dos claves por persona** (o un usuario y una contraseña, según quieras verlo):

  1. **Clave 1** (o nombre de usuario): basada en nombre o apellido + 4 dígitos
  2. **Clave 2**: cadena aleatoria de **8 caracteres** (letras y números)
* El archivo CSV descargado contiene únicamente las claves, ideal para su distribución.

## 🚀 Cómo usar

1. Descarga el archivo HTML que quieras usar.
2. Ábrelo con cualquier navegador moderno (Chrome, Firefox, Edge…).
3. Carga un archivo **CSV** o **ODS** con los nombres en la primera columna.
4. Visualiza las claves generadas.
5. Descarga el CSV con los resultados.

## 🛠 Tecnologías utilizadas

* HTML5 + CSS3
* JavaScript (vanilla)
* [PapaParse](https://www.papaparse.com/) para CSV
* [SheetJS (XLSX)] para archivos ODS

## 📌 Notas

* No se requiere conexión a Internet una vez cargado el archivo.
* Compatible con acentos y nombres compuestos.
* Pensado para uso educativo (alumnado, listas, credenciales temporales).
