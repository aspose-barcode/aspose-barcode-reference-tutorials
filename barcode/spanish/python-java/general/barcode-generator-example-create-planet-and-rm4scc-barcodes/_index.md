---
category: general
date: 2026-10-24
description: Ejemplo de generador de códigos de barras que muestra cómo crear un código
  de barras Planet y cómo establecer la altura del código de barras usando Python.
  Sigue la guía paso a paso.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to create planet barcode
- how to set barcode height
language: es
lastmod: 2026-10-24
og_description: Ejemplo de generador de códigos de barras que muestra cómo crear un
  código de barras Planet y cómo establecer la altura del código de barras en Python.
  Obtén una solución completa y ejecutable.
og_image_alt: Barcode generator example showing Planet and RM4SCC barcodes with different
  heights
og_title: Ejemplo de generador de códigos de barras – crear códigos de barras Planet
  y RM4SCC
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  headline: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  type: TechArticle
- description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  name: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  steps:
  - name: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
    text: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
  - name: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
    text: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
  - name: '**Save** the image to disk in PNG format.'
    text: '**Save** the image to disk in PNG format.'
  type: HowTo
tags:
- barcode
- Python
- image generation
title: Ejemplo de generador de códigos de barras – crear códigos de barras Planet
  y RM4SCC con altura personalizada
url: /es/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ejemplo de generador de códigos de barras – crear códigos Planet y RM4SCC con altura personalizada

Si buscas un **ejemplo de generador de códigos de barras**, esta guía te ofrece una solución completa y lista para ejecutar. Verás **cómo crear imágenes de código de barras Planet**, aprenderás **cómo establecer la altura del código de barras** y comprenderás las pequeñas diferencias entre el dimensionado automático y el manual.

El tutorial recorre dos escenarios realistas: un código Planet que usa la altura predeterminada (automática) y un código RM4SCC donde la altura se fuerza a 100 px. Al final podrás generar archivos PNG para cualquier tipo de código de barras soportado con una API única y consistente.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* Python 3.8 o superior instalado.
* El paquete `aspose-barcode` (o cualquier biblioteca que proporcione `BarcodeGenerator`, `EncodeTypes` y `BarCodeImageFormat`). Instálalo con  

  ```bash
  pip install aspose-barcode
  ```
* Permiso de escritura en una carpeta donde se guardarán los archivos PNG.

No se requieren dependencias del sistema adicionales.

## Visión general de la solución

El núcleo del **ejemplo de generador de códigos de barras** consta de tres pasos reutilizables:

1. **Instanciar** un `BarcodeGenerator` con el valor deseado de `EncodeTypes` y la cadena de datos.
2. **Configurar** la dimensión X (ancho del módulo) y, cuando sea necesario, la altura del código de barras.
3. **Guardar** la imagen en disco en formato PNG.

Ambos ejemplos comparten los pasos 1 y 3; solo el paso 2 difiere porque el código Planet depende del cálculo automático de altura de la biblioteca, mientras que el código RM4SCC muestra **cómo establecer la altura del código de barras** manualmente.

A continuación se muestra un diagrama de alto nivel que ilustra el flujo:

![Barcode generator example showing Planet and RM4SCC barcodes](barcode-example.png)

*Alt text: Ejemplo de generador de códigos de barras que muestra códigos Planet y RM4SCC con diferentes alturas.*

## Cómo crear un código Planet – altura automática

El código Planet forma parte de la familia postal utilizada por muchos servicios postales nacionales. En la mayoría de los casos dejas que el SDK decida la altura, lo que mantiene las proporciones visuales correctas para distintas longitudes de datos.

```python
# Step 1: Create a generator for the Planet barcode with the data "123456"
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

planet_gen = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Define the X‑dimension (module width) as 4 pixels
planet_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Save the barcode image as a PNG file
planet_gen.save("PostalPlanetBarHeightAuto.png", BarCodeImageFormat.Png)
```

**Por qué funciona**

* `EncodeTypes.Planet` indica a la biblioteca que use la simbología Planet.
* Establecer `x_dimension.pixels` a 4 asigna a cada módulo un ancho de 4 px, que es un valor predeterminado común para etiquetas impresas.
* No se establece una altura explícita; el SDK calcula la altura óptima basándose en los datos y la dimensión X, por lo que este es el **ejemplo de generador de códigos de barras** más sencillo para códigos postales.

**Resultado esperado**

Un archivo PNG 2‑D llamado `PostalPlanetBarHeightAuto.png` que contiene un código Planet nítido. La altura será alrededor de 30 px (según la versión de la biblioteca) y el ancho será 4 px × número de módulos.

## Cómo establecer la altura del código de barras – ejemplo RM4SCC personalizado

RM4SCC es otro código postal que a menudo requiere una altura fija para coincidir con plantillas de etiquetas. Esta parte del tutorial muestra **cómo establecer la altura del código de barras** a un recuento exacto de píxeles.

```python
# Step 1: Create a generator for the RM4SCC barcode with the data "123456"
rm4scc_gen = BarcodeGenerator(EncodeTypes.RM4SCC, "123456")

# Step 2: Set the X‑dimension to 4 pixels (same as the Planet example)
rm4scc_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Specify the barcode height as 100 pixels
rm4scc_gen.parameters.barcode.bar_height.pixels = 100

# Step 4: Save the barcode image as a PNG file
rm4scc_gen.save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png)
```

**Por qué funciona**

