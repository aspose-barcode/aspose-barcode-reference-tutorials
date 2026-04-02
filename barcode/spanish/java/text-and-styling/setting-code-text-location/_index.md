---
date: 2025-12-27
description: Aprende cómo crear códigos de barras Data Matrix y cómo establecer la
  ubicación del texto del código de barras en Java usando Aspose.BarCode. Sigue nuestra
  guía paso a paso para una personalización completa.
linktitle: Setting Code Text Location
second_title: Aspose.BarCode Java API
title: Crear código de barras Data Matrix y establecer la ubicación del texto del
  código en Java
url: /es/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear código de barras Data Matrix y establecer la ubicación del texto del código en Java

## Introducción

Generar códigos de barras es un requisito rutinario para inventario, envíos y muchas otras aplicaciones basadas en Java. Con **Aspose.BarCode for Java** puedes **crear códigos de barras Data Matrix** rápidamente y controlar cada aspecto visual, incluida la ubicación del texto legible por humanos. En este tutorial recorreremos los pasos exactos para **crear códigos de barras Data Matrix** y demostraremos **cómo establecer el texto del código de barras** encima del símbolo para que coincida con las especificaciones de tu diseño.

## Respuestas rápidas
- **¿Qué biblioteca se usa?** Aspose.BarCode for Java  
- **¿Qué tipo de código de barras se muestra?** Data Matrix  
- **¿Cómo se posiciona el texto del código?** Usando `CodeLocation.ABOVE`  
- **¿Necesitas una licencia para producción?** Sí, se requiere una licencia comercial  
- **¿Puede el código ejecutarse en Java 8+?** Absolutamente, soporta Java 8 y versiones posteriores  

## ¿Qué es un código de barras Data Matrix?
Un código de barras Data Matrix es un símbolo bidimensional (2‑D) que almacena grandes cantidades de datos en un patrón cuadrado o rectangular compacto. Se utiliza ampliamente para marcar artículos pequeños, componentes electrónicos y dispositivos médicos porque puede codificar hasta 2 335 caracteres alfanuméricos.

## ¿Por qué establecer la ubicación del texto del código de barras?
Colocar el texto legible por humanos **encima**, **debajo** o **al lado** del código de barras ayuda a los usuarios a verificar rápidamente los datos codificados sin necesidad de escanear. Ajustar la ubicación del texto mejora la consistencia de la interfaz y cumple con las directrices de marca.

## Requisitos previos

- Conocimientos básicos de programación Java.  
- Java Development Kit (JDK) instalado.  
- Un IDE como Eclipse o IntelliJ IDEA.  
- Biblioteca Aspose.BarCode for Java (descárgala desde [here](https://releases.aspose.com/barcode/java/)).  

## Importar paquetes

Primero, importa las clases esenciales de Aspose.BarCode en tu proyecto:

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

Estas importaciones te dan acceso al generador de códigos de barras y a la enumeración que controla la ubicación del texto.

## Guía paso a paso

### Paso 1: Definir rutas de directorios
Especifica dónde deseas leer/escribir archivos. Reemplaza los marcadores de posición con rutas reales en tu máquina.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### Paso 2: Crear una instancia de BarcodeGenerator
Instancia `BarcodeGenerator` con el tipo **Data Matrix** y proporciona el texto del código que deseas codificar.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### Paso 3: Cómo establecer la ubicación del texto del código de barras
Utiliza la enumeración `CodeLocation` para mover el texto legible por humanos. En este ejemplo lo colocamos **encima** del código de barras.

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

### Paso 4: Guardar la imagen del código de barras generado
Finalmente, escribe la imagen del código de barras en disco. El archivo contendrá el símbolo Data Matrix con el texto posicionado encima.

```java
generator.save(dataDir + "codetextAbove.png");
```

## Problemas comunes y soluciones
- **Texto no aparece:** Asegúrate de estar usando una versión de Aspose.BarCode que soporte `CodeLocation`.  
- **Errores de ruta de archivo:** Verifica que `dataDir` termine con un separador de archivos (`/` o `\\`) apropiado para tu SO.  
- **Caracteres no soportados:** Data Matrix solo puede codificar un conjunto limitado de caracteres; evita símbolos especiales que no estén en la norma ISO/IEC 16022.

## Preguntas frecuentes (FAQs)

### P: ¿Puedo personalizar la apariencia del código de barras generado?
R: Sí, Aspose.BarCode ofrece amplias opciones de personalización, permitiéndote controlar colores, márgenes y estilos de fuente.

### P: ¿Es Aspose.BarCode compatible con Java 8 y versiones posteriores?
R: Absolutamente, la biblioteca funciona con Java 8 y todas sus versiones posteriores.

### P: ¿Cómo puedo integrar Aspose.BarCode en mi proyecto Java existente?
R: Añade los archivos JAR de Aspose.BarCode al classpath de tu proyecto, importa los paquetes necesarios y estarás listo para generar códigos de barras.

### P: ¿Hay una versión de prueba disponible para Aspose.BarCode?
R: Sí, puedes explorar las capacidades de Aspose.BarCode obteniendo una prueba gratuita [here](https://releases.aspose.com/).

### P: ¿Dónde puedo buscar ayuda o soporte para Aspose.BarCode?
R: Visita el [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) para asistencia de la comunidad y soporte oficial.

## Preguntas frecuentes adicionales

**P: ¿Puedo generar un código de barras con el texto posicionado debajo del símbolo?**  
R: Sí, establece `CodeLocation.BELOW` en el mismo método `setLocation`.

**P: ¿La biblioteca soporta otros códigos de barras 2‑D como QR Code?**  
R: Absolutamente, simplemente cambia `EncodeTypes.DATA_MATRIX` a `EncodeTypes.QR`.

**P: ¿Cómo cambio el tamaño de fuente del texto del código de barras?**  
R: Usa `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`.

## Conclusión

Ahora sabes cómo **crear códigos de barras Data Matrix** en Java y controlar con precisión **cómo establecer la ubicación del texto del código de barras** usando Aspose.BarCode. Experimenta con otros valores de `CodeLocation` y opciones de estilo para que coincidan con los requisitos de diseño de tu aplicación.

---

**Last Updated:** 2025-12-27  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}