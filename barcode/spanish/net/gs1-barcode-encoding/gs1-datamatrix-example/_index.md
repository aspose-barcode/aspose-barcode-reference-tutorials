---
date: 2026-02-22
description: Aprenda cómo crear imágenes de códigos de barras en C# usando Aspose.BarCode
  para .NET y generar códigos de barras GS1 DataMatrix de forma rápida y eficiente.
linktitle: GS1 DataMatrix Example
second_title: Aspose.BarCode .NET API
title: Crear imagen de código de barras C# – Ejemplo de GS1 DataMatrix
url: /es/net/gs1-barcode-encoding/gs1-datamatrix-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ejemplo de GS1 DataMatrix

Si busca una manera confiable de **create barcode image C#** en sus aplicaciones .NET, Aspose.BarCode for .NET hace que el proceso sea sencillo. Esta potente biblioteca admite una amplia gama de simbologías, incluido GS1 DataMatrix, y proporciona una API limpia que le permite centrarse en la lógica de negocio en lugar de los detalles de bajo nivel del código de barras. En los próximos minutos, recorreremos un ejemplo completo y práctico que le muestra cómo generar un código de barras GS1 DataMatrix, personalizar su apariencia y guardarlo como un archivo de imagen.

## Respuestas rápidas
- **¿Qué genera el ejemplo?** Un código de barras GS1 DataMatrix que contiene datos de producto de ejemplo.  
- **¿Qué biblioteca se utiliza?** Aspose.BarCode for .NET.  
- **¿Puedo cambiar el formato de salida?** Sí, puede guardarlo como PNG, JPEG, BMP, etc.  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita funciona para pruebas; se requiere una licencia comercial para producción.  
- **¿El código es compatible con .NET Core?** Absolutamente: la misma API funciona en .NET Framework y .NET Core/5/6.

## ¿Qué es un código de barras GS1 DataMatrix?

Un GS1 DataMatrix es un código de barras bidimensional que codifica información a nivel de producto (como GTIN, número de serie y identificadores de aplicación adicionales). Se utiliza ampliamente en el comercio minorista, la salud y la logística para un almacenamiento de datos compacto y de alta densidad.

## ¿Por qué usar Aspose.BarCode para crear barcode image C#?

- **API completa** – admite estándares GS1, corrección de errores y control de tamaño.  
- **Sin dependencias externas** – biblioteca .NET pura, fácil de integrar.  
- **Multiplataforma** – funciona en Windows, Linux y macOS.  
- **Documentación extensa** – incluye ejemplos como este para que comience rápidamente.

## Requisitos previos

Antes de sumergirnos en el tutorial, asegúrese de que tiene los siguientes requisitos previos:

