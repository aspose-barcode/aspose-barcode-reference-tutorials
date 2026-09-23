---
date: 2026-08-28
description: Aprenda cómo crear una imagen de código de barras en Java con Aspose
  Barcode Java, establecer los símbolos de inicio y fin de CODABAR y generar archivos
  PNG sin marcas de agua.
keywords:
- create barcode image java
- barcode generation without watermark
- codabar start stop symbols
lastmod: 2026-08-28
linktitle: Configuración de símbolos de inicio y fin
og_description: Crear imagen de código de barras en Java usando Aspose Barcode Java.
  Esta guía muestra cómo establecer los símbolos de inicio y fin de CODABAR y exportar
  PNG sin marcas de agua.
og_image_alt: 'Aspose Barcode Java tutorial: create barcode image with start/stop
  symbols'
og_title: Crear imagen de código de barras en Java – guía de símbolos de inicio y
  fin
schemas:
- author: Aspose
  dateModified: '2026-08-28'
  description: Learn how to create barcode image java with Aspose Barcode Java, set
    CODABAR start and stop symbols, and generate PNG files without watermarks.
  headline: Aspose Barcode Java – Create barcode image with start/stop symbols
  type: TechArticle
- questions:
  - answer: Aspose.BarCode for Java.
    question: What library creates barcode images in Java?
  - answer: Yes, using `setCodabarStartSymbol` and `setCodabarStopSymbol`.
    question: Can I customize start/stop symbols?
  - answer: CODABAR.
    question: Which barcode type is used in this example?
  - answer: A commercial license is required for non‑trial use.
    question: Do I need a license for production?
  - answer: PNG image saved to disk.
    question: What output format is generated?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- barcode generation
- Aspose.BarCode
- Java barcode tutorial
title: Aspose Barcode Java – Crear imagen de código de barras con símbolos de inicio
  y fin
url: /es/java/barcode-configuration/setting-start-stop-symbols/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Barcode Java – Crear imagen de código de barras con símbolos de inicio/fin

## Introducción

En este tutorial exhaustivo **creará archivos de imagen de código de barras java** con Aspose Barcode Java y aprenderá **cómo establecer los símbolos de inicio y fin** para códigos de barras CODABAR. Ya sea que esté construyendo un terminal punto de venta, un sistema de gestión de almacenes o cualquier aplicación que necesite generación fiable de códigos de barras, personalizar estos símbolos le permite cumplir con especificaciones heredadas mientras mantiene el código limpio y mantenible. Recorreremos cada paso, explicaremos por qué cada configuración es importante y le mostraremos cómo producir una imagen PNG que no contenga marca de agua de prueba.

## Respuestas rápidas
- **¿Qué biblioteca crea imágenes de códigos de barras en Java?** Aspose.BarCode for Java.  
- **¿Puedo personalizar los símbolos de inicio/fin?** Sí, usando `setCodabarStartSymbol` y `setCodabarStopSymbol`.  
- **¿Qué tipo de código de barras se usa en este ejemplo?** CODABAR.  
- **¿Necesito una licencia para producción?** Se requiere una licencia comercial para uso no de prueba.  
- **¿Qué formato de salida se genera?** Imagen PNG guardada en disco.

## ¿Qué es Aspose Barcode Java?

Aspose Barcode Java es una **biblioteca Java sin dependencias que genera más de 70 simbologías de códigos de barras**, desde códigos clásicos 1D como CODABAR hasta códigos 2D modernos como QR y DataMatrix. Maneja todo el codificado de bajo nivel, por lo que puede centrarse en la lógica de negocio mientras garantiza el cumplimiento de los estándares de la industria.

## ¿Por qué usar Aspose Barcode Java para generar códigos de barras sin marca de agua?

Cargue su licencia primero, y la biblioteca produce imágenes limpias—sin superposición de “Aspose Evaluation”. También ofrece **control granular** (símbolos de inicio/fin, colores, tamaños) y **compatibilidad multiplataforma** (cualquier entorno de ejecución Java, incluido Android). Con soporte para **más de 50 formatos de salida** y la capacidad de transmitir imágenes directamente a respuestas HTTP, es la opción preferida para la creación de códigos de barras de alto rendimiento y calidad de producción.

## Requisitos previos

Antes de comenzar, asegúrese de tener:

