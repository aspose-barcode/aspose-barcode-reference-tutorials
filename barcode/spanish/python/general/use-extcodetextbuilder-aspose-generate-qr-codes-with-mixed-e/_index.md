---
category: general
date: 2026-07-18
description: Utiliza ExtCodeTextBuilder de Aspose para crear códigos QR que combinan
  texto ASCII simple y texto ruso en UTF‑8. Aprende la generación de códigos QR con
  Aspose.Barcode en Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- use extcodetextbuilder aspose
- Aspose.Barcode
- ECI encoding
- QR Code generation
- mixed codetext
language: es
lastmod: 2026-07-18
og_description: Usar extcodetextbuilder de Aspose le permite combinar fragmentos simples
  y codificados en UTF‑8 en un código QR. Siga esta guía paso a paso para Aspose.Barcode
  en Python.
og_image_alt: use extcodetextbuilder aspose QR code example showing mixed ECI text
og_title: usar extcodetextbuilder aspose – Generar códigos QR con texto ECI mixto
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  headline: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  type: TechArticle
- description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  name: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  steps:
  - name: What if my scanner doesn’t recognize the Cyrillic part?
    text: Make sure the scanning app advertises ECI support. Older hardware may ignore
      the ECI segment and treat the bytes as ISO‑8859‑1, resulting in garbled characters.
  - name: Can I add more than two fragments?
    text: Absolutely. Call `add_plain_codetext` or `add_eci_codetext` as many times
      as you need. The builder will concatenate them in the order you invoke the methods.
  - name: How do I change the QR Code size or foreground color?
    text: 'Use the `qr_generator.parameters` object:'
  - name: Is there a way to embed binary data (e.g., a small file) alongside text?
    text: Yes. Use `add_binary_codetext` with a byte array, and pair it with an appropriate
      ECI if the binary represents a specific character set. The builder will handle
      the necessary mode switches.
  type: HowTo
tags:
- barcode
- Aspose
- Python
- QR Code
- ECI
title: 'usar extcodetextbuilder aspose: generar códigos QR con texto ECI mixto'
url: /es/python/general/use-extcodetextbuilder-aspose-generate-qr-codes-with-mixed-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# use extcodetextbuilder aspose – Construir códigos QR con texto ECI mixto

¿Alguna vez te has preguntado cómo **usar extcodetextbuilder aspose** para incrustar tanto caracteres en inglés plano como caracteres cirílicos en un solo código QR? No estás solo. Muchos desarrolladores se topan con un obstáculo cuando necesitan mezclar datos ASCII y no‑ASCII, especialmente cuando el escáner de destino espera marcadores ECI (Extended Channel Interpretation) correctos.  

En este tutorial recorreremos paso a paso los pasos exactos para crear un código QR que contenga “HELLO123” **y** la palabra rusa “Привет”, todo con la API de Python de Aspose.Barcode. Al final tendrás un script listo‑para‑ejecutar, comprenderás por qué cada llamada es importante y sabrás cómo ajustar el proceso para otros idiomas o formatos de datos.

## Lo que aprenderás

- Cómo **inicializar ExtCodetextBuilder** y agregar fragmentos simples y codificados en ECI.  
- Por qué el valor de **codificación ECI** `3` corresponde a UTF‑8 y cómo afecta al escaneo.  
- La secuencia exacta para configurar un **generador de código QR** con Aspose.Barcode.  
- Cómo guardar la imagen resultante y verificar el contenido mixto.  

**Prerequisites** – necesitas Python 3.8+, el paquete `aspose-barcode` instalado (`pip install aspose-barcode`), y una carpeta donde puedas escribir imágenes. Nada más.

---

## usar extcodetextbuilder aspose para construir texto de código mixto

Lo primero que necesitamos es una instancia de `ExtCodetextBuilder`. Piensa en ella como un patrón builder que concatena diferentes fragmentos de texto mientras inserta automáticamente los marcadores ECI correctos detrás de escena.

```python
# Step 1: Build an extended codetext that mixes plain and ECI‑encoded fragments
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

# Create the builder object
ext_builder = ExtCodetextBuilder()

# Add plain ASCII text – this part needs no special handling
ext_builder.add_plain_codetext("HELLO123")                     # Plain ASCII text

# Add UTF‑8 encoded Russian text – ECI value 3 signals UTF‑8 to the scanner
ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")  # UTF‑8 encoded Russian text

# Retrieve the combined string that Aspose.Barcode will consume
extended_codetext = ext_builder.get_extended_codetext()
```

**Por qué esto es importante:**  
- `add_plain_codetext` mantiene los datos tal cual, lo que es perfecto para números o letras en inglés.  
- `add_eci_codetext` inserta un segmento ECI (`[ECI:3]`) antes de la cadena suministrada, indicando a cualquier lector compatible que los bytes siguientes son UTF‑8. Sin esto, el escáner interpretaría los bytes cirílicos como basura.

> **Pro tip:** Si necesitas un conjunto de caracteres diferente, cambia el valor `eci_encoding` según la tabla ECI (p. ej., `26` para ISO‑8859‑1).  

---

## Inicializar generación de código QR con Aspose.Barcode

Ahora que tenemos un `extended_codetext` correctamente formateado, podemos pasarlo al generador de código QR. Aspose.Barcode abstrae la creación de la matriz QR de bajo nivel, permitiéndote centrarte en los datos.

```python
# Step 2: Initialise a QR Code generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)   # Choose QR as the symbology
```

