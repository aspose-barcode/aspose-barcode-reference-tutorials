---
title: Configuración del código unidimensional 128
linktitle: Configuración del código unidimensional 128
second_title: API Aspose.BarCode .NET
description: Aprenda a generar códigos de barras Code 128 unidimensionales en .NET usando Aspose.BarCode. Siga nuestra guía paso a paso para una integración perfecta de códigos de barras.
type: docs
weight: 10
url: /es/net/one-dimensional-barcode-types/one-dimensional-code-128-configuration/
---

Si es un desarrollador de .NET y busca una herramienta poderosa para generar códigos de barras en sus aplicaciones, Aspose.BarCode para .NET es su solución preferida. Esta guía completa lo guiará a través del proceso de aprovechar las capacidades de Aspose.BarCode para .NET para crear códigos de barras Code 128 unidimensionales, y está diseñada tanto para principiantes como para desarrolladores experimentados. 

## Requisitos previos

Antes de sumergirnos en el apasionante mundo de la generación de códigos de barras con Aspose.BarCode, asegúrese de cumplir con los siguientes requisitos previos:

1. Visual Studio: asegúrese de tener Visual Studio instalado en su sistema.

2.  Aspose.BarCode para .NET: deberá descargar e instalar Aspose.BarCode para .NET. Puedes obtenerlo de[aquí](https://releases.aspose.com/barcode/net/).

3. Su proyecto .NET: debe tener un proyecto .NET configurado y listo para integrar la generación de códigos de barras.

¡Ahora comencemos!

## Importar espacios de nombres

El primer paso es importar los espacios de nombres necesarios para su proyecto. Estos espacios de nombres le brindarán acceso a las características y funciones de Aspose.BarCode.

### Paso 1: importar los espacios de nombres

```csharp
using Aspose.BarCode.Generation;
```

## Configuración del código unidimensional 128

Ahora, creemos códigos de barras Code 128 usando Aspose.BarCode para .NET. Revisaremos cada paso en detalle, asegurándonos de que tenga una comprensión clara del proceso.

### Paso 2: establecer el camino

Primero, establezca la ruta al directorio donde desea guardar las imágenes de códigos de barras generadas.

```csharp
string path = "Your Directory Path";
```

### Paso 3: cree un generador de códigos de barras Code 128

 Crear un`BarcodeGenerator` instancia para generar códigos de barras Código 128. Puede especificar el tipo de código de barras que desea generar (en este caso, Código 128) y el valor que desea codificar.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code128, "CODE");
```

### Paso 4: configurar los parámetros del código de barras

Antes de generar el código de barras, puedes configurar varios parámetros. Por ejemplo, puede optar por mostrar u ocultar la suma de comprobación.

#### Opción 1: no mostrar suma de verificación

```csharp
gen.Parameters.Barcode.ChecksumAlwaysShow = false;
```

#### Opción 2: Mostrar suma de verificación

```csharp
gen.Parameters.Barcode.ChecksumAlwaysShow = true;
```

### Paso 5: guarde la imagen del código de barras

Ahora es el momento de guardar la imagen del código de barras generada en el directorio especificado. Puede guardar el código de barras con o sin suma de verificación, según la configuración que eligió en el paso anterior.

#### Guardar código de barras sin suma de comprobación

```csharp
gen.Save($"{path}OneCSCode128NotShowChecksum.png", BarCodeImageFormat.Png);
```

#### Guardar código de barras con suma de comprobación

```csharp
gen.Save($"{path}OneCSCode128ShowChecksum.png", BarCodeImageFormat.Png);
```

¡Eso es todo! Ha generado con éxito códigos de barras Código 128 unidimensionales utilizando Aspose.BarCode para .NET. Puede utilizar estos códigos de barras en diversas aplicaciones, como gestión de inventario, etiquetado de productos y más.

## Conclusión

Aspose.BarCode para .NET proporciona una solución potente y fácil de usar para la generación de códigos de barras en aplicaciones .NET. Con su API intuitiva y su extensa documentación, puede integrar fácilmente la funcionalidad de códigos de barras en sus proyectos. Ya sea que necesite crear códigos de barras unidimensionales o bidimensionales, Aspose.BarCode lo tiene cubierto.

Incorpore Aspose.BarCode a sus aplicaciones .NET hoy y optimice sus procesos de generación de códigos de barras con facilidad.

### Preguntas frecuentes

### ¿Aspose.BarCode para .NET es compatible con .NET Core?
Sí, Aspose.BarCode para .NET es compatible tanto con .NET Framework como con .NET Core.

### ¿Puedo personalizar la apariencia de los códigos de barras generados?
¡Absolutamente! Aspose.BarCode le permite personalizar varios aspectos del código de barras, incluido el tamaño, el color y la ubicación del texto.

### ¿Aspose.BarCode es adecuado para generar códigos QR?
Si bien Aspose.BarCode se centra principalmente en códigos de barras unidimensionales, también puede utilizar Aspose.BarCode para .NET para generar códigos QR.

### ¿Hay una prueba gratuita disponible?
 Sí, puedes probar Aspose.BarCode para .NET gratis descargando la versión de prueba.[aquí](https://releases.aspose.com/).

### ¿Dónde puedo obtener soporte para Aspose.BarCode para .NET?
 Puede buscar ayuda y compartir sus experiencias en el foro Aspose.BarCode para .NET[aquí](https://forum.aspose.com/c/barcode/13).
