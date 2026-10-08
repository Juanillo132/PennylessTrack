# PennyLessTrack

## Descripción

**PennyLessTrack** es una aplicación web para la gestión y el seguimiento de gastos personales. Su objetivo es ofrecer una forma sencilla, rápida y organizada de registrar los gastos del día a día y consultar cómo se distribuye el dinero.

La aplicación permite almacenar los gastos indicando información como el concepto, la cantidad, la categoría y la fecha. Los datos registrados pueden consultarse posteriormente para tener una visión general de los gastos realizados.

## Objetivo del proyecto

El objetivo principal de PennyLessTrack es facilitar la gestión de las finanzas personales mediante una aplicación sencilla e intuitiva.

La aplicación permite:

* Registrar nuevos gastos.
* Consultar los gastos registrados.
* Editar gastos existentes.
* Eliminar gastos.
* Clasificar los gastos por categorías.
* Consultar la cantidad gastada.
* Llevar un seguimiento de los gastos personales.
* Mantener la información organizada.

De esta forma, PennyLessTrack ayuda al usuario a conocer mejor sus hábitos de consumo y a tener un mayor control sobre sus finanzas.

## Tecnologías utilizadas

El proyecto está desarrollado utilizando las siguientes tecnologías:

* **Node.js** — Entorno de ejecución para JavaScript.
* **Express.js** — Framework utilizado para crear el servidor y gestionar las rutas de la aplicación.
* **SQLite** — Base de datos utilizada para almacenar los gastos.
* **HTML5** — Estructura de las páginas.
* **CSS3** — Estilos y diseño de la interfaz.
* **JavaScript** — Lógica de la aplicación e interacción con el usuario.
* **Git** — Control de versiones.

## Requisitos

Para ejecutar PennyLessTrack es necesario tener instalado:

* Node.js 18 o superior.
* npm 9 o superior.
* Git.

No es necesario instalar SQLite de forma independiente, ya que la aplicación utiliza una base de datos SQLite gestionada desde Node.js.

Para comprobar que Node.js y npm están instalados correctamente:


```bash
node --version
npm --version
```

## Instalación

### 1. Clonar el repositorio

Clonar el repositorio utilizando Git:

```bash
git clone https://github.com/usuario/PennyLessTrack.git
```

Acceder al directorio del proyecto:

```bash
cd PennyLessTrack
```

### 2. Instalar las dependencias

Instalar las dependencias 

```bash
npm install
```

Este comando instalará todos los paquetes necesarios definidos en `package.json`.

### 3. Configuración

PennyLessTrack utiliza SQLite como sistema de almacenamiento.

Al iniciar la aplicación por primera vez se crea automáticamente la base de datos:

```text
data/pennylesstrack.db
```

No es necesario crear manualmente las tablas de la base de datos

Si se necesita configurar el puerto del servidor, se puede utilizar un archivo `.env`:

```env
PORT=3000
```

Si no se especifica ningún puerto, la aplicación utilizará el puerto `3000` por defecto

> El archivo `.env` no debe contener información sensible cuando el proyecto se publique en un repositorio público.

## Ejecución

Para iniciar la aplicación en modo desarrollo:

```bash
npm run dev
```

Si el proyecto no dispone de un script de desarrollo, también puede iniciarse directamente mediante:

```bash
npm start
```

Una vez iniciado el servidor, abrir un navegador y acceder a:

```text
http://localhost:3000
```

La aplicación estará disponible desde esa dirección.

## Uso de la aplicación

### Registrar un gasto

Para registrar un nuevo gasto:

1. Acceder a PennyLessTrack.
2. Seleccionar la opción para añadir un gasto.
3. Introducir el concepto del gasto.
4. Introducir la cantidad.
5. Seleccionar una categoría.
6. Indicar la fecha.
7. Guardar el gasto.

Una vez guardado, el gasto aparecerá en el listado de gastos.

### Consultar gastos

Desde la pantalla principal se pueden consultar los gastos registrados.

Cada gasto muestra información como:

* Concepto.
* Cantidad.
* Categoría.
* Fecha.

La información permite revisar rápidamente los gastos realizados.

### Editar un gasto

Para modificar un gasto:

1. Localizar el gasto en el listado.
2. Seleccionar la opción de edición.
3. Modificar los datos necesarios.
4. Guardar los cambios.

Los cambios se almacenarán automáticamente en la base de datos.

### Eliminar un gasto

Para eliminar un gasto:

1. Localizar el gasto que se desea eliminar.
2. Seleccionar la opción de eliminar.
3. Confirmar la operación.

Una vez eliminado, el gasto dejará de aparecer en el listado.

