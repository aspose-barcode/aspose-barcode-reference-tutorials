---
date: 2026-05-04
description: Aprenda a crear un código de barras Data Matrix usando una biblioteca
  de códigos de barras Java y a establecer la ubicación del texto del código de barras
  encima del símbolo con Aspose.BarCode. Siga nuestro ejemplo paso a paso de generación
  de códigos de barras.
keywords:
- java barcode library
- barcode generation example
- barcode text above
- customize barcode text
linktitle: Establecer ubicación del texto del código
second_title: Aspose.BarCode Java API
title: Crear código de barras Data Matrix con la biblioteca Java de códigos de barras
  y establecer la ubicación del texto del código
url: /es/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear código de barras Data Matrix con la biblioteca de códigos de barras Java y establecer la ubicación del texto del código

## Introducción

Si está construyendo un sistema de inventario, envío o seguimiento en Java, descubrirá rápidamente que una **java barcode library** confiable es esencial. Con **Aspose.BarCode for Java** puede generar un **Data Matrix barcode** en solo unas pocas líneas de código y controlar completamente el diseño visual, incluido dónde aparece el texto legible por humanos. En este tutorial recorreremos un **barcode generation example** completo, le mostraremos cómo **customize barcode text** la ubicación y explicaremos por qué colocar el texto encima del símbolo puede mejorar la usabilidad.

## Respuestas rápidas
- **¿Qué biblioteca se utiliza?** Aspose.BarCode for Java  
- **¿Qué tipo de código de barras se muestra?** Data Matrix  
- **¿Cómo posiciona el texto del código?** Usando `CodeLocation.ABOVE` (también puede usar `BELOW`)  
- **¿Necesita una licencia para producción?** Sí, se requiere una licencia comercial  
- **¿Puede el código ejecutarse en Java 8+?** Absolutamente, es compatible con Java 8 y versiones posteriores  

## ¿Qué es una java barcode library?
Una **java barcode library** brinda a los desarrolladores APIs listas para crear, leer y dar estilo a códigos de barras 1‑D y 2‑D directamente desde aplicaciones Java. Abstracta las complejas reglas de codificación y le permite centrarse en la lógica de negocio en lugar del procesamiento de imágenes de bajo nivel.

## ¿Por qué usar una java barcode library para barcode generation example?
- **Speed:** Generar códigos de barras de alta calidad en milisegundos.  
- **Reliability:** Cumplimiento incorporado con los estándares ISO/IEC.  
- **Flexibility:** Control total sobre tamaño, color, márgenes y la ubicación del **barcode text**.  
- **Cross‑platform:** Funciona en cualquier entorno basado en JVM, desde aplicaciones de escritorio hasta servicios en la nube.  

## ¿Qué es un Data Matrix barcode?
Un Data Matrix barcode es un símbolo bidimensional (2‑D) que almacena grandes cantidades de datos en un patrón cuadrado o rectangular compacto. Se utiliza ampliamente para marcar artículos pequeños, electrónica y dispositivos médicos porque puede codificar hasta 2 335 caracteres alfanuméricos.

## ¿Por qué establecer la ubicación del barcode text?
Colocar el texto legible por humanos **above**, **below** o **beside** el barcode ayuda a los usuarios a verificar rápidamente los datos codificados sin escanear. Ajustar la ubicación del texto mejora la consistencia de la UI, cumple con las directrices de marca y puede reducir errores en la entrada manual de datos.

## Requisitos previos

- Conocimientos básicos de programación en Java.  
- Java Development Kit (JDK) instalado.  
- Un IDE como Eclipse o IntelliJ IDEA.  
- Biblioteca Aspose.BarCode for Java (descárguela desde [aquí](https://releases.aspose.com/barcode/java/)).  

## Importar paquetes

Primero, importe las clases esenciales de Aspose.BarCode en su proyecto:

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Guía paso a paso

### Paso 1: Definir rutas de directorio
Especifique dónde desea leer/escribir archivos. Reemplace los marcadores de posición con rutas reales en su máquina.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### Paso 2: Crear una instancia de BarcodeGenerator
Instancie `BarcodeGenerator` con el tipo **Data Matrix** y proporcione el texto del código que desea codificar.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### Paso 3: Establecer la ubicación del barcode text (customize barcode text)
Utilice la enumeración `CodeLocation` para mover el texto legible por humanos. En este ejemplo lo colocamos **above** al barcode.

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

> **Consejo profesional:** Para colocar el texto **below** al símbolo, simplemente cambie `CodeLocation.ABOVE` a `CodeLocation.BELOW`.

### Paso 4: Guardar la imagen del barcode generado
Finalmente, escriba la imagen del barcode en el disco. El archivo contendrá el símbolo Data Matrix con el texto posicionado **above**.

```java
generator.save(dataDir + "codetextAbove.png");
```

## Problemas comunes y soluciones
- **Text not appearing:** Asegúrese de que está usando una versión de Aspose.BarCode que soporta `CodeLocation`.  
- **File path errors:** Verifique que `dataDir` termine con un separador de archivos (`/` o `\\`) apropiado para su SO.  
- **Unsupported characters:** Data Matrix solo puede codificar un conjunto limitado de caracteres; evite símbolos especiales que no estén en el estándar ISO/IEC 16022.  

## Preguntas frecuentes (FAQs)

### Q: ¿Puedo personalizar la apariencia del barcode generado?
A: Sí, Aspose.BarCode ofrece amplias opciones de personalización, permitiendo controlar colores, márgenes y estilos de fuente.

### Q: ¿Es Aspose.BarCode compatible con Java 8 y versiones posteriores?
A: Sí, Aspose.BarCode es compatible con Java 8 y versiones posteriores.

### Q: ¿Cómo puedo integrar Aspose.BarCode en mi proyecto Java existente?
A: Añada los archivos JAR de Aspose.BarCode al classpath de su proyecto, importe los paquetes necesarios y estará listo para generar códigos de barras.

### Q: ¿Hay una versión de prueba disponible para Aspose.BarCode?
A: Sí, puede explorar las capacidades de Aspose.BarCode obteniendo una prueba gratuita [aquí](https://releases.aspose.com/).

### Q: ¿Dónde puedo buscar ayuda o soporte para Aspose.BarCode?
A: Visite el [foro de Aspose.BarCode](https://forum.aspose.com/c/barcode/13) para obtener asistencia de la comunidad y soporte oficial.

## Preguntas frecuentes adicionales

**Q: ¿Puedo generar un barcode con el texto posicionado debajo del símbolo?**  
A: Sí, establezca `CodeLocation.BELOW` en el mismo método `setLocation`.

**Q: ¿La biblioteca soporta otros códigos de barras 2‑D como QR Code?**  
A: Absolutamente, simplemente cambie `EncodeTypes.DATA_MATRIX` a `EncodeTypes.QR`.

**Q: ¿Cómo cambio el tamaño de fuente del barcode text?**  
A: Use `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`.

## Conclusión

Ahora ha aprendido cómo **create a Data Matrix barcode** en Java usando una **java barcode library** y controlar con precisión **how to set barcode text** la ubicación con Aspose.BarCode. Experimente con otros valores de `CodeLocation`, configuraciones de fuente y opciones de color para adaptarse a los requisitos de diseño de su aplicación.

---

**Última actualización:** 2026-05-04  
**Probado con:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}