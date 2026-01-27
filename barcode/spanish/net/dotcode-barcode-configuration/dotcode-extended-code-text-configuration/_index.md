---
date: 2026-01-27
description: 'Aprenda a crear texto de código extendido de dotcode usando Aspose.BarCode
  para .NET: una guía paso a paso para generar códigos de barras DotCode con texto
  de código extendido.'
linktitle: DotCode Extended Code Text Configuration
second_title: Aspose.BarCode .NET API
title: Cómo crear texto de código extendido dotcode con Aspose.BarCode para .NET
url: /es/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear texto de código extendido dotcode con Aspose.BarCode para .NET

## Introducción

En el ámbito de la generación y gestión de códigos de barras, Aspose.BarCode para .NET se destaca como una solución versátil y eficiente. Ya sea que necesites generar códigos de barras para productos, inventario o cualquier otra aplicación, Aspose.BarCode para .NET te cubre. En este tutorial completo, **crearemos texto de código extendido dotcode** y exploraremos por qué esta capacidad es esencial para entornos modernos ricos en datos. DotCode es un código de barras matricial bidimensional que puede codificar datos textuales y binarios, lo que lo convierte en una herramienta valiosa en diversas industrias.

## Respuestas rápidas
- **¿Qué significa “crear texto de código extendido dotcode”?** Significa construir un código de barras DotCode que incluya FNC1, ECICodetext, texto plano y separadores de símbolos en una única carga útil extendida.  
- **¿Qué biblioteca se requiere?** Aspose.BarCode para .NET.  
- **¿Necesito una licencia?** Una licencia temporal funciona para evaluación; se requiere una licencia completa para producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para un ejemplo básico.

## Cómo crear texto de código extendido dotcode

A continuación se muestra una guía concisa, paso a paso, que indica exactamente cómo construir el texto de código extendido y generar la imagen del código de barras.

## Requisitos previos

Antes de adentrarnos en la guía paso a paso, hay algunos requisitos que debes tener listos para seguir el tutorial de manera eficaz:

