---
category: general
date: 2026-09-29
description: Mostrar el nombre del producto en Python mientras se imprime la fecha
  de lanzamiento y se recuperan los detalles de la versión de la biblioteca de códigos
  de barras.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- display product name
- print release date
- how to get version
- how to print product
- show minor version
language: es
lastmod: 2026-09-29
og_description: Muestra el nombre del producto en Python y aprende a imprimir la fecha
  de lanzamiento, obtener la versión y mostrar la versión menor con unas pocas líneas
  de código.
og_image_alt: Screenshot of terminal output showing product name, version, and release
  date
og_title: Mostrar el nombre del producto y la información de versión en Python
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Display product name in Python while printing release date and retrieving
    version details from the barcode library.
  headline: Display product name and version info in Python
  type: TechArticle
tags:
- Python
- barcode library
- version information
title: Mostrar el nombre del producto y la información de versión en Python
url: /es/python/general/display-product-name-and-version-info-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mostrar el nombre del producto y la información de versión en Python

Si necesitas **mostrar el nombre del producto** de una biblioteca, esta guía te muestra exactamente cómo hacerlo. También aprenderás a **imprimir la fecha de lanzamiento**, **obtener la versión** y **mostrar la versión menor** usando código Python conciso.

Muchos desarrolladores integran funciones de escaneo o generación de códigos de barras y deben exponer los metadatos de la biblioteca a los usuarios o a los registros. Este tutorial cubre todo lo necesario para recuperar y presentar esa información de forma fiable.

## Lo que aprenderás

* Recuperar la información de versión de la biblioteca `barcode`.  
* **Mostrar el nombre del producto** junto con los números de versión mayor y menor.  
* **Imprimir la fecha de lanzamiento** en un formato legible para humanos.  
* Manejar atributos ausentes de forma elegante.  

**Prerequisitos**  
* Python 3.8 o superior.  
* Acceso al paquete `barcode` (instálalo con `pip install python-barcode` o la biblioteca que proporcione `BuildVersionInfo`).  

---

## Cómo mostrar el nombre del producto y la información de versión en Python

El primer paso es importar la biblioteca y llamar al método que devuelve un objeto de información de versión. El objeto contiene atributos como `PRODUCT`, `PRODUCT_MAJOR`, `PRODUCT_MINOR` y `RELEASE_DATE`.

```python
import barcode

def main():
    # Step 1: Retrieve version information from the barcode library
    info = barcode.BuildVersionInfo()

    # Step 2: Display product name
    print(f"Product: {info.PRODUCT}")

    # Step 3: Show major and minor version numbers
    print(f"Version: {info.PRODUCT_MAJOR}.{info.PRODUCT_MINOR}")

    # Step 4: Print release date
    print(f"Release date: {info.RELEASE_DATE}")

if __name__ == "__main__":
    main()
```

**Por qué funciona**  
`BuildVersionInfo()` devuelve un objeto ligero cuyos atributos se rellenan en tiempo de importación. Acceder a los atributos directamente evita I/O adicional y garantiza que los datos mostrados coincidan con la versión de la biblioteca que realmente está usando tu código.

### Salida esperada

```
Product: BarcodeLib
Version: 2.5
Release date: 2024-03-15
```

Los valores exactos dependen de la versión instalada de la biblioteca barcode.

---

## Cómo obtener la versión de la biblioteca barcode

Si solo necesitas los números de versión, puedes omitir la impresión del nombre del producto y centrarte en los campos numéricos.

```python
import barcode

info = barcode.BuildVersionInfo()
major = info.PRODUCT_MAJOR
minor = info.PRODUCT_MINOR

print(f"Current version: {major}.{minor}")
```

*Los atributos `PRODUCT_MAJOR` y `PRODUCT_MINOR` siguen el versionado semántico, lo que te permite comparar versiones programáticamente.*

---

## Cómo imprimir la fecha de lanzamiento

La fecha de lanzamiento se almacena como una cadena en formato `YYYY‑MM‑DD`. Para presentarla en una localidad diferente, conviértela primero a un objeto `datetime`.

```python
import barcode
from datetime import datetime

info = barcode.BuildVersionInfo()
raw_date = info.RELEASE_DATE          # e.g., "2024-03-15"
date_obj = datetime.strptime(raw_date, "%Y-%m-%d")
formatted = date_obj.strftime("%B %d, %Y")  # "March 15, 2024"

print(f"Release date: {formatted}")
```

