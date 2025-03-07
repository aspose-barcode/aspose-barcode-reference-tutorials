---
title: Configuración unidimensional de relación ancha-estrecha
linktitle: Configuración unidimensional de relación ancha-estrecha
second_title: API Aspose.BarCode .NET
description: Genere códigos de barras personalizados fácilmente con Aspose.BarCode para .NET. Guía paso a paso para la configuración unidimensional de relación ancha-estrecha.
weight: 22
url: /es/net/one-dimensional-barcode-types/one-dimensional-wide-narrow-ratio-configuration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configuración unidimensional de relación ancha-estrecha


¿Está buscando generar y personalizar códigos de barras sin esfuerzo en sus aplicaciones .NET? ¡No busque más! Aspose.BarCode para .NET es una biblioteca sólida que facilita la generación y personalización de códigos de barras. En esta guía paso a paso, profundizaremos en cómo aprovechar el poder de Aspose.BarCode para .NET para crear códigos de barras con una configuración de relación amplia-estrecha.

## Requisitos previos

Antes de sumergirnos en el mundo de los códigos de barras con Aspose.BarCode para .NET, debe cumplir con los siguientes requisitos previos:

### 1. Entorno de Visual Studio
   - Asegúrese de tener Visual Studio instalado en su sistema para trabajar con aplicaciones .NET.
   
### 2. Aspose.BarCode para la biblioteca .NET
   -  Debe tener instalada la biblioteca Aspose.BarCode para .NET. Puedes descargarlo desde el[sitio web](https://releases.aspose.com/barcode/net/).

### 3. Clave de licencia (opcional)
   -  Si tiene una clave de licencia, puede usarla para desbloquear funciones adicionales de la biblioteca. Puede obtener una licencia temporal de[aquí](https://purchase.aspose.com/temporary-license/).

Ahora que tiene los requisitos previos implementados, pasemos a crear códigos de barras unidimensionales con una configuración de proporción ancha y estrecha usando Aspose.BarCode para .NET.

## Importar espacios de nombres

Primero, debe incluir los espacios de nombres necesarios en su proyecto para acceder a las funciones de Aspose.BarCode para .NET. Puede hacer esto agregando lo siguiente usando declaraciones en la parte superior de su código:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Paso 1: Defina la ruta de su directorio

Comience definiendo la ruta donde desea guardar las imágenes de códigos de barras generadas. Puedes hacer esto con el siguiente código:

```csharp
string path = "Your Directory Path";
```

 Reemplazar`"Your Directory Path"` con la ruta del directorio real donde desea guardar las imágenes de códigos de barras.

## Paso 2: cree un código de barras unidimensional de relación ancha-estrecha

Ahora, creemos un código de barras unidimensional con una configuración de proporción ancha y estrecha usando Aspose.BarCode para .NET. En este ejemplo, usaremos el tipo de codificación Code39Extended y estableceremos los datos en "ASPOSE".

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code39Extended, "ASPOSE");
```

Esta línea de código inicializa un generador de códigos de barras con el tipo de codificación y los datos especificados.

## Paso 3: Establecer la relación ancha/estrecha

La relación ancho-estrecho determina la relación entre elementos anchos y estrechos en el código de barras. En este paso, estableceremos la relación ancho-estrecho en 2:

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 2;
```

Y luego, guardaremos la imagen del código de barras generada en la ruta especificada:

```csharp
gen.Save($"{path}WideNarrow2Code39.png", BarCodeImageFormat.Png);
```

## Paso 4: ajustar la relación ancho-estrecho

Puede experimentar con diferentes proporciones anchas y estrechas para lograr la apariencia de código de barras deseada. Por ejemplo, si desea un código de barras más ancho, establezca la proporción ancho-estrecho en 5:

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 5;
```

Y guarde la imagen del código de barras:

```csharp
gen.Save($"{path}WideNarrow5Code39.png", BarCodeImageFormat.Png);
```

Ahora ha creado con éxito códigos de barras unidimensionales con diferentes proporciones anchas y estrechas utilizando Aspose.BarCode para .NET. Esta biblioteca le brinda la flexibilidad de generar códigos de barras adaptados a sus requisitos específicos.

## Conclusión

Aspose.BarCode para .NET es una biblioteca versátil que simplifica la generación y personalización de códigos de barras en sus aplicaciones .NET. En este tutorial, cubrimos los conceptos básicos de la creación de códigos de barras unidimensionales con una configuración de relación ancha-estrecha. Con la capacidad de ajustar varios parámetros, puede crear códigos de barras que se adapten perfectamente a sus necesidades.

## Preguntas frecuentes

### 1. ¿Cómo puedo obtener una licencia de Aspose.BarCode para .NET?
 Puede adquirir una licencia en el[Aspose sitio web](https://purchase.aspose.com/buy).

### 2. ¿Puedo utilizar Aspose.BarCode para .NET sin licencia?
Sí, puede usarlo con una licencia temporal, que proporciona una funcionalidad limitada.

### 3. ¿Aspose.BarCode para .NET es compatible con .NET Core?
Sí, Aspose.BarCode para .NET es compatible con .NET Core y .NET Framework.

### 4. ¿Existe alguna limitación en los tipos de códigos de barras que puedo generar?
Aspose.BarCode para .NET admite una amplia gama de simbologías de códigos de barras, incluidos el código QR, el código 39 y muchos más.

### 5. ¿Cómo puedo obtener soporte o hacer preguntas sobre Aspose.BarCode para .NET?
 Puedes visitar el[Foro Aspose.BarCode](https://forum.aspose.com/c/barcode/13) para apoyo y discusiones.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
