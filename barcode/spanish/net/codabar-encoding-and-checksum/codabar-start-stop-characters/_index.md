---
date: 2026-01-04
description: Aprenda a generar códigos de barras Codabar con caracteres de inicio
  y fin usando Aspose.BarCode para .NET. Un tutorial paso a paso de generación de
  códigos de barras para desarrolladores.
linktitle: Codabar Start/Stop Characters
second_title: Aspose.BarCode .NET API
title: Generar código de barras Codabar con caracteres de inicio/fin en Aspose.BarCode
  para .NET
url: /es/net/codabar-encoding-and-checksum/codabar-start-stop-characters/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generar código de barras Codabar con caracteres de inicio/parada en Aspose.BarCode para .NET

## Introducción

Bienvenido a esta guía completa sobre cómo **generar imágenes de código de barras codabar** con caracteres de inicio/parada usando Aspose.BarCode para .NET. Ya sea que estés construyendo un sistema de inventario minorista, un rastreador de muestras de laboratorio o una solución de registros médicos, Codabar es una simbología numérica confiable que requiere símbolos de inicio y parada explícitos para un escaneo preciso. En los próximos minutos repasaremos todo lo que necesitas—desde los requisitos previos hasta guardar los archivos PNG finales—para que puedas comenzar a crear códigos de barras Codabar de inmediato.

## Respuestas rápidas
- **¿Qué biblioteca necesito?** Aspose.BarCode para .NET  
- **¿En qué formato puedo guardar el código de barras?** PNG (BarCodeImageFormat.Png)  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita funciona para pruebas; se requiere una licencia comercial para producción.  
- **¿Puedo cambiar los símbolos de inicio/parada?** Sí – usa CodabarSymbol.A, B, C o D.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Requisitos previos

Antes de comenzar, asegurémonos de que tienes todo lo necesario para seguir este tutorial:

1. **Configuración del entorno** – Asegúrate de tener un entorno de desarrollo .NET funcionando en tu máquina. Si necesitas orientación, consulta la [documentación](https://reference.aspose.com/barcode/net/).  
2. **Biblioteca Aspose.BarCode para .NET** – Descarga e instala la biblioteca desde el [origen oficial](https://releases.aspose.com/barcode/net/).  
3. **Conocimientos básicos de .NET** – Familiaridad con C# y Visual Studio (o cualquier IDE preferido) hará que los pasos sean más fluidos.  
4. **IDE** – Visual Studio, Rider o Visual Studio Code son todas opciones válidas.

Ahora que hemos cubierto los requisitos previos, pasemos al código real.

## Importar espacios de nombres

Para comenzar con Aspose.BarCode para .NET, asegúrate de importar el espacio de nombres necesario:

```csharp
using Aspose.BarCode.Generation;
```

## Cómo generar un código de barras codabar – Guía paso a paso

### Paso 1: Inicializar el generador de códigos de barras

Crea una instancia de `BarcodeGenerator`, especifica **Codabar** como el tipo de codificación y proporciona la cadena de datos que ya contiene los caracteres de inicio/parada (p. ej., “-12345-”).

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarStartStop:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

> **Consejo profesional:** El guion (`-`) es uno de los símbolos de inicio/parada válidos para Codabar. También puedes usar A, B, C o D según los requisitos de tu aplicación.

### Paso 2: Establecer la X‑Dimension (ancho del elemento del código de barras)

La X‑Dimension controla el ancho de la barra más estrecha. Ajústala según tu entorno de escaneo.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Por qué importa:** Una X‑Dimension mayor mejora la legibilidad en impresoras de baja resolución, mientras que un valor menor ahorra espacio en etiquetas de alta densidad.

### Paso 3: Definir los caracteres de inicio y parada

Codabar admite cuatro símbolos de inicio/parada (A, B, C, D). A continuación se muestran ejemplos para cada opción. Elige el que coincida con la especificación del sistema con el que te estás integrando.

#### Configurar Inicio A y Parada A

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.A;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.A;
```

#### Configurar Inicio B y Parada B

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.B;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.B;
```

#### Configurar Inicio C y Parada C

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.C;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.C;
```

#### Configurar Inicio D y Parada D

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.D;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.D;
```

Puedes repetir la configuración para cada símbolo que necesites generar; el ejemplo a continuación guarda cuatro imágenes separadas, una para cada par de inicio/parada.

### Paso 4: Guardar las imágenes del código de barras generado (PNG)

Finalmente, escribe el código de barras en archivos PNG. Esto demuestra el caso de uso **save barcode png** y te brinda recursos listos para usar en pruebas.

```csharp
gen.Save($"{path}CodabarStartAStopA.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartBStopB.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartCStopC.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartDStopD.png", BarCodeImageFormat.Png);
```

Cada archivo ahora contiene un **ejemplo de código de barras codabar** con los símbolos de inicio/parada correspondientes.

## Problemas comunes y solución de errores

| Síntoma | Causa probable | Solución |
|---------|----------------|----------|
| El código de barras aparece distorsionado | X‑Dimension demasiado baja para la resolución de la impresora elegida | Incrementa `XDimension.Pixels` (p. ej., a 3 o 4) |
| El escáner no puede leer el inicio/parada | Símbolo de inicio/parada incorrecto para el sistema objetivo | Verifica el símbolo requerido (A‑D) y configúralo en consecuencia |
| El archivo PNG está vacío o corrupto | Ruta de salida inválida o permisos de escritura insuficientes | Asegúrate de que `path` apunte a una carpeta existente y que tu aplicación tenga acceso de escritura |

## Preguntas frecuentes

### P1: ¿Qué es Codabar y por qué son importantes los caracteres de inicio y parada?

R1: Codabar es una simbología de código de barras numérica ampliamente usada en inventario, bibliotecas y atención médica. Los caracteres de inicio y parada definen los límites del código, garantizando que los escáneres sepan dónde comienza y termina la información.

### P2: ¿Puedo personalizar la apariencia de los códigos de barras Codabar con Aspose.BarCode para .NET?

R2: Sí. Además de la X‑Dimension, puedes modificar colores, añadir márgenes e incluso incrustar el código de barras en formatos PDF o SVG usando la misma API.

### P3: ¿Existen limitaciones en los códigos de barras Codabar respecto a la codificación de datos?

R3: Codabar soporta principalmente datos numéricos (0‑9) y algunos caracteres especiales. No es adecuado para cadenas alfanuméricas completas.

### P4: ¿Aspose.BarCode para .NET es apto para uso comercial y cómo puedo obtener una licencia?

R4: Sí, está listo para producción. Compra una licencia en la [página de compra de Aspose](https://purchase.aspose.com/buy).

### P5: ¿Dónde puedo buscar ayuda o discutir problemas relacionados con Aspose.BarCode para .NET?

R5: Únete a la comunidad en el [foro de soporte de Aspose.BarCode para .NET](https://forum.aspose.com/c/barcode/13) para recibir asistencia tanto de ingenieros de Aspose como de otros desarrolladores.

---

**Última actualización:** 2026-01-04  
**Probado con:** Aspose.BarCode 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}