1. **Java Development Kit (JDK)** – Instale el JDK más reciente desde [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. **Biblioteca Aspose.BarCode para Java** – Descárguela desde el [enlace de descarga](https://releases.aspose.com/barcode/java/).

Tener estos elementos listos garantiza que pueda **crear imagen de código de barras java** sin componentes faltantes.

## Importar paquetes

Las siguientes importaciones le dan acceso a las clases principales necesarias para la generación de códigos de barras:

El enum `CodabarSymbol` define los caracteres de inicio/fin permitidos para los códigos de barras CODABAR.  

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.CodabarSymbol;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Guía paso a paso

### ¿Cómo definir la carpeta de salida para la imagen del código de barras?

Especifique la carpeta donde se escribirá el archivo PNG. Usar `Paths.get` hace que el código sea portátil en Windows, macOS y Linux.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### ¿Cómo crear un generador de códigos de barras para CODABAR?

La clase `BarcodeGenerator` crea una imagen de código de barras para una simbología y datos dados.  

Instancie `BarcodeGenerator` con la simbología CODABAR y la cadena de datos que desea codificar.

```java
// Create instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "12345678");
```

### ¿Cómo establecer el símbolo de inicio de CODABAR?

`setCodabarStartSymbol` establece el carácter que marca el inicio de un código de barras CODABAR.  

Llame a `setCodabarStartSymbol` y pase uno de los caracteres admitidos (`A`, `B`, `C`, `D`). En este ejemplo usamos `A`.

```java
// Set the Codabar start symbol to A
generator.getParameters().getBarcode().getCodabar().setCodabarStartSymbol(CodabarSymbol.A);
```

### ¿Cómo establecer el símbolo de fin de CODABAR?

`setCodabarStopSymbol` establece el carácter que marca el final de un código de barras CODABAR.  

Utilice `setCodabarStopSymbol` con el carácter de fin correspondiente—`D` en este caso.

```java
// Set the Codabar stop symbol to D
generator.getParameters().getBarcode().getCodabar().setCodabarStopSymbol(CodabarSymbol.D);
```

### ¿Cómo guardar el código de barras generado como archivo PNG?

El enum `SaveFormat` especifica el formato de archivo para guardar la imagen del código de barras.  

Invocar el método `save`, proporcionando el nombre completo del archivo y el valor del enum `SaveFormat.Png`. La imagen se escribe sin marca de agua una vez que se aplica una licencia válida.

```java
// Save the image to disk in PNG format
generator.save(dataDir + "startAndStopSymbols.png");
```

## Problemas comunes y consejos

La clase `License` carga un archivo de licencia Aspose para habilitar el modo de todas las funciones.

- **Ruta de directorio incorrecta** – Asegúrese de que `dataDir` termine con el separador de archivos apropiado o construya la ruta con `Paths.get`.  
- **Caracteres de inicio/fin no compatibles** – CODABAR solo acepta `A`, `B`, `C` o `D`. Proporcionar cualquier otro valor lanza una `IllegalArgumentException`.  
- **Licencia no aplicada** – En modo de prueba la salida contiene una marca de agua. Cargue su archivo de licencia con `License license = new License(); license.setLicense("Aspose.Total.Java.lic");` antes de crear el generador para evitarlo.  
- **Generación a gran escala** – Al generar miles de códigos de barras, reutilice una única instancia de `BarcodeGenerator` y solo cambie el texto del código para reducir la sobrecarga de creación de objetos.

## Preguntas frecuentes

### ¿Puedo usar Aspose.BarCode para Java en un proyecto comercial?

Sí. Adquiera una licencia comercial [adquirir una licencia comercial](https://purchase.aspose.com/buy) para eliminar la marca de agua de evaluación y obtener soporte técnico completo.

### ¿Hay una versión de prueba gratuita disponible?

Absolutamente. Descargue la versión de prueba [descargar la versión de prueba](https://releases.aspose.com/) para evaluar todas las funciones antes de comprar.

### ¿Cómo puedo obtener soporte para Aspose.BarCode para Java?

Visite el foro de Aspose.BarCode [foro de Aspose.BarCode](https://forum.aspose.com/c/barcode/13) para obtener ayuda de la comunidad, o abra un ticket de soporte a través del portal de su cuenta Aspose.

### ¿Cómo obtener una licencia temporal para pruebas?

Puede solicitar una licencia temporal de 30 días [solicitar una licencia temporal de 30 días](https://purchase.aspose.com/temporary-license/). Esto le permite ejecutar pruebas similares a producción sin una compra completa.

### ¿Qué otras simbologías de códigos de barras admite Aspose.BarCode?

La biblioteca admite **más de 70 simbologías**, incluyendo Code128, EAN‑13, QR, DataMatrix, PDF417 y muchas más. Consulte la lista completa en la documentación oficial.

## Preguntas y respuestas adicionales (compatible con IA)

**Q:** ¿Qué formatos de imagen puedo exportar además de PNG?  
**A:** Aspose.BarCode admite PNG, JPEG, BMP, GIF y TIFF. Elija el formato deseado cambiando el valor del enum `SaveFormat` en la llamada `save`.

**Q:** ¿Puedo generar imágenes de códigos de barras en memoria sin escribir en disco?  
**A:** Sí. Llame a `generator.save(OutputStream)` para escribir directamente a un flujo—ideal para APIs web que devuelven la imagen como respuesta HTTP.

**Q:** ¿La biblioteca funciona en Android?  
**A:** La versión Java se ejecuta en Android, pero debe incluir manualmente las dependencias requeridas (no hay Maven Central para Android). La API principal sigue siendo idéntica.

## Conclusión

Ahora ha aprendido cómo **crear imagen de código de barras java** y establecer con precisión **símbolos de inicio/fin** para un código de barras CODABAR usando Aspose Barcode Java. Este enfoque le brinda la flexibilidad para cumplir con especificaciones heredadas mientras mantiene su base de código limpia y mantenible. Explore personalizaciones adicionales—como cambiar colores, agregar texto legible por humanos o cambiar a otras simbologías—consultando la referencia oficial de la API en [documentación](https://reference.aspose.com/barcode/java/).

---

**Última actualización:** 2026-08-28  
**Probado con:** Aspose.BarCode for Java 24.12  
**Autor:** Aspose

## Tutoriales relacionados

- [Validar suma de verificación y crear código de barras Codabar en Java con Aspose.BarCode](/barcode/java/checksum-and-validation/)
- [Crear código de barras con Aspose - Establecer dimensiones X & Y en Java](/barcode/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [Cómo generar código de barras java: crear una imagen de código de barras exacta](/barcode/java/barcode-basics/creating-image-exact-barcode/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}