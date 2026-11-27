---
category: general
date: 2026-11-27
description: Aprende cómo ajustar la altura de las barras del código de barras en
  un generador DataBar Omni‑Directional. El código paso a paso muestra cómo establecer
  alturas de 30 px y 60 px.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- adjust barcode bar height
- DataBar Omni‑Directional barcode
- set XDimension
- barcode image format
- BarCodeImageFormat
- barcode generator python
language: es
lastmod: 2026-11-27
og_description: Ajusta la altura de las barras del código de barras en un generador
  DataBar Omni‑Directional con Python. Sigue la guía completa para establecer alturas,
  dimensión X y guardar imágenes PNG.
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode with adjusted bar height
og_title: Ajustar la altura de la barra del código de barras en el generador DataBar
  Omni‑Directional
schemas:
- author: GroupDocs
  dateModified: '2026-11-27'
  description: Learn how to adjust barcode bar height in a DataBar Omni‑Directional
    barcode generator. Step‑by‑step code shows setting heights to 30 px and 60 px.
  headline: How to adjust barcode bar height in DataBar Omni‑Directional generator
  type: TechArticle
tags:
- barcode
- python
- DataBar
- imaging
title: Cómo ajustar la altura de la barra del código de barras en el generador DataBar
  Omni‑Directional
url: /es/python-java/general/how-to-adjust-barcode-bar-height-in-databar-omni-directional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo ajustar la altura de la barra del código de barras en el generador DataBar Omni‑Directional

Si necesita **ajustar la altura de la barra del código de barras** para un código de barras DataBar Omni‑Directional, esta guía le muestra exactamente cómo. Verá un ejemplo completo y ejecutable en Python que cambia la altura de la barra de 30 px a 60 px mientras mantiene la X‑dimension y el formato de imagen consistentes.

Cambiar las dimensiones visuales de un código de barras es un requisito común cuando el código debe ajustarse a un tamaño de etiqueta o directriz de diseño específico. Además de la altura de la barra, también puede querer ajustar la **X‑dimension** (tamaño del módulo) o elegir un **formato de imagen del código de barras** diferente, como PNG o JPEG.

En este tutorial usted:

* Instalar la biblioteca requerida (GroupDocs.Barcode for Python)
* Crear un generador de código de barras DataBar Omni‑Directional
* Establecer el tamaño del módulo con `XDimension`
* Ajustar la propiedad de altura de la barra dos veces
* Guardar las imágenes resultantes en el **BarCodeImageFormat** deseado

No se necesita experiencia previa con la API de GroupDocs; solo conocimientos básicos de Python.

## Requisitos previos

Antes de comenzar, asegúrese de tener:

* Python 3.8 o superior instalado
* Paquete `groupdocs.barcode` (`pip install groupdocs-barcode`)  
* Permiso de escritura en una carpeta donde se guardarán los archivos PNG

Si no está familiarizado con el **código de barras DataBar Omni‑Directional**, este codifica un GTIN de 14 dígitos y se usa ampliamente en el comercio minorista para escanear desde cualquier orientación.

## Paso 1: Configurar el generador de código de barras DataBar Omni‑Directional

Primero, importe las clases necesarias e instancie el generador con los datos GTIN que desea codificar.

```python
from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a DataBar Omni‑Directional barcode
# The string "(01)12345678901231" follows the GS1 Application Identifier syntax
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")
```

*Por qué es importante:* La constante `EncodeTypes.DatabarOmniDirectional` indica a la biblioteca que produzca la simbología Omni‑Directional. La cadena de datos incluye el AI `(01)` que marca un valor GTIN‑14.

## Paso 2: Definir la X‑dimension (tamaño del módulo)

La X‑dimension controla el ancho de la barra más estrecha. Un valor común para la representación en pantalla es **2 px por módulo**.

```python
# Set the module (X‑dimension) size – 2 px per module
gen.parameters.barcode.x_dimension.pixels = 2
```

Usar un **set XDimension** consistente garantiza que el código de barras se escale correctamente en diferentes impresoras y escáneres.

## Paso 3: Ajustar la altura de la barra a 30 px y guardar la imagen

Ahora cambiamos la propiedad de altura de la barra. La primera altura que usaremos es **30 px**, adecuada para etiquetas pequeñas.

```python
# Define the first bar height (30 px)
gen.parameters.barcode.bar_height.pixels = 30

# Save the barcode as a PNG image
gen.save("output/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png)
```

La constante `BarCodeImageFormat.Png` selecciona el **formato de imagen del código de barras** PNG, que conserva la calidad sin pérdidas.

### Resultado esperado

El archivo `DatabarBarHeight30Pixels.png` contiene un código de barras DataBar Omni‑Directional cuyas barras miden 30 px de altura. A continuación se muestra una vista previa de marcador de posición:

