# Guía de instalación del etiquetador en Windows

## Requisitos previos

- **Python 3.10 o superior**
  Se descarga desde [https://www.python.org/downloads/](https://www.python.org/downloads/).
  Durante la instalación, marcá la opción **"Add Python to PATH"** antes de continuar.

- **Git** (opcional, para clonar el repositorio)
  Se descarga desde [https://git-scm.com/download/win](https://git-scm.com/download/win).

---

## Pasos de instalación

### 1. Obtener el programa

**Opción A — Con Git:**
```
git clone https://github.com/denzelurias/etiquetador_te
cd etiquetador_te
```

**Opción B — Sin Git:**
Descargue el archivo ZIP del proyecto, descomprimalo y abra la carpeta `etiquetador_te`.

---

### 2. Abrir una terminal en la carpeta del proyecto

Navegue hasta la carpeta `etiquetador_te` en el Explorador de archivos, haga clic derecho dentro de la carpeta y elija **"Abrir en Terminal"** (o **"Abrir ventana de PowerShell aquí"**).

---

### 3. Crear un entorno virtual

Ejecute el siguiente comando en terminal:

```
python -m venv venv
```

---

### 4. Activar el entorno virtual

```
venv\Scripts\activate
```

Va a ver `(venv)` al inicio de la línea de la terminal cuando esté activo.

---

### 5. Instalar las dependencias

```
pip install -r requirements.txt
```

---

### 6. Ejecutar el programa

```
python app.py
```

La terminal mostrará algo como:

```
 * Running on http://127.0.0.1:5000
```

---

### 7. Acceder a la aplicación

Abra un navegador (Chrome, Edge, etc.) y entre a:

```
http://127.0.0.1:5000
```

---

## Uso básico

1. Ingresá el **Pallet ID** en la pantalla inicial y confirmá.
2. En la pantalla de inspección, seleccioná los botones con defectos y elegí el tipo de defecto de la lista.
3. Presioná **Finalizar inspección** para guardar los registros.
4. Podés revisar el historial en la sección **Historial**.

---

## Base de datos

El programa genera automáticamente el archivo `InspeccionManual.db` (SQLite) en la misma carpeta la primera vez que se ejecuta. No es necesario ningún paso adicional.

La base de datos contiene dos tablas:

| Tabla | Descripción |
|---|---|
| `Inspecciones` | Registros de cada defecto detectado por inspección. |
| `Periodos` | Registros de cada sesión del programa (inicio y cierre). |

---

## Detener el programa

Presione `Ctrl + C` en la terminal para cerrar el servidor. El periodo de sesión quedará registrado automáticamente con su hora de cierre.

---

## Solución de problemas comunes

| Problema | Solución |
|---|---|
| `'python' no se reconoce como comando` | Reinstale Python marcando **"Add Python to PATH"**. |
| `No module named flask` | Asegurese de haber activado el entorno virtual antes de realizar (`venv\Scripts\activate`). |
| El puerto 5000 está ocupado | Cierre otras aplicaciones que usen ese puerto o cambie el puerto en la última línea de `app.py`: `app.run(port=5001)`. |
