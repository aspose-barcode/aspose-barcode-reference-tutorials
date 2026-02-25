---
date: 2026-02-25
description: Aprenda cómo generar una imagen de código de barras y guardar el PNG
  del código de barras usando Aspose.BarCode para .NET – un ejemplo completo de Aspose.BarCode.
linktitle: One-Dimensional Code 93 Configuration
second_title: Aspose.BarCode .NET API
title: Generar imagen de código de barras – Code 93 con Aspose.BarCode
url: /es/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/
weight: 12
---

.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generar imagen de código de barras – Código 93 unidimensional con Aspose.BarCode

## Introducción

En la era digital actual, los códigos de barras se han convertido en una parte integral de nuestras vidas, simplificando procesos como la gestión de inventario, el etiquetado de productos y el seguimiento en el punto de venta. **Generar una imagen de código de barras** suele ser el primer paso para integrar estos identificadores en sus aplicaciones. Aspose.BarCode para .NET ofrece una API robusta y fácil de usar que le permite crear códigos de barras Code 93 de alta calidad con solo unas pocas líneas de código C#. Ya sea que esté construyendo un sistema de almacén, una aplicación minorista o una herramienta de informes personalizada, este tutorial le guía a través de un **ejemplo de código de barras Aspose** que muestra cómo generar, personalizar y **guardar archivos PNG de código de barras**.

## Respuestas rápidas
- **¿Qué cubre el tutorial?** Creación y guardado de una imagen de código de barras Code 93 con manejo de suma de verificación.  
- **¿Qué biblioteca se utiliza?** Aspose.BarCode para .NET (última versión estable).  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Puedo cambiar el formato de salida?** Sí – puede guardar como PNG, JPEG, BMP, etc., cambiando el `BarCodeImageFormat`.  
- **¿Cuáles son los requisitos mínimos?** .NET Framework 4.6+ o .NET Core 3.1+ y Visual Studio.

## ¿Qué es un código de barras Code 93?
Code 93 es una simbología alfanumérica de alta densidad que admite el conjunto completo de caracteres ASCII. A menudo se elige por su tamaño compacto y su suma de verificación incorporada, lo que ayuda a garantizar la integridad de los datos durante el escaneo.

## ¿Por qué generar imágenes de códigos de barras con Aspose.BarCode?
- **Control total** sobre el tipo de codificación, suma de verificación, tamaño y formato de imagen.  
- **Sin dependencias externas** – la biblioteca funciona en cualquier plataforma .NET.  
- **Calidad de renderizado excelente**, adecuada tanto para visualización en pantalla como para impresión de alta resolución.  
- **Documentación completa** y un amplio conjunto de ejemplos que aceleran el desarrollo.

## Requisitos previos

Antes de sumergirnos en el código, asegúrese de tener lo siguiente:

1. **Visual Studio** (cualquier edición reciente).  
2. **Aspose.BarCode para .NET** instalado – puede obtenerlo desde la página oficial de descargas.  
3. Familiaridad básica con **C#** y la estructura de proyectos .NET.

Ahora que está listo, pasemos a la guía paso a paso.

## Importar espacios de nombres

Primero, importe los espacios de nombres requeridos para poder acceder a las clases de generación de códigos de barras.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Paso 1: Establecer la ruta del directorio

Defina dónde se guardará la imagen del código de barras generado. Reemplace el marcador de posición con una carpeta válida en su máquina.

```csharp
string path = "Your Directory Path";
```

## Paso 2: Crear un código de barras Code 93 unidimensional

Instancie un `BarcodeGenerator` con el tipo `Code93Extended` y los datos que desea codificar.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code93Extended, "CODE");
```

## Paso 3: Habilitar suma de verificación (Opcional)

Code 93 incluye una suma de verificación por defecto. Puede activarla o desactivarla usando la propiedad `IsChecksumEnabled`.

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
```

## Paso 4: Guardar la imagen del código de barras (Guardar PNG del código de barras)

Genere la imagen y guárdela como un archivo PNG en la carpeta que especificó anteriormente.

```csharp
gen.Save($"{path}OneCSCode93WithChecksum.png", BarCodeImageFormat.Png);
```

## Paso 5: Manejo de excepciones – Generar sin suma de verificación

Si necesita crear un código de barras **sin** suma de verificación, debe manejar las posibles excepciones que puedan surgir.

```csharp
try
{
    gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.No;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### Problemas comunes y soluciones
- **Ruta inválida** – asegúrese de que el directorio exista y la aplicación tenga permisos de escritura.  
- **Caracteres no soportados** – Code 93 admite el conjunto completo de ASCII, pero los caracteres de control pueden causar errores.  
- **Licencia no establecida** – sin una licencia válida, la biblioteca funciona en modo de evaluación y puede añadir una marca de agua.

## Preguntas frecuentes (FAQs)

### P: ¿Dónde puedo encontrar la documentación de Aspose.BarCode para .NET?
A: Puede encontrar la documentación en [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/).

### P: ¿Cómo descargo Aspose.BarCode para .NET?
A: Puede descargar Aspose.BarCode para .NET desde el sitio web en [Aspose.BarCode for .NET Download](https://releases.aspose.com/barcode/net/).

### P: ¿Hay una prueba gratuita disponible para Aspose.BarCode para .NET?
A: Sí, puede obtener una prueba gratuita de Aspose.BarCode para .NET desde [aquí](https://releases.aspose.com/).

### P: ¿Cómo puedo comprar una licencia para Aspose.BarCode para .NET?
A: Puede comprar una licencia en la página de compra en [Aspose.BarCode for .NET Purchase](https://purchase.aspose.com/buy).

### P: ¿Dónde puedo obtener soporte o hacer preguntas sobre Aspose.BarCode para .NET?
A: Puede encontrar un foro comunitario para soporte y discusiones en [Aspose.BarCode for .NET Support](https://forum.aspose.com/c/barcode/13).

---

**Última actualización:** 2026-02-25  
**Probado con:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}