---
date: 2025-12-10
description: Aprende a generar códigos de barras con una relación ancha‑estrecha personalizada
  en Java usando Aspose.BarCode y a crear imágenes de códigos de barras de manera
  eficiente. Sigue nuestra guía paso a paso.
linktitle: Configuring Wide-Narrow Ratio
second_title: Aspose.BarCode Java API
title: Cómo generar código de barras con relación ancho‑estrecho en Java
url: /es/java/barcode-configuration/configuring-wide-narrow-ratio/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo generar un código de barras con relación ancho‑estrecho en Java

## Introducción

Si necesita **cómo generar código de barras** con proporciones visuales precisas, ajustar la relación ancho‑estrecho es la clave. En este tutorial le guiaremos a través de un proceso de creación **código de barras paso a paso** usando Aspose.BarCode for Java, mostrándole cómo configurar la relación, generar la imagen del código de barras y **guardar código de barras png** en disco. Ya sea que esté creando etiquetas de inventario, etiquetas de envío o cualquier aplicación que requiera un código de barras CODE_128 con estilo personalizado, encontrará todo lo que necesita aquí mismo.

## Respuestas rápidas
- **¿Qué es la relación ancho‑estrecho?** Controla la anchura relativa de las barras anchas frente a las barras estrechas en un código de barras.  
- **¿Qué simbología admite el ajuste de la relación?** La mayoría de las simbologías 1‑D, incluido CODE_128, permiten establecer una relación personalizada.  
- **¿Necesito una licencia?** Hay una prueba gratuita disponible, pero se requiere una licencia comercial para uso en producción.  
- **¿Puedo generar una imagen de código de barras en formato PNG?** Sí—utilice `generator.save(...)` para generar la imagen del código de barras como PNG.  
- **¿El código es compatible con Java 8+?** Absolutamente; Aspose.BarCode funciona con todas las versiones modernas de Java.

## Requisitos previos

Antes de sumergirnos en el código, asegúrese de tener lo siguiente:

- Java Development Kit (JDK) instalado en su máquina.  
- Biblioteca Aspose.BarCode for Java. Descárguela desde el [download link](https://releases.aspose.com/barcode/java/).

## Importar paquetes

Para comenzar, importe la clase esencial de Aspose.BarCode en su proyecto.

```java
// Import Aspose.BarCode library
import com.aspose.barcode.generation.BarcodeGenerator;
```

## ¿Qué es la relación ancho‑estrecho y por qué ajustarla?

La relación ancho‑estrecho determina cuán gruesas aparecen las barras “anchas” en comparación con las “estrechas”. Ajustar esta relación puede mejorar la legibilidad del escáner, cumplir con estándares de impresión específicos, o simplemente coincidir con el estilo visual de una marca.

## Cómo generar un código de barras con relación ancho‑estrecho en Java

A continuación se muestra una guía **código de barras paso a paso** que lo lleva a través de cada parte del proceso.

### Paso 1: Establecer el directorio del documento

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Asegúrese de que el directorio exista y tenga permisos de escritura; aquí se colocará el archivo **guardar código de barras png**.

### Paso 2: Instanciar el objeto Barcode

```java
// Instantiate barcode object
// Create an instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

Aquí **creamos un código de barras code_128** pasando `EncodeTypes.CODE_128` al constructor.

### Paso 3: Establecer la relación ancho‑estrecho

```java
// Set the wide to narrow ratio for the barcode
generator.getParameters().getBarcode().setWideNarrowRatio(3.0f);
```

El método `setWideNarrowRatio` le permite afinar el espaciado visual. Un valor de `3.0f` significa que la barra ancha es tres veces la anchura de una barra estrecha.

### Paso 4: Guardar la imagen en disco

```java
// Save the image to disk in PNG format
generator.save(dataDir + "wideNarrowRatio.png");
```

Llamar a `save` **generará la imagen del código de barras** y la almacenará como un archivo PNG, completando el paso **guardar código de barras png**.

## Problemas comunes y soluciones

| Problema | Razón | Solución |
|----------|-------|----------|
| El código de barras se ve distorsionado | Relación demasiado alta/baja para la impresora | Ajuste el valor pasado a `setWideNarrowRatio` (p. ej., 2.0‑2.5). |
| Archivo no creado | Ruta `dataDir` inválida o permisos insuficientes | Verifique la ruta del directorio y asegúrese de que la aplicación tenga acceso de escritura. |
| El escáner no puede leer el código de barras | Relación fuera del rango recomendado para la simbología | Use relaciones estándar (2.0‑3.0) o pruebe con el escáner objetivo. |

## Preguntas frecuentes

**P: ¿Puedo usar Aspose.BarCode con otros frameworks de Java?**  
R: Sí, Aspose.BarCode está diseñado para funcionar sin problemas con Spring, Java EE, Android y otros entornos Java.

**P: ¿Cómo puedo generar códigos de barras con diferentes simbologías?**  
R: Simplemente cambie el tipo de simbología en el constructor `BarcodeGenerator`, por ejemplo `EncodeTypes.QR` para códigos QR.

**P: ¿Hay una versión de prueba disponible para Aspose.BarCode?**  
R: Sí, puede acceder a la versión de prueba gratuita [aquí](https://releases.aspose.com/).

**P: ¿Dónde puedo encontrar documentación detallada de Aspose.BarCode?**  
R: Consulte la documentación [aquí](https://reference.aspose.com/barcode/java/).

**P: ¿Cómo obtener soporte para Aspose.BarCode?**  
R: Visite el foro de Aspose.BarCode [aquí](https://forum.aspose.com/c/barcode/13) para soporte y discusiones de la comunidad.

**Última actualización:** 2025-12-10  
**Probado con:** Aspose.BarCode for Java 24.11 (última versión al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}