**Consejo:** Siempre valida la cadena de fecha antes de analizarla para evitar `ValueError` cuando la biblioteca cambie su formato.

---

## Mostrar la versión menor junto a la versión mayor

A veces necesitas mostrar la versión menor por separado, por ejemplo al registrar advertencias de compatibilidad.

```python
import barcode

info = barcode.BuildVersionInfo()
print(f"Major version: {info.PRODUCT_MAJOR}")
print(f"Minor version: {info.PRODUCT_MINOR}")
```

**Pro tip:** Usa la versión menor para activar banderas de funciones:

```python
if info.PRODUCT_MINOR >= 5:
    enable_new_feature()
```

---

## Manejo de atributos ausentes (casos límite)

Versiones antiguas de la biblioteca barcode pueden no exponer todos los atributos. Envuelve el acceso a los atributos en `getattr` con valores predeterminados razonables.

```python
import barcode

info = barcode.BuildVersionInfo()

product = getattr(info, "PRODUCT", "Unknown Product")
major = getattr(info, "PRODUCT_MAJOR", 0)
minor = getattr(info, "PRODUCT_MINOR", 0)
release = getattr(info, "RELEASE_DATE", "N/A")

print(f"Product: {product}")
print(f"Version: {major}.{minor}")
print(f"Release date: {release}")
```

Este patrón asegura que tu script nunca falle por un campo faltante, haciéndolo robusto para pipelines de CI que pueden ejecutarse contra múltiples versiones de la biblioteca.

---

## Ejemplo completo y ejecutable

A continuación se muestra el script completo que combina todas las mejores prácticas: validación de atributos, formato de fecha y salida clara.

```python
import barcode
from datetime import datetime

def fetch_info():
    """Retrieve version info safely, providing defaults for missing attributes."""
    raw = barcode.BuildVersionInfo()
    return {
        "product": getattr(raw, "PRODUCT", "Unknown Product"),
        "major": getattr(raw, "PRODUCT_MAJOR", 0),
        "minor": getattr(raw, "PRODUCT_MINOR", 0),
        "release_raw": getattr(raw, "RELEASE_DATE", "N/A")
    }

def format_release(date_str):
    """Convert YYYY‑MM‑DD to a friendly format; fall back to the original string."""
    try:
        dt = datetime.strptime(date_str, "%Y-%m-%d")
        return dt.strftime("%B %d, %Y")
    except (ValueError, TypeError):
        return date_str

def main():
    info = fetch_info()

    # Display product name
    print(f"Product: {info['product']}")

    # Show major and minor version numbers
    print(f"Version: {info['major']}.{info['minor']}")

    # Print release date in a readable form
    print(f"Release date: {format_release(info['release_raw'])}")

if __name__ == "__main__":
    main()
```

Ejecutar este script en un sistema con la biblioteca barcode instalada produce una salida similar al ejemplo anterior, pero ahora protege contra campos faltantes y formatea la fecha de manera agradable.

---

## Conclusión

Ahora sabes cómo **mostrar el nombre del producto**, **imprimir la fecha de lanzamiento**, **obtener la versión**, **imprimir el producto** y **mostrar la versión menor** usando un flujo de trabajo Python sencillo. El ejemplo completo demuestra un acceso fiable a los atributos, manejo de fechas y comparación de versiones—habilidades que puedes reutilizar para cualquier biblioteca de terceros que exponga objetos de metadatos.

**Próximos pasos**

* Explora otros métodos de metadatos de la biblioteca barcode, como `BuildCommitInfo()`.  
* Integra la salida en un framework de registro (p. ej., `logging.info`).  
* Compara versiones programáticamente para imponer versiones mínimas requeridas en tu aplicación.

Siéntete libre de experimentar con diferentes formatos de salida o ampliar el script para escribir la información en un archivo con fines de auditoría. ¡Feliz codificación!  

![Terminal output showing product name and version details](image.png "Terminal output")


## ¿Qué deberías aprender a continuación?


Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [display product name using Python barcode library – step‑by‑step guide](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)
- [How to Print Version of Aspose.Barcode (Python)](/barcode/english/python/general/how-to-print-version-of-aspose-barcode-python/)
- [How to generate barcode with Aspose.BarCode in Python](/barcode/english/python-java/general/how-to-generate-barcode-with-aspose-barcode-in-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}