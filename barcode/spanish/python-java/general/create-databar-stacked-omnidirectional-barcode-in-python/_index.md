---
category: general
date: 2026-07-30
description: Crea un código de barras Databar Stacked Omnidirectional en Python. Sigue
  esta guía paso a paso para configurar la relación de aspecto, XDimension y exportar
  PNG usando un generador de códigos de barras en Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked omnidirectional
- python barcode generator
- databar aspect ratio
- xdimension pixel size
- barcodeimageformat png
language: es
lastmod: 2026-07-30
og_description: Crea un código de barras Databar apilado omnidireccional en Python.
  Este tutorial muestra cómo establecer XDimension, ajustar la relación de aspecto
  de DataBar y guardar como PNG con BarCodeImageFormat.
og_image_alt: Screenshot of a Databar Stacked Omnidirectional barcode saved as a PNG
  file
og_title: Crear código de barras Databar apilado omnidireccional – Tutorial de Python
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Create Databar Stacked Omnidirectional barcode in Python. Follow this
    step‑by‑step guide to configure aspect ratio, XDimension, and export PNG using
    a python barcode generator.
  headline: Create Databar Stacked Omnidirectional Barcode in Python
  type: TechArticle
tags:
- barcode
- python
- databar
title: Crear código de barras Databar apilado omnidireccional en Python
url: /es/python-java/general/create-databar-stacked-omnidirectional-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear código de barras Databar apilado omnidireccional en Python

¿Alguna vez necesitaste **crear un código de barras databar apilado omnidireccional** en Python pero no sabías por dónde empezar? No estás solo: muchos desarrolladores se topan con ese obstáculo cuando juegan por primera vez con la clase `BarcodeGenerator`. La buena noticia es que todo el proceso es bastante sencillo una vez que entiendes las propiedades clave.

En esta guía recorreremos un ejemplo completo y ejecutable que usa un **generador de códigos de barras python** para establecer la XDimension, ajustar la relación de aspecto del DataBar y, finalmente, exportar dos archivos PNG. Al terminar tendrás un dominio sólido de cómo generar símbolos apilados omnidireccionales de alta calidad para cualquier proyecto de inventario o logística.

## Lo que aprenderás

- Cómo instanciar un generador **databar apilado omnidireccional** con una carga GTIN‑14.  
- Por qué el **tamaño en píxeles de XDimension** es importante para la fiabilidad del escaneo.  
- El impacto de la **relación de aspecto del DataBar** en el ancho vs. la altura de la fila.  
- Cómo guardar el resultado como un archivo **BarCodeImageFormat PNG**.  
- Consejos para **reutilizar** el mismo objeto generador y producir múltiples variantes sin sobrecarga de memoria adicional.

### Prerrequisitos

- Python 3.8+ (la biblioteca que usamos es puro‑Python, no necesita ruedas compiladas).  
- El paquete `barcode-generator` (instálalo con `pip install barcode-generator`).  
- Una carpeta con permisos de escritura: el script volcará dos imágenes PNG allí.

Si ya manejas importaciones básicas de Python y código orientado a objetos, estás listo para comenzar.

## Crear código de barras Databar apilado omnidireccional – Visión general de los pasos

A continuación dividimos el flujo de trabajo en seis pasos manejables. Cada paso es un fragmento de código autónomo que puedes copiar‑pegar en un REPL o archivo de script. Siéntete libre de experimentar: cambiar la relación de aspecto o la XDimension te dará instantáneamente un estilo visual diferente.

---

## Paso 1: Crear generador Databar apilado omnidireccional

