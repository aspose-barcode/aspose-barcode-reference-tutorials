---
category: general
date: 2026-08-22
description: Aprende a generar códigos de barras DataMatrix en Python y a codificar
  texto en ruso usando Aspose.BarCode – guía paso a paso.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate DataMatrix barcode
- encode Russian text
language: es
lastmod: 2026-08-22
og_description: Genera un código de barras DataMatrix en Python y codifica texto en
  ruso con Aspose.BarCode. Sigue el ejemplo completo y ejecútalo al instante.
og_image_alt: Python script that generate DataMatrix barcode with encoded Russian
  text
og_title: Generar código de barras DataMatrix en Python – tutorial completo de Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  headline: How to generate DataMatrix barcode in Python with Aspose.BarCode
  type: TechArticle
- description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  name: How to generate DataMatrix barcode in Python with Aspose.BarCode
  steps:
  - name: '**ABC123** – the plain identifier.'
    text: '**ABC123** – the plain identifier.'
  - name: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
    text: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
  - name: Open the PNG file in an image viewer.
    text: Open the PNG file in an image viewer.
  - name: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
    text: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
  - name: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
    text: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
  type: HowTo
tags:
- Aspose.BarCode
- Python
- barcode generation
title: Cómo generar código de barras DataMatrix en Python con Aspose.BarCode
url: /es/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo generar un código de barras DataMatrix en Python con Aspose.BarCode

Si necesitas **generar un código de barras DataMatrix** en Python mientras **codificas texto en ruso**, esta guía muestra los pasos exactos. Verás un ejemplo completo y ejecutable que construye un codetext extendido, configura el código de barras y guarda la imagen en un solo script.

Crear códigos de barras que contengan caracteres no ASCII a menudo genera preguntas sobre juegos de caracteres y codificación de datos. Usando `ExtCodetextBuilder` de Aspose.BarCode, puedes incrustar de forma segura texto UTF‑8 como caracteres cirílicos dentro de un símbolo DataMatrix. El resultado funciona con cualquier escáner que soporte el estándar DataMatrix.

En este tutorial aprenderás a:

* Instalar el paquete necesario de Aspose.BarCode.
* Construir un codetext extendido que mezcle datos simples y texto en ruso.
* **Generar un código de barras DataMatrix** con la cadena extendida.
* Ajustar parámetros del código de barras como el tamaño del módulo.
* Guardar el código de barras como archivo PNG.

No se requieren servicios externos; todo se ejecuta localmente en tu máquina.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* Python 3.8 o superior instalado.
* Una licencia activa de Aspose.BarCode para Python (una prueba gratuita funciona para desarrollo).
* Familiaridad básica con la escritura de scripts en Python.

Puedes instalar la biblioteca Aspose.BarCode vía pip:

```bash
pip install aspose-barcode
```

## Paso 1: Construir una cadena de codetext extendido

La primera tarea es crear una única cadena que contenga tanto el identificador de producto simple como la frase en ruso. `ExtCodetextBuilder` te permite concatenar diferentes partes de codetext mientras preserva su información de codificación.

```python
# Import required Aspose.BarCode classes
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

# Initialize the extended codetext builder
builder = ExtCodetextBuilder()

# Add a plain ASCII identifier – this could be a SKU, part number, etc.
builder.add_plain_codetext("ABC123")

# Add Russian text using ECI (Extended Channel Interpretation) encoding.
# The eci_encoding value 3 corresponds to UTF‑8.
builder.add_eci_codetext(eci_encoding=3, codetext="Привет")

# Retrieve the combined string that Aspose.BarCode will use.
extended_text = builder.get_extended_codetext()
print("Generated extended codetext:", extended_text)
```

**Por qué este paso es importante** – Los símbolos DataMatrix almacenan bytes crudos. Cuando necesitas mezclar alfabetos, debes indicar al codificador qué juego de caracteres se aplica a cada segmento. El método `add_eci_codetext` inserta un indicador ECI antes del texto ruso, asegurando que los escáneres interpreten los bytes como UTF‑8. Sin ECI, los caracteres cirílicos aparecerían como datos corruptos.

## Paso 2: Crear un generador de código de barras DataMatrix

Con el codetext extendido listo, instancia un `BarcodeGenerator` especificando el tipo `EncodeTypes.DATA_MATRIX`.

```python
# Create a DataMatrix barcode generator using the extended codetext
generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)
```

**¿Por qué DataMatrix?** – DataMatrix es un código de barras bidimensional que puede almacenar hasta 2 335 caracteres alfanuméricos o 1 556 bytes. Es ideal para artículos pequeños, piezas industriales y situaciones donde necesitas incrustar texto multilingüe.

## Paso 3: (Opcional) Configurar parámetros del código de barras

Aspose.BarCode expone muchos parámetros. Para la mayoría de los casos, la configuración predeterminada produce un símbolo legible. Sin embargo, puede que quieras controlar el tamaño de cada módulo (el cuadrado más pequeño de la matriz) para que coincida con los requisitos de impresión.

```python
# Set the module (pixel) size to 2.5 points – adjust as needed for your printer DPI
generator.parameters.barcode.x_dimension = 2.5
```

