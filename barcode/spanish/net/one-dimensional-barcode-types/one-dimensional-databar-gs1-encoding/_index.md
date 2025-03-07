---
title: Codificación GS1 de barra de datos unidimensional
linktitle: Codificación GS1 de barra de datos unidimensional
second_title: API Aspose.BarCode .NET
description: Aprenda a crear códigos de barras codificados Databar GS1 en .NET usando Aspose.BarCode. Genere códigos de barras con facilidad. Sigue nuestra guía paso a paso.
weight: 18
url: /es/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Codificación GS1 de barra de datos unidimensional


En este tutorial, lo guiaremos a través del proceso de creación de códigos de barras codificados Databar GS1 unidimensionales utilizando la biblioteca Aspose.BarCode para .NET. Ya sea que esté buscando generar códigos de barras con codificación GS1 o sin ella, lo tenemos cubierto. Esta guía paso a paso lo ayudará a comprender los requisitos previos, importar espacios de nombres y demostrar cada ejemplo para crear códigos de barras codificados Databar GS1 con facilidad.

## Requisitos previos

Antes de profundizar en el código, asegúrese de cumplir con los siguientes requisitos previos:

1.  Aspose.BarCode para .NET: Debe tener instalado Aspose.BarCode para .NET. Si aún no lo has hecho, puedes descargarlo desde[aquí](https://releases.aspose.com/barcode/net/).

2.  Ruta de su directorio: Reemplazar`"Your Directory Path"` en los ejemplos de código con la ruta real donde desea guardar las imágenes de códigos de barras generadas.

Ahora que tiene listos los requisitos previos necesarios, pasemos a la parte de codificación.

## Importando espacios de nombres

Para comenzar, debe importar los espacios de nombres relevantes para Aspose.BarCode. Agregue las siguientes líneas de código al comienzo de su proyecto .NET:

```csharp
using Aspose.BarCode;
using System;
```

## Paso 1: Inicialice el generador de códigos de barras

El primer paso es inicializar el objeto BarcodeGenerator con el tipo de codificación deseado. En este caso, estamos utilizando la codificación Databar Expanded. 

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## Paso 2: Generar un código de barras con codificación GS1

Ahora, configuraremos el texto del código con la verificación GS1Encoding y guardaremos la imagen del código de barras generada. 

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## Paso 3: generar un código de barras de codificación variable

En este paso, generaremos un código de barras con texto de código variable sin verificación de codificación GS1.

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## Paso 4: Manejar la excepción para la verificación de codificación GS1

Si intenta generar un código de barras con texto de código variable con la verificación de codificación GS1 habilitada, se generará una excepción. Así es como puedes manejarlo:

```csharp
try
{
    gen.CodeText = "ASPOSE";
    gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

Ahora ha creado con éxito códigos de barras codificados Databar GS1 unidimensionales con Aspose.BarCode para .NET. Puede explorar y personalizar aún más la generación de códigos de barras según sus requisitos específicos.

## Conclusión

En este tutorial, cubrimos el proceso de generación de códigos de barras codificados Databar GS1 unidimensionales utilizando Aspose.BarCode para .NET. Discutimos los requisitos previos, importamos los espacios de nombres necesarios y brindamos orientación paso a paso para crear códigos de barras codificados con GS1 y con codificación variable.

 Con Aspose.BarCode para .NET, la generación de códigos de barras se convierte en una tarea sencilla y ofrece flexibilidad y control sobre sus necesidades de creación de códigos de barras. Si tiene algún problema o tiene preguntas, no dude en visitar el[Documentación de Aspose.BarCode](https://reference.aspose.com/barcode/net/) o buscar ayuda en el[Foro de soporte de Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

## Preguntas frecuentes

### 1. ¿Qué es la codificación GS1 en códigos de barras?
La codificación GS1 es un estándar utilizado en códigos de barras para garantizar una estructura e identificación de datos adecuadas. Se utiliza comúnmente para artículos de venta minorista, atención médica y logística para facilitar el seguimiento preciso y el intercambio de información.

### 2. ¿Puedo personalizar la apariencia de los códigos de barras generados?
Sí, puedes personalizar la apariencia de los códigos de barras generados con Aspose.BarCode para .NET. Tienes control sobre varios parámetros como tamaño, color y estilo.

### 3. ¿Dónde puedo encontrar recursos y documentación adicionales para Aspose.BarCode?
 Puede encontrar documentación completa y ejemplos en[Documentación de Aspose.BarCode](https://reference.aspose.com/barcode/net/). Es un recurso valioso para aprender y solucionar problemas.

### 4. ¿Existe una versión de prueba disponible para Aspose.BarCode?
 Sí, puede obtener una versión de prueba gratuita de Aspose.BarCode para .NET en[aquí](https://releases.aspose.com/).

### 5. ¿Cómo puedo adquirir una licencia de Aspose.BarCode para .NET?
 Para comprar una licencia de Aspose.BarCode para .NET, visite el[pagina de compra](https://purchase.aspose.com/buy) en el sitio web de Aspose.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