**¿Qué está sucediendo aquí?**  
- `BarcodeGenerator()` crea un nuevo objeto generador con la configuración predeterminada (tamaño, resolución, etc.).  
- `set_symbology` indica al motor que queremos un código QR en lugar de, por ejemplo, Code128.  

Si necesitas un nivel de corrección de errores más alto, puedes llamar a `qr_generator.parameters.barcode.qr_error_level = ...` antes de asignar el texto del código.

---

## Asignar el texto de código extendido al generador QR

Con el generador listo, el siguiente paso es simplemente proporcionar la cadena mixta que construimos antes.

```python
# Step 3: Assign the extended codetext to the generator
qr_generator.set_extended_codetext(extended_codetext)
```

**¿Por qué no usar `set_codetext`?**  
`set_codetext` trata la entrada como texto plano, eliminando cualquier marcador ECI. `set_extended_codetext` conserva los bytes crudos, incluido el segmento ECI, asegurando que el escáner vea el cambio de idioma correcto.

---

## Guardar la imagen del código QR y verificar el resultado

Finalmente, escribimos el código QR en disco. Aspose.Barcode admite PNG, JPEG, BMP y más; PNG es una opción segura porque preserva los datos sin pérdida.

```python
# Step 4: Save the generated QR Code image
qr_generator.save("YOUR_DIRECTORY/qr_extended.png")
```

Ahora deberías tener un archivo PNG en la ubicación especificada. Ábrelo con cualquier aplicación escáner de QR que admita ECI (la mayoría de los smartphones modernos lo hacen). Escanéalo una vez – verás “HELLO123”. Escanéalo de nuevo (o usa un escáner que muestre datos crudos) – también obtendrás “Привет”. Las dos partes aparecen como una sola carga útil, exactamente como la construimos.

![ejemplo de código QR con extcodetextbuilder aspose](YOUR_DIRECTORY/qr_extended.png)

*Texto alternativo de la imagen: ejemplo de código QR con extcodetextbuilder aspose mostrando texto ECI mixto*

---

## Script completo, listo para ejecutar

Juntando todo, aquí tienes el programa completo que puedes copiar‑pegar en un archivo llamado `qr_mixed_eci.py`:

```python
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

def generate_mixed_eci_qr(output_path: str):
    # Build mixed codetext
    ext_builder = ExtCodetextBuilder()
    ext_builder.add_plain_codetext("HELLO123")
    ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_codetext = ext_builder.get_extended_codetext()

    # Initialise QR generator
    qr_generator = BarcodeGenerator()
    qr_generator.set_symbology(Symbology.QR)

    # Assign extended codetext
    qr_generator.set_extended_codetext(extended_codetext)

    # Save image
    qr_generator.save(output_path)
    print(f"QR Code saved to {output_path}")

if __name__ == "__main__":
    generate_mixed_eci_qr("qr_extended.png")
```

Ejecuta con:

```bash
python qr_mixed_eci.py
```

Verás un mensaje en la consola confirmando la ubicación de guardado, y el PNG aparecerá justo donde indicaste.

---

## Preguntas frecuentes y casos límite

### ¿Qué pasa si mi escáner no reconoce la parte cirílica?

Asegúrate de que la aplicación de escaneo anuncie soporte ECI. El hardware más antiguo puede ignorar el segmento ECI y tratar los bytes como ISO‑8859‑1, lo que produce caracteres distorsionados.

### ¿Puedo agregar más de dos fragmentos?

Absolutamente. Llama a `add_plain_codetext` o `add_eci_codetext` tantas veces como necesites. El builder los concatenará en el orden en que invoques los métodos.

### ¿Cómo cambio el tamaño del código QR o el color de primer plano?

Utiliza el objeto `qr_generator.parameters`:

```python
qr_generator.parameters.barcode.x_dimension = 4   # module size in points
qr_generator.parameters.barcode.qr_error_level = qr_generator.parameters.barcode.QrErrorLevel.QR_ECLEVEL_Q
qr_generator.save("qr_custom.png", BarCodeImageFormat.PNG, 300)  # 300 DPI
```

### ¿Hay una forma de incrustar datos binarios (p. ej., un archivo pequeño) junto con texto?

Sí. Usa `add_binary_codetext` con un arreglo de bytes, y emparejalo con un ECI apropiado si el binario representa un conjunto de caracteres específico. El builder gestionará los cambios de modo necesarios.

---

## Conclusión

Ahora sabes **cómo usar extcodetextbuilder aspose** para crear códigos QR que combinan sin problemas texto ASCII simple y texto ruso codificado en UTF‑8. Al aprovechar `ExtCodetextBuilder`, establecer la **codificación ECI** correcta y pasar el resultado a un **generador de código QR de Aspose.Barcode**, obtienes una única imagen conforme a los estándares que funciona en escáneres modernos.  

A partir de aquí, prueba a cambiar `eci_encoding=3` por otros identificadores de idioma, o experimenta con fragmentos simples adicionales para construir cargas útiles multilingües. También puedes explorar las opciones `BarCodeImageFormat` para generar SVG o PDF si necesitas gráficos vectoriales.  

¡Feliz codificación, y no dudes en dejar un comentario si encuentras algún problema—tu feedback ayuda a que estas guías sean aún mejores!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Generar código de barras Java - Establecer texto del código usando Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)
- [Crear código de barras aspose .net - Configuración del texto de código DataMatrix](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Codificación de texto de código Aztec con Aspose.BarCode para .NET](/barcode/english/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}