## Categorías

Los gastos pueden clasificarse utilizando diferentes categorías para facilitar su organización.

Las categorías disponibles inicialmente son:

* Alimentación.
* Transporte.
* Vivienda.
* Ocio.
* Compras.
* Salud.
* Educación.
* Suscripciones.
* Otros.

La clasificación permite identificar de forma sencilla en qué áreas se concentra el gasto.

## Estructura del proyecto

La estructura principal del proyecto es la siguiente:

```text
PennyLessTrack/
│
├── public/
│   ├── css/
│   │   └── styles.css
│   ├── js/
│   │   └── app.js
│   └── index.html
│
├── routes/
│   └── expenses.js
│
├── database/
│   ├── database.js
│   └── init.js
│
├── data/
│   └── pennylesstrack.db
│
├── app.js
├── package.json
├── package-lock.json
├── .env
├── .gitignore
└── README.md
```

### Descripción de las carpetas

#### `public/`

Contiene los archivos utilizados por la interfaz de usuario.

Incluye:

* HTML.
* CSS.
* JavaScript del cliente.
* Recursos estáticos.

#### `routes/`

Contiene las rutas utilizadas por el servidor para gestionar las diferentes operaciones de la aplicación.

Por ejemplo:

* Crear gastos.
* Consultar gastos.
* Actualizar gastos.
* Eliminar gastos.

#### `database/`

Contiene la configuración y lógica relacionada con la base de datos SQLite.

#### `data/`

Contiene el archivo de la base de datos utilizada por la aplicación.

#### `app.js`

Es el punto de entrada de la aplicación. Se encarga de configurar Express, registrar las rutas y poner en funcionamiento el servidor.

#### `package.json`

Contiene la información del proyecto, sus dependencias y los scripts disponibles.

## Dependencias

Las principales dependencias utilizadas por el proyecto son:

* **express** — Framework para crear el servidor web.
* **sqlite3** — Conector para trabajar con SQLite.
* **dotenv** — Gestión de variables de entorno.
* **cors** — Gestión de peticiones entre diferentes orígenes.

Las dependencias se instalan automáticamente mediante:

```bash
npm install
```

## Scripts disponibles

Los principales scripts del proyecto son:

```bash
npm start
```

Inicia la aplicación en modo producción.

```bash
npm run dev
```

Inicia la aplicación en modo desarrollo utilizando Nodemon para reiniciar automáticamente el servidor cuando se detectan cambios.

```bash
npm test
```

Ejecuta las pruebas automatizadas del proyecto.

## Base de datos

PennyLessTrack utiliza **SQLite** para almacenar la información de los gastos.

La tabla principal utilizada por la aplicación es `expenses`.

Su estructura contiene los siguientes campos:

| Campo         | Tipo     | Descripción                    |
| ------------- | -------- | ------------------------------ |
| `id`          | INTEGER  | Identificador único del gasto  |
| `description` | TEXT     | Descripción del gasto          |
| `amount`      | REAL     | Cantidad gastada               |
| `category`    | TEXT     | Categoría del gasto            |
| `date`        | TEXT     | Fecha del gasto                |
| `created_at`  | DATETIME | Fecha de creación del registro |

El identificador `id` se genera automáticamente para cada gasto.

## API

La aplicación dispone de una API REST para gestionar los gastos.

### Obtener todos los gastos

```http
GET /api/expenses
```

Devuelve todos los gastos registrados.

### Obtener un gasto

```http
GET /api/expenses/:id
```

Devuelve la información correspondiente al gasto indicado.

### Crear un gasto

```http
POST /api/expenses
```

Ejemplo de petición:

```json
{
  "description": "Compra supermercado",
  "amount": 45.50,
  "category": "Alimentación",
  "date": "2026-10-07"
}
```

### Actualizar un gasto

```http
PUT /api/expenses/:id
```

Permite modificar la información de un gasto existente.

### Eliminar un gasto

```http
DELETE /api/expenses/:id
```

Elimina el gasto indicado.

## Validación de datos

La aplicación realiza validaciones básicas antes de guardar los gastos.

La cantidad:

* Debe ser numérica.
* Debe ser mayor que cero.

La descripción:

* No puede estar vacía.
* Debe contener información válida sobre el gasto.

La categoría:

* Debe corresponder a una de las categorías disponibles.

La fecha:

* Debe tener un formato válido.

Estas validaciones evitan almacenar información incorrecta en la base de datos.

## Seguridad:

PennyLessTrack sigue algunas medidas básicas de seguridad:

* Las variables de configuración se almacenan mediante variables de entorno.
* Los datos recibidos por la API son validados.
* No se almacenan c
