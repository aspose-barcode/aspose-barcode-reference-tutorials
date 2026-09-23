---
category: general
date: 2026-08-12
description: Crea un databar omnidireccional con Python y aprende cómo generar una
  imagen de código de barras en Python usando Aspose.BarCode. Sigue la guía paso a
  paso para obtener una solución completa.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni directional databar
- create barcode image python
language: es
lastmod: 2026-08-12
og_description: Crea un databar omnidireccional con Python y genera una imagen de
  código de barras en minutos. Este tutorial muestra un ejemplo completo y ejecutable.
og_image_alt: example of create omni directional databar barcode image in Python
og_title: Crea una barra de datos omnidireccional – guía completa de Python
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create omni directional databar with Python and learn how to create
    barcode image python using Aspose.BarCode. Follow the step‑by‑step guide for a
    complete solution.
  headline: Create omni directional databar and barcode image in Python
  type: TechArticle
tags:
- barcode
- Python
- Aspose
- DataBar
title: Crear una imagen de databar omnidireccional y código de barras en Python
url: /es/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear databar omnidireccional e imagen de código de barras en Python

Si necesitas **crear databar omnidireccional** en un proyecto Python, esta guía te muestra cómo hacerlo y también cómo **crear imagen de código de barras python** usando la biblioteca Aspose.BarCode. Obtendrás un script listo‑para‑ejecutar que produce dos archivos PNG con diferentes relaciones de aspecto.

Generar un DataBar que siga la especificación omnidireccional es un requisito común para aplicaciones de retail y logística. El tutorial cubre la instalación, configuración de la dimensión X, ajuste de la relación de aspecto y guardado de las imágenes finales. No se requieren servicios externos; todo se ejecuta localmente.

## Lo que necesitarás

Antes de comenzar, asegúrate de tener:

* Python 3.8 o superior instalado en tu máquina.
* Acceso a una terminal o símbolo del sistema.
* Permiso de escritura en una carpeta donde se guardarán las imágenes del código de barras.

La única dependencia de terceros es **Aspose.BarCode for Python via .NET**, que soporta el tipo DataBar omnidireccional de forma nativa.

## Paso 1: Instalar Aspose.BarCode para Python

Aspose.BarCode proporciona la clase `BarcodeGenerator` usada en el código de ejemplo. Instala el paquete con `pip`:

```bash
pip install aspose-barcode
```

El paquete incluye los enlaces necesarios al runtime de .NET, por lo que no necesitas instalar el SDK de .NET por separado.

## Paso 2: Importar la biblioteca y crear el generador

La primera línea del script crea un generador para un DataBar omnidireccional apilado. El valor GTIN‑14 `(01)12345678901231` se usa como dato de muestra.

```python
# Step 2: Import classes and create the generator
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a stacked Omni‑directional DataBar with the required data
barcode_generator = BarcodeGenerator(
    EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
    "(01)12345678901231"
)
```

*Por qué este paso es importante*: La constante `EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL` indica a la biblioteca que codifique el valor como un DataBar omnidireccional, que es el formato requerido por muchos escáneres de punto de venta.

## Paso 3: Establecer la dimensión X (ancho del módulo)

La dimensión X define el ancho del módulo de barra más pequeño. Un valor de `2` píxeles produce un código de barras claro y legible sin un tamaño de archivo excesivo.

```python
# Step 3: Set the basic X‑dimension (width of the smallest module) in pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 2
```

*Por qué este paso es importante*: Ajustar la dimensión X te permite equilibrar la legibilidad y las dimensiones de la imagen. Una dimensión X demasiado pequeña puede renderizarse pobremente en impresoras de baja resolución.

## Paso 4: Configurar la relación de aspecto y guardar la primera imagen

La relación de aspecto influye en la altura total del DataBar respecto a su ancho. Una relación de aspecto de `15` crea un estilo visual compacto.

```python
# Step 4: Configure an aspect ratio of 15 and save the first image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 15
barcode_generator.save("output/StackedAR15.png", BarCodeImageFormat.Png)
```

> **Consejo profesional**: Usa `pathlib.Path` para construir la ruta de salida, lo que crea automáticamente los directorios faltantes.

```python
from pathlib import Path

output_dir = Path("output")
output_dir.mkdir(parents=True, exist_ok=True)
barcode_generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)
```

## Paso 5: Cambiar la relación de aspecto para un segundo estilo visual y guardar otra imagen

