---
date: 2026-10-19
description: Aprenda cómo crear QR code java y generar varios códigos de barras en
  una sola imagen usando Aspose.BarCode for Java. Incluye configuración, código y
  solución de problemas.
keywords:
- create qr code java
- how to create qr
- java barcode library
- generate multiple barcodes
- aspose trial license
lastmod: 2026-10-19
linktitle: Generar varios códigos de barras en una sola imagen
og_description: Crear QR code java y combinar varios tipos de códigos de barras en
  una sola imagen con Aspose.BarCode for Java. Siga la guía paso a paso, vea fragmentos
  de código y aprenda consejos para solucionar problemas.
og_image_alt: Screenshot of a Java application generating a QR code and other barcodes
  on one combined image
og_title: Crear QR code java – generar varios códigos de barras en una sola imagen
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to create QR code java and generate multiple barcodes on
    a single image using Aspose.BarCode for Java. Includes setup, code, and troubleshooting.
  headline: Create QR code java – generate multiple barcodes on one image
  type: TechArticle
- questions:
  - answer: Yes. Use the `BarcodeGenerator` properties such as `setBarColor`, `setBackgroundColor`,
      and `setXDimension` to style each barcode independently before adding it to
      the canvas.
    question: Can I customize the appearance of individual barcodes in the generated
      image?
  - answer: Absolutely. The library supports 50+ symbologies, including CODE_39, DATA_MATRIX,
      QR, CODE_128, EAN_13, and AZTEC, as demonstrated in this tutorial.
    question: Is Aspose.BarCode compatible with different barcode symbologies?
  - answer: Download the JAR from the Aspose.BarCode for Java library download page,
      add it to your project’s classpath, and import the required namespaces as shown
      in the “Import namespaces” section.
    question: How do I integrate Aspose.BarCode into my Java project?
  - answer: Yes. Purchase a license from the Aspose.BarCode license purchase page
      to remove trial limitations and obtain full production support.
    question: Can I use Aspose.BarCode for commercial applications?
  - answer: Certainly. A free trial license is available from the Aspose.BarCode free
      trial download page, giving you full API access for evaluation.
    question: Are there trial options available for Aspose.BarCode?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- create qr code
- aspose barcode
- java barcode generation
- multiple barcodes image
title: Crear QR code java – generar varios códigos de barras en una sola imagen
url: /es/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear código QR java – generar varios códigos de barras en una sola imagen

## Introducción

En este tutorial aprenderás **cómo crear código QR java** y combinar varios tipos de códigos de barras diferentes en un solo lienzo usando **Aspose.BarCode for Java**. Ya sea que necesites una etiqueta QR compacta, un código de barras de producto, o una mezcla de simbologías 2‑D y lineales, esta guía te acompañará paso a paso—desde la configuración del proyecto hasta guardar la imagen combinada final—para que puedas comenzar a integrar la generación de códigos de barras en tus aplicaciones Java de inmediato.

## Respuestas rápidas
- **¿Qué biblioteca debo usar?** Aspose.BarCode for Java proporciona el conjunto más completo de simbologías.  
- **¿Puedo generar diferentes tipos de códigos de barras juntos?** Sí, puedes mezclar CODE_39, QR, AZTEC y más en un solo lienzo.  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita funciona para pruebas; se requiere una licencia comercial para producción.  
- **¿Qué versión de Java es compatible?** Java 8 y versiones posteriores son totalmente compatibles.  
- **¿Es configurable el formato de salida?** Puedes exportar la imagen combinada como PNG, JPEG, BMP o TIFF.

## Qué es crear código QR java?

`create QR code java` se refiere al proceso de convertir una cadena de texto en una matriz bidimensional que puede ser escaneada por smartphones o lectores de códigos de barras. Aspose.BarCode for Java realiza la codificación y el renderizado, de modo que puedes centrarte en la lógica de negocio en lugar de manejar imágenes a nivel de píxel.

## ¿Por qué usar Aspose.BarCode Java para generar códigos de barras java?

