---
title: Genere códigos de barras DataMatrix con Aspose.BarCode para .NET
linktitle: Versiones de DataMatrix
second_title: API Aspose.BarCode .NET
description: Aprenda a generar códigos de barras DataMatrix en .NET usando Aspose.BarCode para .NET. Dimensiones personalizadas, soporte ECC y más.
weight: 12
url: /es/net/datamatrix-barcode-reading/datamatrix-versions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Genere códigos de barras DataMatrix con Aspose.BarCode para .NET

Si está buscando una solución confiable para generar códigos de barras DataMatrix en sus aplicaciones .NET, Aspose.BarCode para .NET es el camino a seguir. En esta guía paso a paso, lo guiaremos a través del proceso de uso de Aspose.BarCode para .NET para crear códigos de barras DataMatrix. Dividiremos cada ejemplo en varios pasos, asegurándonos de que pueda seguirlo con facilidad.

## Requisitos previos

Antes de profundizar en el código, asegúrese de cumplir con los siguientes requisitos previos:
- Un entorno de desarrollo con soporte .NET.
-  Una copia de Aspose.BarCode para .NET, que puede descargar desde[este enlace](https://releases.aspose.com/barcode/net/).
- Conocimientos básicos de C# y el framework .NET.

Ahora, exploremos las versiones de DataMatrix y cómo generarlas usando Aspose.BarCode para .NET.

## Importar espacios de nombres

En cualquier proyecto de C#, es esencial importar los espacios de nombres necesarios. En el caso de Aspose.BarCode, deberá incluir lo siguiente:

```csharp
using Aspose.BarCode.Generation;
```

 Este espacio de nombres proporciona acceso a la`BarcodeGenerator` clase, que es crucial para generar códigos de barras.

Ahora, dividamos el ejemplo en varios pasos.

## Paso 1: configure la ruta de su directorio

Comience definiendo la ruta del directorio donde desea guardar los códigos de barras DataMatrix generados.

```csharp
string path = "Your Directory Path";
```

 Reemplazar`"Your Directory Path"` con la ruta real donde desea guardar las imágenes de códigos de barras.

## Paso 2: Inicialice el generador de códigos de barras

 Crear una instancia del`BarcodeGenerator` clase y especifique el tipo de código de barras como`DataMatrix`. También puede proporcionar los datos que desea codificar dentro del código de barras.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // El código para generar códigos de barras va aquí.
}
```

## Paso 3: configurar las propiedades del código de barras

Puede personalizar varias propiedades del código de barras DataMatrix, como sus dimensiones y el tipo ECC (código de corrección de errores). A continuación se muestra un ejemplo de cómo configurar la dimensión X en 4 píxeles y elegir ECC200:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4;
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

## Paso 4: configurar la versión de DataMatrix y guardar

Puede especificar la versión de DataMatrix configurando el número de filas y columnas. Después de configurar la versión, guarde la imagen del código de barras.

Por ejemplo, para crear un código de barras DataMatrix con 22 filas y 22 columnas usando ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC200_22x22;
generator.Save($"{path}DataMatrixRows22Columns22Ecc200.png", BarCodeImageFormat.Png);
```

De manera similar, puede generar un código de barras con diferentes parámetros cambiando la versión y el tipo de ECC según sea necesario.

## Paso 5: repita para otras versiones

Puede repetir el Paso 4 para otras versiones de DataMatrix. Por ejemplo, para crear un código de barras con 12 filas y 64 columnas usando ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.DMRE_12x64;
generator.Save($"{path}DataMatrixRows12Columns64Ecc200.png", BarCodeImageFormat.Png);
```

## Paso 6: cambiar los tipos de ECC

Si desea cambiar el tipo de ECC a Ecc140, puede hacerlo actualizando la propiedad ECC:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;
```

## Paso 7: Genere códigos de barras con diferentes versiones y ECC

Repita el Paso 4 para otras versiones de DataMatrix y tipos de ECC, guardando cada código de barras con un nombre de archivo único.

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC000_140_29x29;
generator.Save($"{path}DataMatrixRows29Columns29Ecc140.png", BarCodeImageFormat.Png);
```

Ahora que ha aprendido cómo generar códigos de barras DataMatrix utilizando Aspose.BarCode para .NET, puede integrar fácilmente esta funcionalidad en sus aplicaciones .NET.

## Conclusión

Aspose.BarCode para .NET simplifica el proceso de generación de códigos de barras DataMatrix en sus aplicaciones .NET. Con esta guía paso a paso, puede crear códigos de barras con diferentes versiones y tipos ECC, ofreciendo flexibilidad y personalización para satisfacer sus necesidades específicas.

 Si tienes alguna pregunta o necesitas ayuda, no dudes en visitar el[Aspose.BarCode para la documentación de .NET](https://reference.aspose.com/barcode/net/) o echa un vistazo a[Foro Aspose.BarCode](https://forum.aspose.com/c/barcode/13) para soporte.

## Preguntas frecuentes

### P1: ¿Qué es ECC en los códigos de barras DataMatrix?

R1: ECC (Código de corrección de errores) es un componente vital de los códigos de barras DataMatrix que ayuda a garantizar la integridad de los datos. Los diferentes niveles de ECC proporcionan distintos grados de corrección de errores.

### P2: ¿Puedo generar códigos de barras DataMatrix con dimensiones personalizadas usando Aspose.BarCode para .NET?

R2: Sí, puede personalizar las dimensiones de los códigos de barras DataMatrix configurando el número de filas y columnas como se muestra en el tutorial.

### P3: ¿Dónde puedo descargar Aspose.BarCode para .NET?

 R3: Puede descargar Aspose.BarCode para .NET desde[este enlace](https://releases.aspose.com/barcode/net/).

### P4: ¿Hay una prueba gratuita disponible para Aspose.BarCode para .NET?

 R4: Sí, puede acceder a una prueba gratuita de Aspose.BarCode para .NET[aquí](https://releases.aspose.com/).

### P5: ¿Cómo puedo obtener una licencia temporal de Aspose.BarCode para .NET?

 R5: Para obtener una licencia temporal de Aspose.BarCode para .NET, visite[este enlace](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