Cambiar la relación de aspecto a `30` produce un código de barras más alto que puede ser requerido por hardware de escáner específico.

```python
# Step 5: Change the aspect ratio to 30 and save the second image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 30
barcode_generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)
```

*Por qué este paso es importante*: Diferentes minoristas y dispositivos de escaneo tienen restricciones de tamaño distintas. Proveer ambas relaciones de aspecto en un solo script te permite generar el estilo exacto que necesitas sin duplicar código.

## Script completo – crear databar omnidireccional e imagen de código de barras python

A continuación se muestra el ejemplo completo y ejecutable que incorpora todos los pasos anteriores. Guárdalo como `generate_databar.py` y ejecútalo con `python generate_databar.py`.

```python
#!/usr/bin/env python3
"""
Complete example that creates an omni directional databar
and demonstrates how to create barcode image python using Aspose.BarCode.
"""

# Import required classes
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from pathlib import Path

def main():
    # Define output directory and ensure it exists
    output_dir = Path("output")
    output_dir.mkdir(parents=True, exist_ok=True)

    # Initialize the generator with Omni‑directional DataBar data
    generator = BarcodeGenerator(
        EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
        "(01)12345678901231"
    )

    # Set X‑dimension to 2 pixels for good readability
    generator.parameters.barcode.x_dimension.pixels = 2

    # First visual style – aspect ratio 15
    generator.parameters.barcode.data_bar.aspect_ratio = 15
    generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)

    # Second visual style – aspect ratio 30
    generator.parameters.barcode.data_bar.aspect_ratio = 30
    generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)

    print(f"Images saved to: {output_dir.resolve()}")

if __name__ == "__main__":
    main()
```

### Salida esperada

Ejecutar el script crea los siguientes archivos:

```
output/StackedAR15.png   # DataBar with aspect ratio 15
output/StackedAR30.png   # DataBar with aspect ratio 30
```

Ambas imágenes muestran un DataBar omnidireccional válido que puede ser escaneado por equipos de retail estándar.

![ejemplo de crear databar omnidireccional imagen de código de barras en Python](example_databar.png "crear databar omnidireccional imagen de código de barras python")

*La imagen anterior es un marcador de posición que ilustra los dos archivos PNG guardados.*

## Resolución de problemas comunes

| Problema | Razón | Solución |
|----------|-------|----------|
| `ImportError: No module named aspose` | Aspose.BarCode no está instalado o está instalado en un entorno diferente. | Activa el entorno virtual correcto y ejecuta `pip install aspose-barcode`. |
| `PermissionError` al guardar | El script no tiene permiso de escritura para la carpeta de destino. | Elige un directorio que poseas o ejecuta el script con los privilegios adecuados. |
| El código de barras no se escanea | Dimensión X demasiado baja o relación de aspecto incompatible con el escáner. | Aumenta `x_dimension.pixels` a 3 o 4, y prueba diferentes valores de `aspect_ratio` (p. ej., 20, 25). |
| Falta runtime de .NET | Aspose.BarCode depende del runtime de .NET en Windows/Linux. | Instala el runtime más reciente de .NET desde el sitio de Microsoft; la documentación del paquete brinda guías específicas por plataforma. |

## Extender el ejemplo

Puedes adaptar el script para generar otras variantes de DataBar (p. ej., `DATABAR_STACKED`, `DATABAR_EXPANDED`). Reemplaza la constante `EncodeTypes` según corresponda:

```python
generator = BarcodeGenerator(EncodeTypes.DATABAR_EXPANDED, "(01)12345678901231")
```

Si necesitas incrustar el código de barras en un PDF, Aspose.PDF para Python puede importar directamente el archivo PNG o puedes usar el método `save` con `BarCodeImageFormat.Pdf`.

## Conclusión

Este tutorial mostró cómo **crear databar omnidireccional** y cómo **crear imagen de código de barras python** usando Aspose.BarCode. Ahora dispones de un script completo y reproducible que genera dos archivos PNG con diferentes relaciones de aspecto, maneja problemas comunes y puede ampliarse a otros formatos de código de barras.

A continuación, explora la generación de códigos QR, la incorporación del código de barras en facturas PDF o la automatización del procesamiento por lotes para catálogos de productos extensos. Cada uno de esos temas se basa en el mismo patrón `BarcodeGenerator` demostrado aquí. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to create barcode image and render it in Java](/barcode/english/java/barcode-rendering-techniques/rendering-barcode-image-instance/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}