---
category: general
date: 2026-11-20
description: Aprende a usar ECI, generar QR a partir de texto, limpiar el constructor
  y guardar la imagen QR usando la biblioteca de códigos de barras de Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use eci
- generate qr from text
- how to clear builder
- save qr image
- clear qr builder
language: es
lastmod: 2026-11-20
og_description: Cómo usar ECI para generar QR a partir de texto, limpiar el generador
  de QR y guardar la imagen QR – una guía completa paso a paso.
og_image_alt: Diagram illustrating how to use ECI to generate a QR code and save the
  QR image
og_title: Cómo usar ECI en la generación de códigos QR con Python
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to use ECI, generate QR from text, clear the builder, and
    save QR image using the Python barcode library.
  headline: How to use ECI in QR code generation with Python
  type: TechArticle
tags:
- QR code
- Python
- barcode
- ECI
title: Cómo usar ECI en la generación de códigos QR con Python
url: /es/python/general/how-to-use-eci-in-qr-code-generation-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo usar ECI en la generación de códigos QR con Python

Si necesitas **how to use eci** al crear códigos QR, esta guía muestra los pasos exactos. Verás cómo generar QR a partir de texto, limpiar el generador y, finalmente, guardar la imagen QR, todo con unas pocas líneas de Python.

Los códigos QR que contienen datos multilingües a menudo requieren un segmento Extended Channel Interpretation (ECI) para que los escáneres sepan qué conjunto de caracteres aplicar. Este tutorial te guía en la construcción de un codetext extendido, limpiar el generador al reutilizarlo y guardar el resultado como un archivo PNG.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

- Python 3.8+ instalado.
- El paquete Aspose.BarCode for Python via .NET (o cualquier biblioteca `barcode` compatible que proporcione `ExtCodetextBuilder` y `BarcodeGenerator`).
- Familiaridad básica con los conceptos de códigos QR.

Instala la biblioteca con pip:

```bash
pip install aspose-barcode
```

> **Consejo profesional:** Usa un entorno virtual para evitar conflictos de versiones.

## Paso 1: Importar las clases requeridas

Las clases principales con las que trabajarás son `ExtCodetextBuilder` para construir codetext extendido y `BarcodeGenerator` para renderizar el código QR.

```python
from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
```

Estas importaciones te dan acceso a los métodos del constructor (`add_plain_codetext`, `add_eci_codetext`, etc.) y a las funciones `set_code_text`, `set_symbology` y `save` del generador.

## Paso 2: Crear y configurar el ExtCodetextBuilder

Crear una nueva instancia del constructor es el primer ejemplo concreto de **how to use eci**. También puedes limpiar el constructor más tarde si necesitas reutilizarlo.

```python
# Create an ExtCodetextBuilder instance
extended_text_builder = ExtCodetextBuilder()

# Optional: clear any previous items (useful when reusing the same builder)
extended_text_builder.clear()   # this demonstrates how to clear builder
```

Llamar a `clear()` asegura que el constructor comience con un estado limpio, lo cual es esencial al generar múltiples códigos QR en un bucle.

## Paso 3: Añadir codetext plano (sin ECI)

El texto plano no necesita un segmento ECI. Usa `add_plain_codetext` para cadenas compatibles con ASCII.

```python
# Add plain codetext (e.g., an English phrase)
extended_text_builder.add_plain_codetext("HelloWorld")
```

El constructor ahora contiene el segmento plano `"HelloWorld"`.

## Paso 4: Añadir un segmento codificado con ECI

Aquí está el núcleo de **how to use eci**: especificas el valor ECI (26 para UTF‑8) y proporcionas la cadena Unicode que deseas codificar. Esto permite que el código QR contenga ruso, chino o cualquier otro idioma que no esté cubierto por el conjunto predeterminado ISO‑8859‑1.

```python
# Add ECI‑encoded codetext (ECI value 26 = UTF‑8, Russian “Hello”)
extended_text_builder.add_eci_codetext(26, "Привет")
```

> **Por qué es importante:** Sin el indicador ECI, un escáner interpretaría los bytes usando el conjunto de caracteres predeterminado y mostraría caracteres distorsionados para texto no ASCII.

## Paso 5: Recuperar la cadena de codetext extendido combinada

Después de añadir todos los segmentos requeridos, obtén la cadena final que se pasará al generador QR.

```python
combined_extended_text = extended_text_builder.get_extended_codetext()
print("Extended codetext:", combined_extended_text)
```

El valor impreso se ve algo así:

```
Extended codetext: [ECI26]ПриветHelloWorld
```

El formato exacto depende de la biblioteca, pero lo importante es que el marcador ECI (`[ECI26]`) precede a la carga UTF‑8.

## Paso 6: Generar el código QR usando el texto combinado

Ahora puedes **generate QR from text** pasando el codetext extendido a `BarcodeGenerator`.

