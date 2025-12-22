---
date: 2025-12-22
description: Aprenda a crear una imagen de código de barras con barras vacías usando
  Aspose.BarCode para Java. Este ejemplo paso a paso de generación de códigos de barras
  le ayuda a generar códigos de barras en Java rápidamente.
linktitle: Generating Barcode with Empty Bars
second_title: Aspose.BarCode Java API
title: Cómo crear una imagen de código de barras con barras vacías en Java
url: /es/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear una imagen de código de barras con barras vacías en Java

## Introducción

En las aplicaciones Java modernas, la capacidad de **create barcode image** de forma dinámica es una característica valiosa para la gestión de inventarios, sistemas de tickets y muchos otros escenarios empresariales. Aspose.BarCode for Java ofrece una API potente y fácil‑de‑usar que le permite generar códigos de barras de alta calidad con solo unas pocas líneas de código. En este tutorial recorreremos un proceso de creación de **step‑by‑step barcode** que produce un código de barras con barras vacías (sin rellenar), perfecto para diseños que requieren un aspecto hueco.

## Respuestas rápidas
- **¿Qué significa “empty bars”?** Las barras se renderizan sin el relleno sólido predeterminado, dando una apariencia hueca.  
- **¿Qué tipo de código de barras se utiliza?** Code 128 (una simbología lineal ampliamente soportada).  
- **¿Necesito una licencia para probarlo?** Hay una prueba gratuita disponible; se requiere una licencia para uso en producción.  
- **¿Qué formatos de salida son compatibles?** PNG, JPEG, BMP, GIF, TIFF y más.  
- **¿Es compatible con todas las versiones de Java?** Sí, la biblioteca funciona con Java 8 y posteriores.

## ¿Qué es create barcode image?
Crear una imagen de código de barras significa convertir una cadena de datos en una representación visual que los escáneres pueden leer. La imagen resultante puede guardarse como PNG, JPEG u otros formatos comunes y embedderse en PDFs, imprimirse en etiquetas o mostrarse en una interfaz de usuario.

## ¿Por qué usar la biblioteca Aspose.BarCode para Java?
- **Conjunto de funciones rico** – soporta más de 50 simbologías de códigos de barras, incluyendo Code 128, QR, DataMatrix y más.  
- **Control fino** – propiedades como `FilledBars`, colores, márgenes y tamaño de imagen son fácilmente configurables.  
- **Sin dependencias externas** – un solo archivo JAR maneja todo, simplificando la implementación.  
- **Documentación completa** – ejemplos, referencia de API y foros le ayudan a ponerse al día rápidamente.

## Requisitos previos

Antes de embarcarnos en el viaje de generación de códigos de barras, asegúrese de contar con los siguientes requisitos:

1. **Entorno de desarrollo Java** – Asegúrese de tener Java 8+ instalado y un IDE o herramienta de compilación compatible.  
2. **Biblioteca Aspose.BarCode para Java** – Descargue e instale la biblioteca Aspose.BarCode para Java desde la [página de descarga](https://releases.aspose.com/barcode/java/).  
3. **Directorio de documentos** – Cree un directorio en su sistema para almacenar la imagen de código de barras generada.

## Importar paquetes

En su proyecto Java, importe los paquetes necesarios para trabajar con Aspose.BarCode:

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Cómo crear una imagen de código de barras con barras vacías

### Paso 1: Configurar el directorio de recursos

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Reemplace `"Your Document Directory"` con la ruta real donde desea guardar el archivo de salida.

### Paso 2: Crear una instancia del generador de códigos de barras (Code128 Barcode Java)

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

Aquí, estamos usando la simbología **Code 128**, una de las más populares de códigos de barras lineales, lo que convierte este ejemplo en un clásico **code128 barcode java**.

### Paso 3: Establecer la propiedad FilledBars a False

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

Establecer `FilledBars` a `false` indica a Aspose.BarCode que renderice las barras como formas vacías (huecas) en lugar de bloques sólidos.

### Paso 4: Guardar la imagen del código de barras

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

La imagen se guarda en formato PNG, pero puede cambiar el enumerado `BarCodeImageFormat` para producir JPEG, BMP u otros tipos compatibles.

Repita estos pasos en su aplicación Java para crear sin esfuerzo archivos **create barcode image** con barras vacías usando Aspose.BarCode for Java.

## Conclusión

En conclusión, este tutorial le ha guiado a través de un proceso de creación de **step‑by‑step barcode** que muestra cómo **create barcode image** con barras vacías en Java. Con su API intuitiva y amplias opciones de personalización, Aspose.BarCode simplifica la integración de códigos de barras, convirtiéndose en un activo valioso para los desarrolladores que necesitan una **java barcode library** confiable.

## Preguntas frecuentes

### ¿Es Aspose.BarCode compatible con todos los entornos de desarrollo Java?
Sí, Aspose.BarCode está diseñado para integrarse sin problemas con varios entornos de desarrollo Java.

### ¿Puedo personalizar la apariencia del código de barras generado?
¡Absolutamente! Aspose.BarCode ofrece numerosas opciones de personalización, permitiéndole adaptar el código de barras a sus necesidades específicas.

### ¿Está disponible una versión de prueba para Aspose.BarCode?
Sí, puede explorar las capacidades de Aspose.BarCode obteniendo una prueba gratuita [aquí](https://releases.aspose.com/).

### ¿Cómo puedo obtener soporte para Aspose.BarCode?
Para cualquier consulta o asistencia, visite el [foro de Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

### ¿Dónde puedo encontrar documentación detallada para Aspose.BarCode?
La documentación completa está disponible [aquí](https://reference.aspose.com/barcode/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-22  
**Tested With:** Aspose.BarCode Java 24.11 (latest)  
**Author:** Aspose