* `EncodeTypes.RM4SCC` selecciona la simbología RM4SCC.
* La dimensión X se mantiene en 4 px para conservar el tamaño del módulo consistente entre ambos códigos.
* `bar_height.pixels = 100` obliga al código de barras a tener exactamente 100 px de altura, sobrescribiendo el cálculo automático. Esta es la forma recomendada de **cómo establecer la altura del código de barras** cuando tu diseño exige un tamaño específico.

**Resultado esperado**

Un archivo PNG llamado `PostalRM4SCCBarHeight100Pixels.png` que muestra un código RM4SCC alto. El ancho sigue determinado por la dimensión X, mientras que la altura está fija en 100 px, lo que lo hace adecuado para impresoras de etiquetas de alta resolución.

## Script completo – combinar ambos ejemplos

Si prefieres un único script que genere ambas imágenes, copia el siguiente código en `generate_barcodes.py` y ejecútalo.

```python
"""
Full barcode generator example that creates:
* a Planet barcode with automatic height
* an RM4SCC barcode with a custom 100 px height
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_planet_barcode(data: str, x_dim: int, out_path: str):
    """Generate a Planet barcode using the default height."""
    gen = BarcodeGenerator(EncodeTypes.Planet, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.save(out_path, BarCodeImageFormat.Png)

def create_rm4scc_barcode(data: str, x_dim: int, height_px: int, out_path: str):
    """Generate an RM4SCC barcode with a fixed height."""
    gen = BarcodeGenerator(EncodeTypes.RM4SCC, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.parameters.barcode.bar_height.pixels = height_px
    gen.save(out_path, BarCodeImageFormat.Png)

if __name__ == "__main__":
    # Planet barcode – auto height
    create_planet_barcode(
        data="123456",
        x_dim=4,
        out_path="PostalPlanetBarHeightAuto.png"
    )

    # RM4SCC barcode – custom 100 px height
    create_rm4scc_barcode(
        data="123456",
        x_dim=4,
        height_px=100,
        out_path="PostalRM4SCCBarHeight100Pixels.png"
    )
```

**Explicación del script**

* Dos funciones auxiliares mantienen el código DRY (Don’t Repeat Yourself) y facilitan la ampliación del script a otras simbologías.
* La guarda `if __name__ == "__main__":` permite que el archivo se importe como módulo sin ejecutar la lógica de generación, lo cual es útil para pruebas unitarias.
* Todos los parámetros (cadena de datos, dimensión X, altura) son explícitos, de modo que el script sirve como referencia de **ejemplo de generador de códigos de barras** para proyectos futuros.

## Preguntas frecuentes y casos límite

| Pregunta | Respuesta |
|----------|-----------|
| *¿Qué pasa si necesito una dimensión X diferente?* | Cambia `x_dimension.pixels` al ancho de módulo deseado. Valores mayores aumentan el tamaño total del código de barras proporcionalmente. |
| *¿Puedo generar otros formatos de imagen?* | Sí. Reemplaza `BarCodeImageFormat.Png` por `Jpg`, `Bmp` o `Gif` según el enum de la biblioteca. |
| *¿Qué ocurre si la cadena de datos contiene caracteres no válidos?* | El generador lanza una `ArgumentException`. Valida los datos contra el conjunto de caracteres de la simbología antes de llamar al constructor. |
| *¿Es posible establecer una altura mínima manteniendo el escalado automático?* | Usa `gen.parameters.barcode.bar_height.min_pixels = <valor>` (si el SDK expone una propiedad `min_pixels`). Esto evita que el código de barras se reduzca por debajo de un tamaño legible. |
| *¿Necesito disponer del generador?* | La clase `BarcodeGenerator` implementa `IDisposable` en .NET; en Python el recolector de basura lo gestiona, pero puedes llamar a `gen.dispose()` si creas muchas instancias dentro de un bucle. |

## Consejos para uso en producción

* **Pro tip:** Almacena los valores de dimensión X y altura en un archivo de configuración para poder ajustarlos sin recompilar.
* **Cuidado con:** Usar una altura demasiado pequeña para la simbología seleccionada; los escáneres pueden no leer el código de barras.
* **Nota de rendimiento:** Generar un lote grande de códigos de barras es más rápido cuando reutilizas una única instancia de `BarcodeGenerator` y solo cambias su propiedad `code_text` entre guardados.

## Conclusión

Este **ejemplo de generador de códigos de barras** muestra tanto **cómo crear imágenes de código Planet** con dimensionado automático como **cómo establecer la altura del código de barras** manualmente para códigos RM4SCC. Siguiendo la guía paso a paso podrás integrar la creación de códigos de barras en cualquier aplicación Python, personalizar dimensiones y producir archivos PNG listos para impresión o visualización digital.

### Próximos pasos

* Explora simbologías adicionales como `EncodeTypes.Postnet` o `EncodeTypes.Code128` – se aplica el mismo patrón.
* Experimenta con **cómo establecer la altura del código de barras** para códigos QR o símbolos DataMatrix; la mayoría de las bibliotecas exponen una propiedad `bar_height` similar.
* Combina el generador con una biblioteca PDF para incrustar códigos de barras directamente en facturas o etiquetas de envío.

¡Siéntete libre de adaptar el script, compartir tus resultados y hacernos saber qué tipos de códigos de barras agregarás a continuación!


## ¿Qué deberías aprender a continuación?


Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [How to save PNG from a barcode generator example in Python](/barcode/english/python-java/general/how-to-save-png-from-a-barcode-generator-example-in-python/)
- [How to create planet barcode PNG with Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [How to use a C# barcode generator to create a Planet barcode](/barcode/english/python-java/general/how-to-use-a-c-barcode-generator-to-create-a-planet-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}