```python
# Initialize the QR generator
qr_generator = barcode.generation.BarcodeGenerator()

# Assign the combined extended codetext
qr_generator.set_code_text(combined_extended_text)

# Choose QR symbology (the library supports many, QR is the most common)
qr_generator.set_symbology(barcode.Symbology.QR)

# Save the QR image to disk – this demonstrates how to save QR image
output_path = "qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Cuando abras `qr_extended.png`, aparecerá un código QR que codifica tanto la cadena en inglés plana como el saludo en ruso. Escanearlo con un escáner QR moderno mostrará correctamente “HelloWorld” y “Привет”.

### Por qué deberías llamar a `clear()` antes de reutilizar el constructor

Si generas múltiples códigos QR en un bucle, olvidar limpiar el constructor concatenará segmentos antiguos con nuevos, produciendo un código inválido. Aquí tienes un patrón rápido:

```python
for text, eci, unicode_str in data_set:
    extended_text_builder.clear()                       # ensures a fresh start
    extended_text_builder.add_plain_codetext(text)
    extended_text_builder.add_eci_codetext(eci, unicode_str)
    qr_generator.set_code_text(extended_text_builder.get_extended_codetext())
    qr_generator.save(f"qr_{text}.png")
```

Este fragmento ilustra **how to clear builder** y **how to generate QR from text** de forma repetida.

## Casos límite y errores comunes

| Situación | Qué observar | Cómo manejar |
|-----------|--------------|--------------|
| **Valor ECI no soportado** | La biblioteca lanza `InvalidArgumentException`. | Usa solo los valores ECI listados en la especificación (p.ej., 26 para UTF‑8, 20 para Shift‑JIS). |
| **Texto combinado muy largo** | La versión QR puede exceder la capacidad máxima. | Incrementa la versión QR automáticamente (`qr_generator.set_qr_version(QRVersion.AUTO)`) o divide los datos en varios códigos QR. |
| **Errores de permisos del sistema de archivos** | `save` falla con `IOError`. | Asegúrate de que el directorio de destino exista y el proceso tenga permiso de escritura. |
| **Visualización incorrecta del conjunto de caracteres** | El escáner muestra caracteres distorsionados. | Verifica que el valor ECI correcto coincida con la codificación real de la cadena. |

## Ejemplo completo ejecutable

A continuación hay un script autónomo que puedes copiar, pegar y ejecutar. Incluye todas las importaciones, manejo de errores y comentarios para mayor claridad.

```python
# qr_eci_example.py
# Demonstrates how to use ECI, generate QR from text, clear the builder,
# and save QR image using Aspose.BarCode for Python.

from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
import os

def generate_qr(plain_text: str, eci_value: int, unicode_text: str, out_file: str):
    """
    Creates a QR code that contains both plain and ECI‑encoded text.
    Parameters:
        plain_text – ASCII‑compatible string.
        eci_value  – Numeric ECI identifier (e.g., 26 for UTF‑8).
        unicode_text – Text that requires the specified ECI.
        out_file – Destination file path for the PNG image.
    """
    # Step 1: instantiate and clear the builder
    builder = ExtCodetextBuilder()
    builder.clear()                       # how to clear builder

    # Step 2: add segments
    builder.add_plain_codetext(plain_text)
    builder.add_eci_codetext(eci_value, unicode_text)

    # Step 3: retrieve combined text
    combined = builder.get_extended_codetext()
    print("Combined extended codetext:", combined)

    # Step 4: generate QR code
    generator = barcode.generation.BarcodeGenerator()
    generator.set_code_text(combined)
    generator.set_symbology(barcode.Symbology.QR)

    # Ensure output directory exists
    os.makedirs(os.path.dirname(out_file), exist_ok=True)

    # Step 5: save QR image – how to save QR image
    generator.save(out_file)
    print(f"QR code saved as {out_file}")

if __name__ == "__main__":
    # Example usage
    generate_qr(
        plain_text="HelloWorld",
        eci_value=26,               # UTF‑8
        unicode_text="Привет",      # Russian "Hello"
        out_file="output/qr_extended.png"
    )
```

Ejecutar este script produce `output/qr_extended.png`, un código QR que codifica correctamente tanto texto en inglés como en ruso.

## Conclusión

Ahora sabes **how to use eci** al crear códigos QR, cómo **clear the QR builder** antes de reutilizarlo, cómo **generate QR from text**, y los pasos exactos para **save QR image** con Python. Siguiendo el patrón anterior, puedes incrustar cualquier cadena Unicode en un código QR manteniendo el estado del constructor predecible.

### ¿Qué sigue?

- Explora otros valores ECI para idiomas como chino (ECI 20) o ISO‑8859‑5.
- Ajusta los niveles de corrección de errores (`qr_generator.set_error_correction_level`) para mejorar la fiabilidad del escaneo.
- Combina múltiples segmentos ECI en un solo QR para mensajes multilingües.

¡Feliz codificación y disfruta creando códigos QR multilingües!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo generar código de barras con ECI usando Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)
- [Cómo generar imagen de código QR en Python con Aspose.Barcode – Guía completa](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Cómo generar código de barras en Python – guía completa paso a paso](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}