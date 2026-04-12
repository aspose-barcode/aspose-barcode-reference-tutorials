---
date: 2026-04-12
description: Aprende a crear códigos de barras Code128 con barras vacías en Java usando
  Aspose.BarCode. Esta guía te muestra cómo generar imágenes de códigos de barras
  en Java rápidamente.
keywords:
- create code128 barcode
- generate barcode java
- barcode generator java example
- java generate barcode image
linktitle: Generando código de barras con barras vacías
second_title: Aspose.BarCode Java API
title: Cómo crear un código de barras Code128 con barras vacías en Java
url: /es/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un código de barras Code128 con barras vacías en Java

## Introducción

Integrar la generación de códigos de barras en aplicaciones Java es un requisito frecuente, ya sea que estés construyendo sistemas de inventario, plataformas de tickets o soluciones de punto de venta. Con **Aspose.BarCode for Java**, puedes **crear imágenes de código de barras Code128** en solo unas pocas líneas de código. En este tutorial recorreremos los pasos para **generar imágenes de código de barras Java** que presentan barras vacías (no rellenas), dándote control total sobre el estilo visual del código de barras.

## Respuestas rápidas
- **¿Qué biblioteca?** Aspose.BarCode for Java  
- **Caso de uso principal?** Crear códigos de barras Code128 con barras vacías para diseños de UI personalizados  
- **¿Requisitos previos?** Java JDK 8+, Aspose.BarCode JAR, acceso de escritura a una carpeta para la imagen de salida  
- **¿Tiempo típico de implementación?** 5‑10 minutos para un ejemplo básico  
- **¿Puedo personalizar colores?** Sí – la API ofrece amplias opciones de estilo  

## ¿Qué es un código de barras Code128?

Code128 es una simbología de código de barras lineal de alta densidad que codifica el conjunto completo de caracteres ASCII. Se usa ampliamente en logística, envíos y comercio minorista porque puede representar datos alfanuméricos de forma compacta. Por defecto, Aspose.BarCode representa las barras Code128 como rectángulos sólidos; establecer la propiedad **FilledBars** a `false` las convierte en barras vacías (contorno), lo cual es útil para la marca estilística.

## ¿Por qué usar Aspose.BarCode para Java?

- **Rich feature set** – soporta más de 50 tipos de códigos de barras, incluidos QR, DataMatrix y PDF417.  
- **No external dependencies** – un solo JAR funciona en cualquier entorno Java.  
- **Fine‑grained control** – puedes ajustar el ancho de barra, colores, fuentes y la propiedad `FilledBars`.  
- **Cross‑platform** – funciona en Windows, Linux y macOS sin bibliotecas nativas.  

## Requisitos previos

Antes de comenzar, asegúrate de tener:

1. **Entorno de desarrollo Java** – JDK 8 o posterior instalado y `JAVA_HOME` configurado.  
2. **Aspose.BarCode for Java** – descarga el último JAR desde la [página de descarga](https://releases.aspose.com/barcode/java/).  
3. **Directorio de documentos** – una carpeta en tu computadora donde se guardará la imagen del código de barras generado.  

## Importar paquetes

En tu proyecto Java, importa las clases que necesitarás para trabajar con Aspose.BarCode:

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

Estas importaciones te dan acceso al generador de códigos de barras, la enumeración de formatos de imagen y el manejo de excepciones.

## Paso 1: Configurar el directorio de recursos

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Reemplaza `"Your Document Directory"` con la ruta absoluta a la carpeta que creaste en los requisitos previos. Aquí es donde se escribirá el archivo PNG.

## Paso 2: Crear una instancia del generador de código de barras Code128

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

Aquí instanciamos `BarcodeGenerator` con la simbología **CODE_128** y el texto de muestra `"TEXT"`. Este es un **ejemplo de generador de códigos de barras Java** que puedes adaptar a cualquier cadena que necesites codificar.

## Paso 3: Establecer la propiedad FilledBars a false

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

Al establecer `FilledBars` a `false`, el código de barras generado mostrará barras vacías en lugar de sólidas, logrando el efecto visual que buscamos.

## Paso 4: Guardar la imagen del código de barras

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

El método `save` escribe el código de barras en el directorio especificado en formato PNG. Puedes cambiar `BarCodeImageFormat.PNG` a `JPG`, `BMP` o `TIFF` si se requiere un tipo de imagen diferente.

## Casos de uso comunes

- **Custom branding** – las barras vacías pueden superponerse con patrones o colores de fondo.  
- **Print‑ready assets** – genera PNG de alta resolución para incluir en facturas o etiquetas de envío.  
- **Dynamic generation** – crea códigos de barras al instante en servicios web o aplicaciones de escritorio.  

## Consejos de solución de problemas

- **Invalid path** – asegúrate de que `dataDir` termine con un separador de archivos (`/` o `\\`) o concatena usando `File.separator`.  
- **License required** – una versión de prueba funciona para evaluación, pero se necesita una licencia completa para producción.  
- **Unsupported characters** – Code128 soporta el conjunto completo de ASCII; evita caracteres Unicode a menos que cambies a una simbología diferente.  

## Conclusión

Ahora has aprendido cómo **crear imágenes de código de barras Code128** con barras vacías usando Aspose.BarCode for Java. Este enfoque sencillo te permite generar gráficos de códigos de barras personalizables rápidamente, ya sea que estés construyendo una herramienta de inventario de escritorio o una API basada en la nube.

## Preguntas frecuentes

### ¿Es Aspose.BarCode compatible con todos los entornos de desarrollo Java?
Sí, Aspose.BarCode está diseñado para integrarse sin problemas con cualquier IDE o sistema de compilación Java, incluidos Maven, Gradle y proyectos JAR simples.

### ¿Puedo personalizar la apariencia del código de barras generado?
¡Absolutamente! Además de `FilledBars`, puedes modificar colores, ancho de barra, márgenes e incluso agregar texto legible por humanos usando la amplia API.

### ¿Está disponible una versión de prueba de Aspose.BarCode?
Sí, puedes explorar las capacidades de Aspose.BarCode obteniendo una prueba gratuita [aquí](https://releases.aspose.com/).

### ¿Cómo puedo obtener soporte para Aspose.BarCode?
Para cualquier consulta o asistencia, visita el [foro de Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

### ¿Dónde puedo encontrar documentación detallada de Aspose.BarCode?
La documentación completa está disponible [aquí](https://reference.aspose.com/barcode/java/).

**Preguntas adicionales**

**P: ¿Cómo generar una imagen de código de barras en un formato diferente, como JPEG?**  
R: Cambia el segundo argumento de `save` a `BarCodeImageFormat.JPEG`.

**P: ¿Puedo generar varios códigos de barras en un bucle?**  
R: Sí – instancia un nuevo `BarcodeGenerator` dentro de tu bucle o reutiliza la misma instancia con un nuevo `CodeText`.

**Última actualización:** 2026-04-12  
**Probado con:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}