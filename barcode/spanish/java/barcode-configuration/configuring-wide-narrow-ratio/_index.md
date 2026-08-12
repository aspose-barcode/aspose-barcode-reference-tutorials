---
date: 2026-08-12
description: Aprenda cómo mejorar la legibilidad del código de barras personalizando
  la relación ancho‑estrecho de CODE_128 en Java con Aspose.BarCode y genere imágenes
  PNG de manera eficiente. Siga nuestro tutorial paso a paso de generación de códigos
  de barras en Java.
keywords:
- improve barcode readability
- customize code128 barcode
- barcode generation tutorial java
- step by step barcode
lastmod: 2026-08-12
linktitle: Configurando la relación ancho‑estrecho
og_description: Aprenda cómo mejorar la legibilidad del código de barras personalizando
  la relación ancho‑estrecho de CODE_128 en Java con Aspose.BarCode. Este tutorial
  paso a paso le muestra cómo generar códigos de barras PNG rápidamente.
og_image_alt: Guide to creating CODE_128 barcode with custom wide‑narrow ratio in
  Java
og_title: Mejore la legibilidad del código de barras con la relación ancho‑estrecho
  de CODE_128 (58 caracteres)
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Learn how to improve barcode readability by customizing the CODE_128
    wide‑narrow ratio in Java using Aspose.BarCode, and generate PNG images efficiently.
    Follow our step‑by‑step barcode generation tutorial Java.
  headline: Improve barcode readability with CODE_128 wide‑narrow ratio
  type: TechArticle