![DataBar barcode with 30 px bar height](images/databar_30px.png "DataBar barcode with 30 px bar height")

> **Consejo:** Si abre el PNG en un editor de imágenes, verá la altura exacta de la barra. Las barras estrechas tienen 2 px de ancho, como se definió anteriormente.

## Paso 4: Cambiar la altura de la barra a 60 px para un código de barras más alto

Para aplicaciones que requieren una huella visual mayor —como una etiqueta de carga— puede aumentar la altura de la barra a **60 px**.

```python
# Change the bar height to 60 px for a taller barcode
gen.parameters.barcode.bar_height.pixels = 60
```

Solo cambia la propiedad `BarHeight`; la X‑dimension y la codificación permanecen iguales, por lo que el código de barras sigue siendo escaneable.

## Paso 5: Guardar la imagen del código de barras actualizado

Finalmente, escriba el código de barras más alto en un segundo archivo PNG.

```python
# Save the updated barcode image
gen.save("output/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png)
```

### Resultado esperado

El archivo `DatabarBarHeight60Pixels.png` muestra los mismos datos codificados, pero cada barra ahora mide 60 px de altura. La diferencia visual se ilustra a continuación:

![DataBar barcode with 60 px bar height](images/databar_60px.png "DataBar barcode with 60 px bar height")

## Ejemplo completo y ejecutable

Juntando todo, aquí está el script completo que puede copiar y pegar en un archivo llamado `adjust_barcode_height.py` y ejecutar directamente.

```python
# adjust_barcode_height.py
# Demonstrates how to adjust barcode bar height for a DataBar Omni‑Directional barcode

from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create the generator with GTIN data
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")

# 2️⃣ Set module size (X‑dimension) to 2 px
gen.parameters.barcode.x_dimension.pixels = 2

# 3️⃣ First bar height: 30 px
gen.parameters.barcode.bar_height.pixels = 30
gen.save(os.path.join(output_dir, "DatabarBarHeight30Pixels.png"), BarCodeImageFormat.Png)

# 4️⃣ Second bar height: 60 px
gen.parameters.barcode.bar_height.pixels = 60
gen.save(os.path.join(output_dir, "DatabarBarHeight60Pixels.png"), BarCodeImageFormat.Png)

print(f"Barcodes saved to '{output_dir}'")
```

Ejecute el script:

```bash
python adjust_barcode_height.py
```

Debería ver dos archivos PNG en la carpeta `output`, cada uno reflejando la altura de barra que estableció.

## Preguntas comunes y casos límite

| Pregunta | Respuesta |
|----------|-----------|
| **¿Puedo usar JPEG en lugar de PNG?** | Sí. Reemplace `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg`. JPEG es con pérdida, por lo que se prefiere PNG para escaneo preciso. |
| **¿Qué pasa si necesito una altura de barra que no sea múltiplo de 10?** | La propiedad `BarHeight.Pixels` acepta cualquier valor entero. Simplemente asigne la cantidad de píxeles deseada (p. ej., `45`). |
| **¿Cambiar la altura de la barra afecta los datos codificados?** | No. Solo cambia la representación visual; la cadena de datos subyacente permanece idéntica. |
| **¿Cómo cambio la X‑dimension después de guardar la primera imagen?** | Puede modificar `gen.parameters.barcode.x_dimension.pixels` en cualquier momento antes de llamar a `save()`. El cambio se aplicará a las imágenes posteriores. |
| **¿El generador es seguro para subprocesos?** | La instancia `BarcodeGenerator` no garantiza ser segura para subprocesos. Cree una instancia separada por subproceso si genera códigos de barras concurrentemente. |

## Conclusión

Ahora sabe cómo **ajustar la altura de la barra del código de barras** en un generador de código de barras DataBar Omni‑Directional usando Python. El tutorial cubrió la creación del generador, la configuración de la **X‑dimension**, la modificación de la propiedad **barcode bar height** y la guardado de imágenes en el **formato de imagen del código de barras** deseado.

A partir de aquí puede experimentar con otras alturas, diferentes tamaños de módulo, o cambiar a formatos de imagen alternativos como JPEG o BMP. También podría explorar características adicionales del **barcode generator python**, como agregar texto legible por humanos o cambiar esquemas de color.

¡Feliz codificación, y mantenga sus códigos de barras nítidos y perfectamente dimensionados!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarle a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en sus propios proyectos.

- [Cómo establecer el ancho y ajustar la altura para un código de barras GS1 DataBar Omni‑Directional](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Crear databar omnidireccional e imagen de código de barras en Python](/barcode/english/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/)
- [Generador de códigos de barras .net – cambiar la altura del código de barras](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}