1. Aspose.BarCode para .NET: Asegúrate de tener la biblioteca Aspose.BarCode para .NET instalada y lista. Si no la tienes, puedes descargarla desde la [documentación de Aspose.BarCode para .NET](https://reference.aspose.com/barcode/net/).

2. Entorno de desarrollo: Debes contar con un entorno de desarrollo .NET funcional, preferiblemente Visual Studio, instalado en tu sistema.

Con estos requisitos en orden, podemos proceder a generar el Texto de Código Extendido DotCode.

## Importar espacios de nombres

Primero, necesitas importar los espacios de nombres necesarios a tu proyecto .NET para acceder a las funcionalidades requeridas de la biblioteca Aspose.BarCode. Así es como puedes hacerlo:

```csharp
using Aspose.BarCode.Generation;
```

Ahora que cubrimos los requisitos previos, desglosaremos el proceso de generación del Texto de Código Extendido DotCode en una guía paso a paso.

## Paso 1: Definir la ruta del directorio

En este paso, debes especificar la ruta del directorio donde deseas guardar la imagen generada del Texto de Código Extendido DotCode.

```csharp
string path = "Your Directory Path";
```

Reemplaza `"Your Directory Path"` con la ruta real en tu sistema.

## Paso 2: Crear Texto de Código Extendido DotCode

Para crear el Texto de Código Extendido DotCode, sigue estos sub‑pasos:

### 2.1 Añadir identificador de formato FNC1

El identificador de formato FNC1 se utiliza para indicar el comienzo de un nuevo campo de datos. Es una parte esencial del Texto de Código Extendido DotCode.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 Añadir ECICodetext

El ECICodetext es donde puedes codificar caracteres especiales y texto internacional. En este ejemplo, hemos codificado `"犬Right狗"` usando codificación UTF‑8.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 Añadir texto plano

También puedes añadir texto plano al Texto de Código Extendido DotCode. Aquí, hemos añadido `"Plain text"`.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 Añadir separador de símbolo FNC3

El separador de símbolo FNC3 se utiliza para separar diferentes secciones del código.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 Añadir inicialización del lector FNC3

Este paso agrega la información de inicialización del lector FNC3.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 Generar texto de código

Ahora, genera el Texto de Código Extendido DotCode llamando al método `GetExtendedCodetext` del objeto `textBuilder`.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## Paso 3: Generar imagen DotCode

Para generar el Texto de Código Extendido DotCode como una imagen, sigue estos sub‑pasos:

#### 4.1 Inicializar generador de código de barras

Inicializa el `BarcodeGenerator` con los parámetros apropiados. En este caso, usamos `EncodeTypes.DotCode` y el texto de código generado.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

¡Y eso es todo! Has generado con éxito el Texto de Código Extendido DotCode usando Aspose.BarCode para .NET.

## Conclusión

Aspose.BarCode para .NET es una herramienta poderosa que simplifica la generación de códigos de barras. En este tutorial, nos centramos en cómo **crear texto de código extendido dotcode**, lo cual es esencial en diversas industrias, especialmente donde se requiere codificación multilingüe y de caracteres especializados. Siguiendo los pasos descritos arriba, puedes crear fácilmente Texto de Código Extendido DotCode para tus necesidades específicas.

Si necesitas más orientación o tienes preguntas, no dudes en visitar la [documentación de Aspose.BarCode para .NET](https://reference.aspose.com/barcode/net/) o participar en la comunidad del [foro de soporte de Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

## Preguntas frecuentes

### Q1 ¿Para qué se utiliza DotCode?

A1: DotCode se utiliza para codificar tanto datos textuales como binarios y se aplica comúnmente en industrias como la salud y la logística para el seguimiento y la codificación de datos.

### Q2: ¿Puedo personalizar la apariencia de los códigos de barras DotCode?

A2: Sí, Aspose.BarCode para .NET ofrece opciones para personalizar la apariencia de los códigos de barras DotCode, incluyendo tamaño y modo de codificación.

### Q3: ¿Es Aspose.BarCode para .NET compatible con varios frameworks .NET?

A3: Sí, Aspose.BarCode para .NET es compatible con una amplia gama de frameworks .NET, garantizando flexibilidad y facilidad de integración.

### Q4: ¿Cómo obtengo una licencia temporal para Aspose.BarCode para .NET?

A4: Puedes obtener una licencia temporal desde el [sitio web de Aspose](https://purchase.aspose.com/temporary-license/) para evaluación y pruebas.

### Q5: ¿Es Aspose.BarCode para .NET adecuado para la generación de códigos de barras a nivel empresarial?

A5: Absolutamente, Aspose.BarCode para .NET está diseñado para satisfacer las necesidades tanto de generación de códigos de barras a pequeña escala como a nivel empresarial, ofreciendo escalabilidad y fiabilidad.

## Preguntas frecuentes adicionales

**P: ¿Puedo usar el código de barras generado en una aplicación móvil?**  
R: Sí. La imagen PNG producida por el generador puede incrustarse en iOS, Android o cualquier aplicación móvil multiplataforma.

**P: ¿Qué pasa si necesito codificar datos binarios en lugar de texto?**  
R: Utiliza el método `AddECICodetext` con el `ECIEncodings` apropiado (p. ej., `ECIEncodings.Base64`) para incrustar cargas binarias.

**P: ¿Cómo cambio el tamaño del código de barras sin afectar la legibilidad?**  
R: Ajusta la propiedad `XDimension.Pixels`; valores más altos aumentan el tamaño del módulo, mientras que valores más bajos hacen el código más compacto.

**P: ¿Hay forma de añadir una zona silenciosa alrededor del código de barras?**  
R: Sí. Configura `gen.Parameters.Barcode.Margin` para definir la zona silenciosa deseada en píxeles.

**P: ¿La biblioteca soporta .NET 8?**  
R: Las versiones más recientes de Aspose.BarCode son compatibles con .NET 8; solo hay que referenciar la versión adecuada del paquete NuGet.

---

**Última actualización:** 2026-01-27  
**Probado con:** Aspose.BarCode 24.12 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}