# LlanquihueTourApp

## Descripción
Aplicación de consola en Java que carga tours turísticos desde un archivo de texto, los muestra en pantalla, los filtra por precio máximo y los busca por el nombre del operador.

Es la continuación del proyecto de la semana 4. En esta versión se agregaron las clases Guia y Operador, y se relacionaron con Tour mediante composición.

## Estructura del proyecto
El código está organizado en tres paquetes dentro de `src`:

- `model`: clases del modelo de datos
  - `Operador`: empresa que ofrece el tour (nombre, ubicación y número)
  - `Guia`: guía del tour (nombre y número). Tiene un Operador
  - `Tour`: tour turístico (nombre, ciudad y precio). Tiene un Guia
- `service`
  - `GestorDatos`: lee el archivo de texto y crea la lista de tours
- `app`
  - `Main`: clase principal que ejecuta el programa

Un Tour tiene un Guia, y el Guia tiene un Operador.

Todas las clases del modelo tienen atributos privados, constructor, getters y setters, toString() y validación básica de datos: el precio no puede ser negativo y los nombres del guía y del operador no pueden estar vacíos.

## Formato del archivo de datos
Los tours se cargan desde `resources/tours.txt`. Cada línea tiene 8 campos separados por `;`:

```
nombre;ciudad;precio;guiaNombre;guiaNumero;operadorNombre;operadorUbicacion;operadorNumero
```

Ejemplo:

```
Navegación Lago Llanquihue;Puerto Varas;55000;Mateo Soto;+56981234567;Sur Austral Tours;Llanquihue;+56971112233
```

Las líneas con cantidad de campos incorrecta, precio que no sea un número o datos que no pasen la validación se omiten y el programa muestra un aviso.

## Cómo ejecutar
1. Tener instalado el JDK y NetBeans.
2. Clonar o descargar este repositorio.
3. Abrir la carpeta del proyecto en NetBeans.
4. Verificar que la carpeta `resources` esté en la raíz del proyecto, junto a `src`.
5. Ejecutar la clase `app.Main`.
6. El programa pide un precio máximo (por ejemplo 50000) y luego un nombre de operador (por ejemplo Andes).

## Autor
Joaquín Muñoz Riquelme, Duoc UC
