---
date: 2026-01-02
description: 'Aprenda a usar el generador de códigos de barras Aztec con Aspose.BarCode
  para .NET: guía paso a paso sobre cómo configurar el modo de símbolo Aztec (Auto,
  FullRange, Compact, Rune).'
linktitle: Aztec Symbol Mode Example
second_title: Aspose.BarCode .NET API
title: generador de códigos de barras aztec – Dominando el modo de símbolo Aztec con
  Aspose.BarCode para .NET
url: /es/net/aztec-barcode-encoding/aztec-symbol-mode-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# generador de códigos de barras aztec – Dominando el modo de símbolo Aztec con Aspose.BarCode para .NET

Si deseas incorporar potentes capacidades de generación de códigos de barras en tus aplicaciones .NET, el **barcode generator aztec** de Aspose.BarCode para .NET es una solución fantástica. En este tutorial profundizaremos en el modo de símbolo Aztec, mostraremos **cómo configurar las opciones aztec** y te guiaremos con ejemplos de código prácticos que puedes insertar directamente en tu proyecto.

## Respuestas rápidas
- **¿Cuál es la clase principal?** `BarcodeGenerator` de `Aspose.BarCode.Generation`.
- **¿Qué modos de símbolo están disponibles?** Auto, FullRange, Compact y Rune.
- **¿Necesito una licencia?** Una licencia temporal funciona para pruebas; se requiere una licencia completa para producción.
- **¿Puedo cambiar el texto del código?** Sí, asigna `gen.CodeText` antes de guardar.
- **¿Qué formatos de imagen son compatibles?** PNG, JPEG, BMP, GIF, TIFF y más.

## ¿Qué es un barcode generator aztec?
El barcode generator aztec crea códigos Aztec bidimensionales, un código de matriz compacto que puede almacenar una gran cantidad de datos en un espacio reducido. Es ideal para boletos móviles, URLs y datos binarios donde el espacio es limitado.

## ¿Por qué usar Aspose.BarCode para .NET?
- **Compatibilidad total con .NET** – funciona con .NET Framework, .NET Core y .NET 5/6.  
- **Conjunto de funciones rico** – múltiples modos de símbolo, corrección de errores y amplia personalización.  
- **Sin dependencias externas** – genera códigos de barras completamente en proceso.  
- **Multiplataforma** – se ejecuta en Windows, Linux y macOS.

## Requisitos previos

- Conocimientos básicos de desarrollo .NET.  
- Visual Studio instalado en tu máquina.  
- Una copia de Aspose.BarCode para .NET. Puedes descargarla [aquí](https://releases.aspose.com/barcode/net/).

Ahora que estás listo, exploremos las opciones del modo de símbolo Aztec.

## Cómo establecer el modo de símbolo Aztec con el barcode generator aztec

### Importar espacios de nombres

Primero, agrega el espacio de nombres requerido al inicio de tu archivo C#:

```csharp
using Aspose.BarCode.Generation;
```

Con el espacio de nombres importado, puedes comenzar a crear códigos de barras Aztec.

### Paso 1: Configurar el generador de códigos de barras

Inicializa el generador con el tipo de codificación Aztec y proporciona el texto que deseas codificar:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

> **Consejo profesional:** Usa una cadena compatible con UTF‑8 para caracteres internacionales, como se muestra arriba.

### Paso 2: Establecer el modo de símbolo a Auto

El modo **Auto** permite que la biblioteca decida el tamaño óptimo según la longitud de los datos:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

El PNG generado se guardará en la carpeta que especificaste.

### Paso 3: Establecer el modo de símbolo a FullRange

Si deseas que la biblioteca utilice todo el rango de tamaños de símbolo Aztec, elige **FullRange**:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

### Paso 4: Establecer el modo de símbolo a Compact

Para un código de barras más compacto que aún mantiene buena legibilidad, usa **Compact**:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

### Paso 5: Establecer el modo de símbolo a Rune

El modo **Rune** está diseñado para casos de uso especiales donde se requiere un estilo visual diferente:

```csharp
gen.CodeText = "123"; // Change the code text if needed
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

### Problemas comunes y soluciones

| Problema | Solución |
|----------|----------|
| La imagen del código de barras está en blanco | Verifica que `path` apunte a un directorio existente y con permisos de escritura. |
| Caracteres no compatibles | Usa solo los caracteres admitidos por el estándar Aztec o cambia a codificación UTF‑8. |
| Tamaño de símbolo incorrecto | Experimenta con `AztecSymbolMode.Auto` para que la biblioteca elija el mejor tamaño. |

## Preguntas frecuentes

**P: ¿Cuál es el propósito del modo de símbolo Aztec en la generación de códigos de barras?**  
R: Permite controlar la densidad visual y el nivel de corrección de errores del código Aztec, adaptando el código de barras a tus requisitos de espacio y legibilidad.

**P: ¿Puedo cambiar el texto del código para códigos Aztec en Aspose.BarCode para .NET?**  
R: Sí, simplemente asigna una nueva cadena a `gen.CodeText` antes de llamar a `Save`.

**P: ¿Existe una versión de prueba gratuita de Aspose.BarCode para .NET?**  
R: Sí, puedes descargar una prueba gratuita [aquí](https://releases.aspose.com/).

**P: ¿Dónde puedo encontrar la documentación completa de Aspose.BarCode para .NET?**  
R: La referencia completa de la API está disponible [aquí](https://reference.aspose.com/barcode/net/).

**P: ¿Cómo puedo obtener una licencia temporal para Aspose.BarCode para .NET?**  
R: Una licencia temporal se puede solicitar a través de [este enlace](https://purchase.aspose.com/temporary-license/).

## Conclusión

En esta guía cubrimos todo lo que necesitas saber para usar el **barcode generator aztec** con Aspose.BarCode para .NET, desde la configuración del generador hasta el dominio de cada modo de símbolo (Auto, FullRange, Compact, Rune). Con estos ejemplos, ahora puedes incrustar códigos de barras Aztec versátiles en cualquier aplicación .NET de forma rápida y fiable.

Si tienes más preguntas, no dudes en unirte a la comunidad de Aspose.BarCode en su [foro de soporte](https://forum.aspose.com/c/barcode/13).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2026-01-02  
**Probado con:** Aspose.BarCode 24.10 para .NET  
**Autor:** Aspose