Aspose.BarCode soporta **más de 50 simbologías de códigos de barras** —incluyendo QR, Data Matrix, Code 128, AZTEC y códigos lineales tradicionales— lo que lo convierte en la biblioteca de códigos de barras Java más versátil. Renderiza **imágenes anti‑alias a hasta 1200 dpi**, garantizando escaneos nítidos en pantalla e impresión. La API solo requiere la JVM y ofrece un modelo de configuración fluido para personalizar tamaño, color, márgenes y corrección de errores en solo unas pocas líneas de código.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

- Una comprensión sólida de los fundamentos de Java.  
- JDK 8 o superior instalado y configurado en tu PATH.  
- El JAR de Aspose.BarCode for Java (descárgalo desde la página oficial de descarga de Aspose.BarCode for Java).  
- Un IDE como IntelliJ IDEA o Eclipse para editar y ejecutar el ejemplo.  

## Importar espacios de nombres

Las declaraciones de importación traen clases de Aspose.BarCode como `BarcodeGenerator`, `EncodeTypes` y `BarCodeImageFormat` al alcance, permitiéndote referenciarlas sin nombres totalmente calificados.  
`BarcodeGenerator` es la clase principal usada para configurar y generar imágenes de códigos de barras.  
`EncodeTypes` es un enum en Aspose.BarCode que especifica la simbología del código de barras a generar.  
`BarCodeImageFormat` define el formato de imagen de salida para el código de barras generado.

## Paso 1: establecer el directorio de recursos

El **directorio de recursos** es la carpeta en tu sistema de archivos donde se escribirán todas las imágenes de códigos de barras generadas. Definirlo una sola vez mantiene tu proyecto organizado y facilita la limpieza de archivos antiguos.

```java
import java.awt.Color;
import java.awt.Graphics;
import java.awt.image.BufferedImage;
import java.io.File;
import java.util.ArrayList;
import java.util.HashMap;

import javax.imageio.ImageIO;

import com.aspose.barcode.BaseEncodeType;
import com.aspose.barcode.EncodeTypes;


import com.aspose.barcode.generation.BarcodeGenerator;
```

## Paso 2: crear una colección de códigos de barras

Un `HashMap<String, EncodeTypes>` almacena la cadena de datos de cada código de barras junto con la simbología que deseas usar. `HashMap` es una colección de Java que asigna claves a valores. Esta colección impulsa el bucle de generación que sigue. `EncodeTypes` es un enum que especifica qué tipo de código de barras generar.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Paso 3: generar imágenes de códigos de barras

El bucle de generación itera sobre el `HashMap`, crea un `BarcodeGenerator` para cada entrada y llama a `generateBarCodeImage()` para obtener un `BufferedImage`. `generateBarCodeImage()` crea un `BufferedImage` que contiene el código de barras renderizado. `BufferedImage` es una clase Java que representa una imagen en memoria. Todas las imágenes se añaden a un `ArrayList<BufferedImage>` para su posterior composición. `ArrayList` es una implementación de lista redimensionable en Java.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Paso 4: crear una imagen combinada

Primero, el algoritmo calcula el **ancho máximo** entre todas las imágenes de códigos de barras y la **altura total** necesaria para apilarlas verticalmente con espaciado opcional. Luego crea un `BufferedImage` de ese tamaño y dibuja cada código de barras en el lienzo usando un objeto `Graphics2D`. `Graphics2D` es una clase Java que proporciona capacidades de renderizado 2D para dibujar formas e imágenes.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Paso 5: guardar el resultado

Finalmente, la imagen compuesta se escribe en disco con `ImageIO.write`, usando el formato que especificaste (PNG, JPEG, BMP o TIFF). `ImageIO.write` escribe un `BufferedImage` a un archivo en el formato especificado. La ruta del archivo es relativa al directorio de recursos definido anteriormente.