1. **Aspose.BarCode for .NET** – Necesita tener Aspose.BarCode for .NET instalado. Si aún no lo ha hecho, puede [descargarlo aquí](https://releases.aspose.com/barcode/net/).  
2. **Entorno de desarrollo** – Debe tener un entorno de desarrollo .NET configurado en su sistema (Visual Studio, VS Code o cualquier IDE que prefiera).

Ahora que tiene los requisitos previos listos, comencemos a generar códigos de barras GS1 DataMatrix.

## Importar espacios de nombres

Primero, importe los espacios de nombres necesarios para trabajar con Aspose.BarCode for .NET. Estos espacios de nombres le dan acceso a las capacidades de generación de códigos de barras.

```csharp
using Aspose.BarCode;
using System;
```

## Cómo crear barcode image C# – Guía paso a paso

### Paso 1: Configurar el generador de códigos de barras

Para comenzar, cree una instancia de `BarcodeGenerator` y especifique la simbología **GS1 DataMatrix** junto con los datos que desea codificar. En este ejemplo codificamos la cadena **"(01)12345678901231(21)ASPOSE(30)9876"**, que sigue el formato de Identificador de Aplicación GS1.

```csharp
// The path to the documents directory.
string path = "Your Directory Path";
System.Console.WriteLine("Gs1DataMatrixExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1DataMatrix, "(01)12345678901231(21)ASPOSE(30)9876");
```

*Consejo profesional:* Reemplace los datos de ejemplo con sus propios identificadores GS1 para adaptarlos a su catálogo de productos.

### Paso 2: Personalizar las propiedades del código de barras

Puede adaptar la apariencia del código de barras usando el objeto `Parameters`. Aquí establecemos la X‑dimension (el tamaño del módulo más pequeño) a 8 píxeles, y definimos un tamaño de matriz de 36 columnas por 12 filas. Ajuste estos valores para cumplir con sus requisitos de escaneo.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 8;
gen.Parameters.Barcode.DataMatrix.Columns = 36;
gen.Parameters.Barcode.DataMatrix.Rows = 12;
```

*¿Por qué ajustar la X‑dimension?* Una X‑dimension mayor facilita la lectura del código de barras en dispositivos de baja resolución, mientras que un valor menor reduce el tamaño de la imagen.

### Paso 3: Guardar la imagen del código de barras

Finalmente, guarde el código de barras generado en disco. El ejemplo usa PNG, pero puede elegir entre JPEG, GIF, BMP y otros formatos compatibles con Aspose.BarCode.

```csharp
gen.Save($"{path}Gs1DataMatrixExample.png", BarCodeImageFormat.Png);
```

Al ejecutar el código, encontrará **Gs1DataMatrixExample.png** en la carpeta especificada, listo para usarse en etiquetas, empaques o aplicaciones digitales.

## Casos de uso comunes

- **Etiquetado de productos minoristas** – Codifique GTIN, números de lote y fechas de caducidad.  
- **Seguimiento farmacéutico** – Cumpla con los requisitos regulatorios con datos compatibles con GS1.  
- **Logística de almacén** – Almacene de forma compacta la información de ubicación e inventario.  

## Solución de problemas y consejos

- **Formato de datos incorrecto** – Asegúrese de que su cadena siga la sintaxis del Identificador de Aplicación GS1; de lo contrario, el código de barras puede no ser legible.  
- **Problemas de tamaño de imagen** – Si la imagen generada se ve borrosa, aumente el valor de `XDimension.Pixels`.  
- **Errores de licencia** – Una licencia de prueba funciona para evaluación, pero se requiere una licencia completa para implementaciones en producción.

## Preguntas frecuentes

### ¿Qué es GS1 DataMatrix?
GS1 DataMatrix es una simbología de código de barras bidimensional utilizada para codificar datos relacionados con productos y su identificación, particularmente en las industrias minorista y de la salud.

### ¿Aspose.BarCode for .NET es adecuado para otros tipos de códigos de barras?
Sí, Aspose.BarCode for .NET admite una amplia gama de tipos de códigos de barras, lo que lo hace versátil para diferentes aplicaciones.

### ¿Puedo generar códigos de barras en otros formatos de imagen además de PNG?
Sí, Aspose.BarCode for .NET le permite guardar los códigos de barras generados en varios formatos de imagen, como JPEG, GIF y BMP, además de PNG.

### ¿Necesito una licencia para usar Aspose.BarCode for .NET?
Sí, se requiere una licencia válida para el uso comercial de Aspose.BarCode for .NET. Puede obtener una licencia en el [sitio web de Aspose](https://purchase.aspose.com/buy).

### ¿Dónde puedo obtener soporte para Aspose.BarCode for .NET?
Puede encontrar respuestas a sus preguntas y solicitar soporte en el [foro de Aspose.BarCode for .NET](https://forum.aspose.com/c/barcode/13).

## Preguntas frecuentes adicionales (optimizado por IA)

**P: ¿Cómo genero un código de barras DataMatrix en C# sin formato GS1?**  
R: Use `EncodeTypes.DataMatrix` en lugar de `EncodeTypes.GS1DataMatrix` y proporcione la cadena de datos simple al `BarcodeGenerator`.

**P: ¿Puedo cambiar los colores del código de barras programáticamente?**  
R: Sí, establezca `gen.Parameters.Barcode.ForeColor` y `gen.Parameters.Barcode.BackColor` para personalizar los colores de primer plano y de fondo.

**P: ¿Es posible incrustar el código de barras generado directamente en un PDF?**  
R: Absolutamente: recupere el código de barras como un `System.Drawing.Image` y añádalo a un PDF usando Aspose.PDF o cualquier otra biblioteca PDF.

**P: ¿Qué versiones de .NET son compatibles?**  
R: Aspose.BarCode for .NET es compatible con .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6 y versiones posteriores.

**P: ¿Cómo puedo mejorar la fiabilidad de escaneo para etiquetas pequeñas?**  
R: Aumente la X‑dimension, añada zonas silenciosas (`gen.Parameters.Barcode.Margin`) y asegúrese de que haya suficiente contraste entre el código de barras y el fondo.

## Conclusión

En este tutorial, exploramos cómo **create barcode image C#** usando Aspose.BarCode for .NET para generar un código de barras GS1 DataMatrix. Con solo unas pocas líneas de código puede incrustar códigos de barras de alta calidad en sus aplicaciones, ya sea que esté construyendo soluciones minoristas, sistemas de salud o plataformas logísticas. Explore la biblioteca más a fondo para descubrir simbologías adicionales, opciones avanzadas de renderizado y escenarios de integración.

Para obtener más información y documentación detallada, consulte la [documentación de Aspose.BarCode for .NET](https://reference.aspose.com/barcode/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2026-02-22  
**Probado con:** Aspose.BarCode for .NET (latest version)  
**Autor:** Aspose  

---