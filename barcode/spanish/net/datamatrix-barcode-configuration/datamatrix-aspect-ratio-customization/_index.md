---
date: 2026-01-12
description: Aprenda a crear PNG de códigos de barras con una relación de aspecto
  personalizada de DataMatrix usando Aspose.BarCode para .NET. Guía paso a paso para
  la generación de códigos de barras y la personalización del tamaño.
linktitle: DataMatrix Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
title: Crear PNG de código de barras – Relación de aspecto DataMatrix – Aspose.BarCode
url: /es/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear PNG de Código de Barras – Relación de Aspecto DataMatrix – Aspose.BarCode

Generar un **barcode PNG** con una relación de aspecto DataMatrix personalizada es un requisito común cuando necesita que el código de barras se ajuste a restricciones de diseño específicas. En este tutorial recorreremos los pasos exactos para **crear barcode PNG** usando Aspose.BarCode para .NET, explicaremos por qué podría querer ajustar la relación de aspecto y le mostraremos cómo afinar la salida para su aplicación.

## Respuestas Rápidas
- **¿Qué controla la “relación de aspecto”?** Define la proporción ancho‑alto de los módulos DataMatrix.  
- **¿Puedo generar PNG, JPEG o SVG?** Sí – el método `Save` admite PNG, JPEG, BMP, GIF y más.  
- **¿Necesito una licencia para esta función?** Una prueba gratuita funciona para desarrollo; se requiere una licencia completa para producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **¿Cuántos valores de relación de aspecto son válidos?** Cualquier número flotante positivo; los valores típicos son 0.5 – 2.0.

## Qué es un código de barras DataMatrix y por qué ajustar su relación de aspecto?
DataMatrix es un código de barras matricial bidimensional que almacena grandes cantidades de datos en un espacio reducido. Ajustar la **relación de aspecto** le permite estirar o comprimir los módulos horizontalmente, lo que puede ser útil para encajar el código de barras en columnas estrechas o etiquetas anchas sin sacrificar la legibilidad.

## Requisitos Previos

Antes de comenzar a personalizar las relaciones de aspecto de DataMatrix, asegúrese de que tiene los siguientes requisitos:

1. **Visual Studio** – cualquier versión reciente servirá.  
2. **Aspose.BarCode for .NET** – descárguelo [aquí](https://releases.aspose.com/barcode/net/).  
3. **.NET Framework / .NET Core** – su proyecto debe dirigirse a una versión compatible.

## Importar Espacios de Nombres

Primero, necesita importar el espacio de nombres necesario en su proyecto C#:

```csharp
using Aspose.BarCode.Generation;
```

> **Consejo profesional:** Mantenga esta declaración `using` en la parte superior de su archivo para que la clase `BarcodeGenerator` esté siempre disponible.

## Guía Paso a Paso

### Paso 1: Configurar su Proyecto
Cree un nuevo proyecto de consola o Windows Forms en Visual Studio y agregue una referencia al DLL de Aspose.BarCode.

### Paso 2: Inicializar un Generador de Código de Barras
Instancie un `BarcodeGenerator` con el tipo DataMatrix y los datos que desea codificar:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> Esta línea crea un generador listo para producir un código de barras DataMatrix que contiene el texto de ejemplo.

### Paso 3: Personalizar la Relación de Aspecto y Guardar Archivos PNG
Ahora puede cambiar la **relación de aspecto** y guardar cada versión como una imagen PNG:

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- La primera llamada crea un código de barras con proporción cuadrada (`AspectRatio = 1`).  
- La segunda llamada comprime el código de barras horizontalmente (`AspectRatio = 0.5`), produciendo una apariencia más ancha.

Ahora tiene dos archivos **barcode PNG** con diferentes relaciones de aspecto listos para usar en informes, etiquetas o elementos de UI.

## Problemas Comunes y Soluciones
| Problema | Solución |
|----------|----------|
| **La imagen generada está borrosa** | Aumente el parámetro `Resolution` antes de guardar (`gen.Parameters.ImageResolution = 300`). |
| **El código de barras no se escanea** | Asegúrese de que la relación de aspecto se mantenga dentro de 0.5 – 2.0 y mantenga una zona silenciosa suficiente (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **Errores de ruta de archivo** | Use `Path.Combine` para construir la ruta de salida y verifique que la carpeta exista. |

## Preguntas Frecuentes

**P: ¿Puedo personalizar la relación de aspecto de otros tipos de códigos de barras usando Aspose.BarCode para .NET?**  
R: Sí, muchos códigos de barras 2‑D (p. ej., QR, PDF417) admiten ajustes de relación de aspecto a través de sus objetos de parámetros específicos.

**P: ¿Hay una prueba gratuita disponible para Aspose.BarCode para .NET?**  
R: Sí, puede acceder a una prueba gratuita de Aspose.BarCode para .NET [aquí](https://releases.aspose.com/).

**P: ¿Dónde puedo comprar una licencia para Aspose.BarCode para .NET?**  
R: Puede comprar una licencia en el sitio web de Aspose [aquí](https://purchase.aspose.com/buy).

**P: ¿Aspose.BarCode para .NET es compatible con diferentes versiones de .NET Framework?**  
R: Sí, funciona con .NET Framework 4.x, .NET Core 3.1+ y las últimas versiones de .NET.

**P: ¿Puedo generar códigos de barras en diferentes formatos con Aspose.BarCode para .NET?**  
R: Absolutamente – PNG, JPEG, BMP, GIF, TIFF, SVG y PDF son compatibles de forma nativa.

## Conclusión

Personalizar la **relación de aspecto** de un código de barras DataMatrix y **crear barcode PNG** es sencillo con Aspose.BarCode para .NET. Siguiendo los pasos anteriores, puede generar códigos de barras de tamaño perfecto que cumplan con los requisitos exactos de diseño de su proyecto. Explore otros parámetros como `Resolution`, `Margin` y `Color` para ajustar aún más la salida.

Para una exploración más profunda, consulte la [documentación](https://reference.aspose.com/barcode/net/) oficial o únase a la comunidad en el [foro de Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Last Updated:** 2026-01-12  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}