```java
int maxWidth = 0;
int sumHeight = 0;
for (BufferedImage bmp : images) {
    sumHeight += bmp.getHeight();
    if (maxWidth < bmp.getWidth())
        maxWidth = bmp.getWidth();
}

int offset = 10;
BufferedImage resultBitmap = new BufferedImage(maxWidth + offset * 2, sumHeight + offset * images.size(),
        BufferedImage.TYPE_INT_ARGB);
Graphics g = resultBitmap.getGraphics();
g.setColor(Color.white);
g.fillRect(0, 0, resultBitmap.getWidth(), resultBitmap.getHeight());

int yPosition = offset;
for (int i = 0; i < images.size(); ++i) {
    BufferedImage currentBitmap = images.get(i);
    g.drawImage(currentBitmap, offset, yPosition, null);
    yPosition += currentBitmap.getHeight() + offset;
}
```

## Casos de uso comunes para generar múltiples códigos de barras

- **Etiquetas de embalaje** – combina códigos de producto, lote y envío en una sola etiqueta para reducir costos de impresión.  
- **Entradas de eventos** – incrusta identificadores QR, Data Matrix y Code 128 para diferentes estaciones de escaneo en un recinto.  
- **Gestión de inventario** – muestra SKU, datos de etiquetas RFID y números de serie juntos para una auditoría rápida y trazabilidad.

## Solución de problemas y consejos

- **Problemas de tamaño de imagen** – ajusta la variable `offset` para aumentar o disminuir el espacio entre códigos de barras.  
- **Simbología no soportada** – verifica que tu versión de Aspose.BarCode soporta el tipo de código de barras deseado; versiones más recientes añaden códigos 2‑D adicionales.  
- **Rendimiento** – reutiliza un solo objeto `Graphics2D` al generar muchas imágenes en un bucle para minimizar la sobrecarga de asignación de objetos.  

## Preguntas frecuentes

**P: ¿Puedo personalizar la apariencia de códigos de barras individuales en la imagen generada?**  
R: Sí. Usa las propiedades de `BarcodeGenerator` como `setBarColor`, `setBackgroundColor` y `setXDimension` para estilizar cada código de barras de forma independiente antes de añadirlo al lienzo.

**P: ¿Aspose.BarCode es compatible con diferentes simbologías de códigos de barras?**  
R: Absolutamente. La biblioteca soporta más de 50 simbologías, incluyendo CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 y AZTEC, como se muestra en este tutorial.

**P: ¿Cómo integro Aspose.BarCode en mi proyecto Java?**  
R: Descarga el JAR desde la página de descarga de la biblioteca Aspose.BarCode for Java, añádelo al classpath de tu proyecto y importa los espacios de nombres requeridos como se muestra en la sección “Importar espacios de nombres”.

**P: ¿Puedo usar Aspose.BarCode para aplicaciones comerciales?**  
R: Sí. Compra una licencia en la página de compra de licencias de Aspose.BarCode para eliminar las limitaciones de prueba y obtener soporte completo para producción.

**P: ¿Hay opciones de prueba disponibles para Aspose.BarCode?**  
R: Claro. Una licencia de prueba gratuita está disponible en la página de descarga de prueba gratuita de Aspose.BarCode, brindándote acceso completo a la API para evaluación.

**P: ¿Cómo genero un código QR de alta resolución para impresión?**  
R: Configura la propiedad `setResolutionDpi` en el `BarcodeGenerator` antes de llamar a `generateBarCodeImage()`, luego guarda el resultado en un formato sin pérdida como PNG.

**P: ¿Qué debo hacer si la imagen combinada aparece truncada?**  
R: Verifica que los cálculos de `offset` y del tamaño del lienzo tengan en cuenta correctamente todas las alturas de los códigos de barras; aumentar la altura del lienzo o reducir los tamaños individuales de los códigos de barras resuelve la mayoría de los problemas de truncamiento.

**Última actualización:** 2026-10-19  
**Probado con:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  








```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Tutoriales relacionados

- [Cómo crear imagen de código de barras Java – Añadir borde con Aspose](/barcode/java/image-manipulation/adding-borders-barcode-image/)
- [Cómo generar código de barras Java: Guardar en streams con Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/saving-barcode-image-streams/)
- [Cómo generar código de barras Java e imprimir código de barras con Aspose](/barcode/java/barcode-rendering-techniques/rendering-barcode-printer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}