- description: Learn how to improve barcode readability by customizing the CODE_128
    wide‑narrow ratio in Java using Aspose.BarCode, and generate PNG images efficiently.
    Follow our step‑by‑step barcode generation tutorial Java.
  name: Improve barcode readability with CODE_128 wide‑narrow ratio
  steps:
  - name: set document directory
    text: Make sure the directory exists and you have write permissions; this is where
      the **saved barcode image** file will be placed.
  - name: instantiate barcode object
    text: The `BarcodeGenerator` class creates barcode images based on the specified
      symbology and encoding options. Here we **create a CODE_128 barcode** by passing
      `EncodeTypes.CODE_128` to the constructor.
  - name: set wide‑narrow ratio
    text: '`setWideNarrowRatio` sets the proportion between wide and narrow bars for
      the generated barcode. The `setWideNarrowRatio` method lets you fine‑tune the
      visual spacing. A value of `3.0f` means the wide bar is three times the width
      of a narrow bar, which falls within the optimal 2.0‑3.0 range for most'
  - name: save image to disk
    text: Calling `save` will **generate a barcode image** and store it as a PNG file,
      completing the **save barcode image** step.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode works seamlessly with Spring, Java EE, Android, and
      other Java environments.
    question: Can I use Aspose.BarCode with other Java frameworks?
  - answer: Change the symbology type in the `BarcodeGenerator` constructor, for example
      `EncodeTypes.QR` for QR codes.
    question: How can I generate barcodes with different symbologies?
  - answer: Yes, you can access the free trial version on the [Aspose.BarCode free
      trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.BarCode?
  - answer: Refer to the documentation on the [Aspose.BarCode Java API documentation](https://reference.aspose.com/barcode/java/).
    question: Where can I find detailed documentation for Aspose.BarCode?
  - answer: Visit the Aspose.BarCode community forum at [Aspose.BarCode community
      forum](https://forum.aspose.com/c/barcode/13) for support and community discussions.
    question: How to get support for Aspose.BarCode?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- barcode readability
- Aspose.BarCode
- Java barcode tutorial
title: Mejore la legibilidad del código de barras con la relación ancho‑estrecho de
  CODE_128
url: /es/java/barcode-configuration/configuring-wide-narrow-ratio/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mejorar la legibilidad del código de barras con la relación ancho‑estrecho de CODE_128

## Introducción

Si necesita **mejorar la legibilidad del código de barras** para etiquetas de inventario, etiquetas de envío o cualquier aplicación que use CODE_128, ajustar la relación ancho‑estrecho es la técnica más eficaz. En este tutorial recorreremos un proceso de creación de **código de barras paso a paso** usando Aspose.BarCode para Java, mostrándole cómo configurar la relación, **generar imágenes PNG del código de barras** y **guardar la imagen del código de barras** en disco. También verá por qué la relación es importante para el rendimiento del escáner y cómo ajustarla finamente para su entorno de impresión específico.

## Respuestas rápidas
- **¿Qué es la relación ancho‑estrecho?** Controla la anchura relativa de las barras anchas frente a las barras estrechas en un código de barras.  
- **¿Qué simbología soporta el ajuste de la relación?** La mayoría de las simbologías 1‑D, incluido CODE_128, le permiten establecer una relación personalizada.  
- **¿Necesito una licencia?** Hay una prueba gratuita disponible, pero se requiere una licencia comercial para uso en producción.  
- **¿Puedo generar una imagen de código de barras en formato PNG?** Sí—use `generator.save(...)` para generar imágenes PNG del código de barras.  
- **¿El código es compatible con Java 8+?** Absolutamente; Aspose.BarCode funciona con todas las versiones modernas de Java.

## Requisitos previos

Antes de sumergirnos en el código, asegúrese de contar con lo siguiente:

- Java Development Kit (JDK) instalado en su máquina.  
- Biblioteca Aspose.BarCode para Java. Descárguela desde el [download link](https://releases.aspose.com/barcode/java/).

## Importar paquetes

Para comenzar, importe la clase esencial de Aspose.BarCode en su proyecto.  
`BarcodeGenerator` es la clase principal utilizada para generar imágenes de códigos de barras con la simbología y opciones especificadas.  

```java
// Import Aspose.BarCode library
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Qué es la relación ancho‑estrecho y por qué ajustarla?

La relación ancho‑estrecho define cuántas veces más ancha es una barra “ancha” en comparación con una barra “estrecha”. Ajustar esta relación mejora la compatibilidad con los escáneres (la mayoría de los escáneres leen mejor con relaciones entre 2.0 y 3.0), compensa las limitaciones de DPI de la impresora y le permite adaptar el estilo visual de una marca sin sacrificar la fiabilidad.

## Cómo mejorar la legibilidad del código de barras creando un código CODE_128 con relación ancho‑estrecho en Java

Comience añadiendo la biblioteca Aspose.BarCode a su proyecto Java, luego cree una instancia de `BarcodeGenerator` especificando `EncodeTypes.CODE_128`. Configure el generador con la relación ancho‑estrecho deseada usando `setWideNarrowRatio`, ajuste opcionalmente otras configuraciones visuales y, finalmente, llame a `save` para escribir el código de barras como un archivo PNG. Este flujo de trabajo conciso garantiza una calidad de código de barras constante y mejora las tasas de lectura del escáner en diversos dispositivos.

### Paso 1: establecer el directorio del documento

Asegúrese de que el directorio exista y tenga permisos de escritura; aquí se colocará el archivo de **imagen de código de barras guardada**.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### Paso 2: instanciar el objeto de código de barras

La clase `BarcodeGenerator` crea imágenes de códigos de barras basadas en la simbología y opciones de codificación especificadas.  

```java
// Instantiate barcode object
// Create an instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

Aquí **creamos un código de barras CODE_128** pasando `EncodeTypes.CODE_128` al constructor.

### Paso 3: establecer la relación ancho‑estrecho

`setWideNarrowRatio` establece la proporción entre barras anchas y estrechas para el código de barras generado.  

```java
// Set the wide to narrow ratio for the barcode
generator.getParameters().getBarcode().setWideNarrowRatio(3.0f);
```

El método `setWideNarrowRatio` le permite afinar el espaciado visual. Un valor de `3.0f` significa que la barra ancha es tres veces la anchura de una barra estrecha, lo que se encuentra dentro del rango óptimo de 2.0‑3.0 para la mayoría de los escáneres.

### Paso 4: guardar la imagen en disco

Llamar a `save` **generará una imagen de código de barras** y la almacenará como un archivo PNG, completando el paso de **guardar la imagen del código de barras**.  

```java
// Save the image to disk in PNG format
generator.save(dataDir + "wideNarrowRatio.png");
```

## ¿Por qué ajustar la relación ancho‑estrecho?

Ajustar la relación ancho‑estrecho mejora la compatibilidad con los escáneres porque la mayoría de los escáneres industriales leen mejor cuando la relación está entre 2.0 y 3.0. También mejora la calidad de impresión al compensar resoluciones de impresora de 150–300 dpi, reduciendo la distorsión de las barras. Además, la relación permite a las empresas alinear la estética del código de barras con las directrices de marca sin comprometer el rendimiento de escaneo fiable.

## Problemas comunes y soluciones

| Problema | Razón | Solución |
|----------|-------|----------|
| El código de barras se ve distorsionado | Relación demasiado alta/baja para la impresora | Ajuste el valor pasado a `setWideNarrowRatio` (p.ej., 2.0‑2.5). |
| Archivo no creado | Ruta `dataDir` inválida o permisos insuficientes | Verifique la ruta del directorio y asegúrese de que la aplicación tenga acceso de escritura. |
| El escáner no puede leer el código de barras | Relación fuera del rango recomendado para la simbología | Utilice relaciones estándar (2.0‑3.0) o pruebe con el escáner objetivo. |

## Preguntas frecuentes

**Q: ¿Puedo usar Aspose.BarCode con otros frameworks de Java?**  
A: Sí, Aspose.BarCode funciona sin problemas con Spring, Java EE, Android y otros entornos Java.

**Q: ¿Cómo puedo generar códigos de barras con diferentes simbologías?**  
A: Cambie el tipo de simbología en el constructor de `BarcodeGenerator`, por ejemplo `EncodeTypes.QR` para códigos QR.

**Q: ¿Hay una versión de prueba disponible para Aspose.BarCode?**  
A: Sí, puede acceder a la versión de prueba gratuita en la [Aspose.BarCode free trial page](https://releases.aspose.com/).

**Q: ¿Dónde puedo encontrar documentación detallada para Aspose.BarCode?**  
A: Consulte la documentación en la [Aspose.BarCode Java API documentation](https://reference.aspose.com/barcode/java/).

**Q: ¿Cómo obtener soporte para Aspose.BarCode?**  
A: Visite el foro de la comunidad de Aspose.BarCode en [Aspose.BarCode community forum](https://forum.aspose.com/c/barcode/13) para obtener soporte y discusiones comunitarias.

**Última actualización:** 2026-08-12  
**Probado con:** Aspose.BarCode for Java 24.11 (latest at time of writing)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Generar código de barras Java – Establecer resolución de imagen con Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)
- [Detectar orientación del código de barras en Java con Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/configuring-barcode-orientation/)
- [Cómo crear imágenes de código de barras code128 en Java con Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}