Lo primero que hacemos es **crear una instancia del generador databar apilado omnidireccional**, pasando el enum `EncodeTypes` apropiado y la cadena de datos.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1 – initialize the generator with a GTIN‑14 payload
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)
```

> **Por qué importa:** La bandera `EncodeTypes.DatabarStackedOmniDirectional` indica a la biblioteca que produzca un símbolo apilado omnidireccional, que es la única variante DataBar que **puede codificar hasta 14 dígitos y sigue siendo legible desde cualquier ángulo**.

---

## Configurar el tamaño de píxel XDimension

El **tamaño de píxel XDimension** controla el módulo más pequeño (la barra negra más fina). Un valor de `2` píxeles funciona bien para la mayoría de los escenarios de visualización en pantalla.

```python
# Step 2 – set the smallest module to 2 pixels
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2
```

> **Consejo profesional:** Si planeas imprimir el código de barras a alta DPI, aumenta este valor a 3 o 4 para evitar bordes borrosos.

---

## Ajustar la relación de aspecto del DataBar (15)

La **relación de aspecto del DataBar** determina cuán ancha es cada fila en comparación con su altura. Una relación de aspecto de `15` produce filas más anchas, lo que muchos escáneres prefieren para una captura rápida en movimiento.

```python
# Step 3 – make rows wider (aspect ratio = 15)
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
```

> **¿Por qué 15?** La especificación oficial de GS1 recomienda una relación entre 10 y 20 para símbolos apilados omnidireccionales. Elegimos `15` como valor predeterminado equilibrado.

---

## Exportar el código de barras como PNG usando BarCodeImageFormat

Ahora que el generador está configurado, guardamos la imagen. El enum `BarCodeImageFormat.Png` garantiza una salida sin pérdida, perfecta para procesamiento posterior.

```python
# Step 4 – save the first PNG with the 15 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR15.png",
    BarCodeImageFormat.Png
)
```

> **Lo que verás:** Abre el PNG resultante; deberías notar un código de barras limpio, de alto contraste y con filas relativamente anchas.

---

## Cambiar la relación de aspecto del DataBar a 30

A veces necesitas **filas más altas** en lugar de más anchas—quizá para **ajustar una etiqueta estrecha**. Cambiar la **relación de aspecto del DataBar** a `30` hace que cada fila sea más alta.

```python
# Step 5 – increase the aspect ratio to make rows taller
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
```

> **Caso límite:** Relaciones muy altas (p. ej., >40) pueden hacer que el código de barras supere la altura típica de una etiqueta, así que pruébalo en una impresora real antes de adoptarlo.

---

## Exportar el código de barras nuevamente con la nueva relación de aspecto

Finalmente, reutilizamos el mismo objeto `barcode_generator` para escribir un segundo PNG. No es necesario recrear el generador—solo cambia la propiedad y llama a `Save` otra vez.

```python
# Step 6 – save the second PNG with the 30 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR30.png",
    BarCodeImageFormat.Png
)
```

> **Resultado:** Ahora **tienes dos archivos PNG**—uno con **filas anchas** (`AR15`) y otro con **filas altas** (`AR30`). Compáralos lado a lado para decidir cuál funciona mejor con tu configuración de escáner.

---

## Ejemplo completo y funcional

Juntando todo, aquí tienes el script completo que puedes ejecutar al instante. Sustituye `YOUR_DIRECTORY` por una ruta absoluta en tu máquina.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1️⃣ Initialize generator
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)

# 2️⃣ Set smallest module (XDimension)
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2

# 3️⃣ First aspect ratio – wider rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR15.png", BarCodeImageFormat.Png)

# 4️⃣ Second aspect ratio – taller rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR30.png", BarCodeImageFormat.Png)

print("✅ Two PNG files created – AR15 and AR30")
```

**Salida esperada** (en tu consola):

```
✅ Two PNG files created – AR15 and AR30
```

Y aparecen dos archivos de imagen en la carpeta de destino, listos para pruebas de escaneo.

---

## Conclusión

Acabamos de **crear códigos de barras databar apilados omnidireccionales** en Python, ajustado el **tamaño de píxel XDimension**, experimentado con dos configuraciones diferentes de **relación de aspecto del DataBar**, y exportado los resultados como archivos **BarCodeImageFormat PNG**. Todo el flujo de trabajo cabe en unas cuantas líneas, pero te brinda control total sobre las características visuales que más importan para los escáneres.

¿Qué sigue? Prueba **cambiar la carga útil** a otro GTIN, juega **con colores** convirtiendo el PNG a una imagen basada en paleta, o **genera un informe PDF** que **incorpore ambos PNGs lado a lado**. La clase `BarcodeGenerator` es lo suficientemente flexible como para manejar todos esos escenarios, así que siéntete libre de experimentar.

¿Tienes preguntas sobre un caso de uso concreto o te encuentras con un error? Deja un comentario abajo y estaré encantado de ayudar. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}