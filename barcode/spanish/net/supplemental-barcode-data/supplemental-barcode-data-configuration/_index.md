---
title: Creación de datos de códigos de barras complementarios con Aspose.BarCode para .NET
linktitle: Configuración de datos de códigos de barras suplementarios
second_title: API Aspose.BarCode .NET
description: Genere datos de códigos de barras complementarios con Aspose.BarCode para .NET. Personalice códigos de barras EAN-2 y EAN-5 sin esfuerzo. Guía paso a paso para desarrolladores .NET.
weight: 10
url: /es/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Creación de datos de códigos de barras complementarios con Aspose.BarCode para .NET


En el mundo de la generación y personalización de códigos de barras, Aspose.BarCode para .NET se destaca como una herramienta potente y versátil. Si es un desarrollador experimentado o recién está comenzando, esta guía paso a paso lo guiará a través del proceso de configuración de datos de códigos de barras complementarios utilizando Aspose.BarCode para .NET. 

## Requisitos previos

Antes de sumergirnos en el mundo de los datos de códigos de barras complementarios, asegúrese de cumplir con los siguientes requisitos previos:

- Un entorno de desarrollo configurado con Visual Studio o cualquier otra herramienta de desarrollo .NET.
-  Una copia de Aspose.BarCode para .NET. Si aún no lo has hecho, puedes descargarlo.[aquí](https://releases.aspose.com/barcode/net/).
- Conocimientos básicos de programación en C#.
- Un directorio donde puede guardar las imágenes de códigos de barras generadas.

## Importando espacios de nombres

Primero, asegúrese de tener incluidos los espacios de nombres necesarios en su código C# para trabajar con Aspose.BarCode para .NET. Importe los espacios de nombres requeridos al comienzo de su archivo C#:

```csharp
using Aspose.BarCode.Generation;
```

Ahora, dividamos el proceso de configuración de datos de códigos de barras complementarios en varios pasos.

## Paso 1: configurar la ruta del directorio

 En su código C#, defina la ruta al directorio donde desea guardar las imágenes de códigos de barras generadas. Reemplazar`"Your Directory Path"` con la ruta de su directorio real.

```csharp
string path = "Your Directory Path";
```

## Paso 2: crear un generador de códigos de barras

 Crear una instancia de`BarcodeGenerator` especificando el tipo de código de barras y los datos que desea codificar. En este ejemplo, utilizamos un código de barras EAN-13 con los datos "1234567890128".

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

## Paso 3: Personalización de las dimensiones del código de barras

Establezca las dimensiones del código de barras, como la dimensión X (el ancho del elemento más pequeño del código de barras) y el espacio suplementario. En este ejemplo, configuramos la dimensión X en 2 píxeles y el espacio suplementario en 20 píxeles.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

## Paso 4: Configurar el Suplemento EAN-2

Para configurar un código de barras suplementario EAN-2, establezca los datos suplementarios en el valor deseado. En este caso, lo configuramos en "12". 

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

## Paso 5: guardar la imagen del código de barras

Guarde la imagen del código de barras generada en su directorio especificado con un nombre significativo. En este ejemplo, guardamos el código de barras suplementario EAN-2 como "SupplementEAN2.png".

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

## Paso 6: Configurar el Suplemento EAN-5

 Para configurar un código de barras suplementario EAN-5, simplemente cambie el`SupplementData` a su valor deseado. Aquí lo configuramos en "12345".

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

## Paso 7: Guardar la imagen del código de barras (EAN-5)

Finalmente, guarde la imagen del código de barras suplementario EAN-5 en su directorio especificado. En este caso lo guardamos como "SupplementEAN5.png".

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

Ahora, ha configurado y generado con éxito datos de códigos de barras complementarios utilizando Aspose.BarCode para .NET. Puede utilizar este enfoque para crear una amplia gama de tipos de códigos de barras con distintos datos complementarios.

## Conclusión

Aspose.BarCode para .NET es una poderosa herramienta para la generación y personalización de códigos de barras. En esta guía, recorrimos paso a paso el proceso de configuración y generación de datos de códigos de barras complementarios. Con los requisitos previos correctos y un poco de codificación, puede trabajar de manera eficiente con datos de códigos de barras y satisfacer sus necesidades específicas.

 Para obtener más información y uso avanzado, consulte la[Aspose.BarCode para la documentación de .NET](https://reference.aspose.com/barcode/net/).

## Preguntas frecuentes

### ¿Puedo usar Aspose.BarCode para .NET en mi proyecto .NET Core?
Sí, Aspose.BarCode para .NET es compatible con .NET Core.

### ¿Hay una prueba gratuita disponible para Aspose.BarCode para .NET?
 Sí, puedes probarlo gratis visitando[este enlace](https://releases.aspose.com/).

### ¿Dónde puedo obtener una licencia temporal de Aspose.BarCode para .NET?
 Puede obtener una licencia temporal de[este enlace](https://purchase.aspose.com/temporary-license/).

### ¿Aspose.BarCode admite una amplia gama de tipos de códigos de barras?
Sí, admite varios tipos de códigos de barras, incluidos EAN-13, Código QR, Código 128 y más.

### ¿Puedo personalizar la apariencia de los códigos de barras generados?
Por supuesto, puede personalizar las dimensiones, los colores y otros aspectos de los códigos de barras para satisfacer sus necesidades.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