Otros parámetros útiles incluyen el nivel de corrección de errores, margen y color de fondo. Ajústalos solo si tu entorno de escaneo objetivo requiere tolerancias específicas.

## Paso 4: Guardar la imagen del código de barras

Finalmente, escribe el código de barras en un archivo. El método `save` admite PNG, JPEG, BMP y varios formatos vectoriales.

```python
# Save the barcode image to the desired folder
output_path = "YOUR_DIRECTORY/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

Al abrir `extended_codetext.png`, verás un símbolo DataMatrix nítido. Escanearlo con un lector estándar de DataMatrix devuelve las dos partes:

1. **ABC123** – el identificador simple.
2. **Привет** – el saludo en ruso, decodificado correctamente como UTF‑8.

## Ejemplo completo y ejecutable

A continuación tienes el script completo que puedes copiar‑pegar en un archivo llamado `generate_datamatrix.py`. Sustituye `YOUR_DIRECTORY` por una carpeta existente en tu sistema.

```python
# generate_datamatrix.py
# -------------------------------------------------
# Complete example: generate DataMatrix barcode and encode Russian text
# -------------------------------------------------

import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

def main():
    # Step 1: Build extended codetext
    builder = ExtCodetextBuilder()
    builder.add_plain_codetext("ABC123")
    builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_text = builder.get_extended_codetext()
    print("Generated extended codetext:", extended_text)

    # Step 2: Create DataMatrix generator
    generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)

    # Step 3: Optional parameters (adjust module size if needed)
    generator.parameters.barcode.x_dimension = 2.5

    # Step 4: Save the image
    output_path = "YOUR_DIRECTORY/extended_codetext.png"
    generator.save(output_path)
    print(f"Barcode saved as {output_path}")

if __name__ == "__main__":
    main()
```

Ejecuta el script desde la línea de comandos:

```bash
python generate_datamatrix.py
```

Deberías ver una salida en consola similar a:

```
Generated extended codetext: (ECI:3)ПриветABC123
Barcode saved as YOUR_DIRECTORY/extended_codetext.png
```

## Verificando el resultado

Para confirmar que el código de barras codifica correctamente la frase en ruso:

1. Abre el archivo PNG en un visor de imágenes.
2. Usa cualquier aplicación de escaneo DataMatrix (muchas apps móviles lo soportan) o un escáner hardware.
3. La cadena decodificada debería mostrar `ABC123Привет` (o las dos partes separadas según la UI del escáner).

Si los caracteres rusos aparecen como basura, verifica que el escáner soporte ECI UTF‑8. La mayoría de los lectores modernos lo hacen, pero dispositivos heredados pueden requerir configuración explícita.

## Problemas comunes y cómo evitarlos

| Problema | Causa | Solución |
|----------|-------|----------|
| Salida cirílica corrupta | Indicador ECI ausente | Usa `add_eci_codetext` con `eci_encoding=3`. |
| Código de barras demasiado pequeño para la impresora | Tamaño de módulo predeterminado demasiado fino para DPI bajo | Incrementa `x_dimension` (p. ej., `3.0` o `4.0`). |
| Archivo no guardado | Ruta de directorio inválida | Asegúrate de que `YOUR_DIRECTORY` exista y tenga permisos de escritura. |
| El escáner no puede leer | Densidad de datos excesiva | Reduce la cantidad de datos codificados o aumenta el nivel de corrección de errores (`generator.parameters.barcode.error_correction_level`). |

## Extender el ejemplo

Puedes adaptar este patrón para otros idiomas o tipos de datos:

* **Codificar texto japonés o árabe** – cambia `eci_encoding` al valor correspondiente (p. ej., 5 para ISO‑8859‑5, 6 para ISO‑8859‑7).  
* **Agregar varios segmentos ECI** – llama a `add_eci_codetext` varias veces, cada una con su propia codificación.  
* **Crear un código QR en su lugar** – reemplaza `EncodeTypes.DATA_MATRIX` por `EncodeTypes.QR`.  

Todos los demás pasos permanecen idénticos porque `ExtCodetextBuilder` abstrae el manejo de bytes de bajo nivel.

## Conclusión

Ahora sabes cómo **generar un código de barras DataMatrix** en Python y **codificar texto en ruso** usando la función de codetext extendido de Aspose.BarCode. El script completo maneja la negociación del juego de caracteres, la creación del código de barras y la salida de imagen con solo unas pocas líneas de código.

A continuación, explora otras simbologías de códigos de barras (PDF417, Aztec) o integra el generador en un servicio web que devuelva imágenes PNG bajo demanda. Los mismos principios—construir un codetext extendido y seleccionar el `EncodeTypes` apropiado—se aplican a toda la suite de Aspose.BarCode.

¡Feliz codificación y disfruta del poder de la generación multilingüe de códigos de barras!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo generar códigos de barras DataMatrix usando Aspose.BarCode para .NET – Guía paso a paso](/barcode/english/net/datamatrix-barcode-configuration/)
- [Generar un código de barras DataMatrix en modo ASCII con Aspose.BarCode para .NET (C#)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Cómo generar códigos de barras DataMatrix (ECC 200) con Aspose.BarCode para .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}