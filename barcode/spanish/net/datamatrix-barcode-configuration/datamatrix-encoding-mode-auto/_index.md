---
date: 2026-01-15
description: Guía tutorial paso a paso de códigos de barras para leer códigos DataMatrix
  en C# y generar imágenes de códigos de barras en C# usando Aspose.BarCode para .NET.
linktitle: DataMatrix Encoding Mode (Auto)
second_title: Aspose.BarCode .NET API
title: Leer código de barras DataMatrix C# – Generar modo DataMatrix (Auto)
url: /es/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Leer DataMatrix barcode C# – Generar modo DataMatrix (Auto)

En el mundo digital de hoy, que sea posible **read DataMatrix barcode C#** de forma rápida y fiable es esencial para todo, desde el seguimiento de inventario hasta la gestión segura de documentos. Este tutorial le guiará paso a paso para generar un código de barras DataMatrix en modo *Auto* con Aspose.BarCode para .NET y luego mostrará cómo leer ese código de barras nuevamente en C#. Ya sea que esté siguiendo una **barcode tutorial guide** o simplemente necesite un ejemplo de código sólido, terminará esta guía con una solución funcional que podrá incorporar en sus propios proyectos.

## Respuestas rápidas
- **¿Qué hace el modo “Auto”?** Permite que Aspose.BarCode seleccione automáticamente el mejor esquema de codificación para sus datos.  
- **¿Qué biblioteca se requiere?** Aspose.BarCode for .NET (prueba gratuita disponible).  
- **¿Puedo leer el código de barras en la misma aplicación?** Sí – use `BarCodeReader` con `DecodeType.DataMatrix`.  
- **¿Necesito una licencia para producción?** Se requiere una licencia comercial para uso en producción.  
- **¿Versiones .NET compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## ¿Qué es leer un código de barras DataMatrix en C#?
Leer un código de barras DataMatrix en C# significa decodificar la matriz bidimensional de módulos negros y blancos de vuelta al texto o datos originales. Aspose.BarCode ofrece una API sencilla que abstrae el procesamiento de imágenes de bajo nivel, permitiéndole centrarse en su lógica de negocio.

## ¿Por qué usar Aspose.BarCode para generar una imagen de código de barras C#?
- **Confiabilidad:** Maneja todos los estándares DataMatrix y selecciona automáticamente la codificación óptima.  
- **Flexibilidad:** Control total sobre dimensiones, codificación ECI y formato de imagen.  
- **Multiplataforma:** Funciona con .NET Framework, .NET Core y aplicaciones .NET 5+.  

## Requisitos previos

1. **Entorno .NET** – Instale la última versión del runtime .NET desde el [.NET website](https://dotnet.microsoft.com/download/dotnet).  
2. **Aspose.BarCode for .NET** – Descargue la biblioteca desde el [sitio web](https://releases.aspose.com/barcode/net/).  

## Importando espacios de nombres

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Ahora que los espacios de nombres están en su lugar, vamos a recorrer el código paso a paso.

## Paso 1: Establecer la ruta del directorio

```csharp
string path = "Your Directory Path";
```

Reemplace `"Your Directory Path"` con la carpeta donde desea que se guarde el PNG generado (u otro formato).

## Paso 2: Crear un código de barras DataMatrix en modo Auto

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose常に先を行く"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Auto;
    generator.Parameters.Barcode.DataMatrix.ECIEncoding = ECIEncodings.UTF8;
    Bitmap bitmap = generator.GenerateBarCodeImage();
}
```

La configuración `DataMatrixEncodeMode.Auto` permite que la biblioteca decida la mejor codificación para el texto suministrado. Siéntase libre de reemplazar el texto de ejemplo con cualquier cadena que necesite para **generate barcode image C#**.

## Paso 3: Leer el código de barras (read DataMatrix barcode C#)

```csharp
using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
{
    reader.ReadBarCodes();
    Console.WriteLine(reader.FoundBarCodes[0].CodeText);
}
```

Este fragmento decodifica la imagen que acabamos de generar e imprime el texto original en la consola, demostrando un ciclo completo desde la generación hasta la lectura.

## Problemas comunes y soluciones

| Problema | Causa | Solución |
|----------|-------|----------|
| **No se detectó el código de barras** | Resolución de la imagen demasiado baja | Aumente `XDimension.Pixels` (p.ej., a 6) |
| **Caracteres basura** | Codificación ECI incorrecta | Establezca `ECIEncoding` para que coincida con sus datos (UTF‑8, ASCII, etc.) |
| **Excepción en `ReadBarCodes`** | Bitmap liberado antes de la lectura | Mantenga la instancia `Bitmap` viva hasta después de la lectura |

## Preguntas frecuentes

**Q: ¿Qué es el modo de codificación DataMatrix "Auto"?**  
A: Permite que Aspose.BarCode seleccione automáticamente el método de codificación óptimo para los datos proporcionados, simplificando el proceso de **how to generate datamatrix barcode**.

**Q: ¿Puedo personalizar las dimensiones del código de barras generado?**  
A: Sí – ajuste `generator.Parameters.Barcode.XDimension.Pixels` para cambiar el tamaño del módulo.

**Q: ¿Es Aspose.BarCode for .NET adecuado para uso comercial?**  
A: Absolutamente. Adquiera una licencia desde el [sitio web](https://purchase.aspose.com/buy).

**Q: ¿Hay una prueba gratuita disponible?**  
A: Sí, puede explorar Aspose.BarCode con una prueba gratuita desde [este enlace](https://releases.aspose.com/).

**Q: ¿Qué opciones de codificación están disponibles para los códigos de barras DataMatrix?**  
A: Aspose.BarCode admite UTF‑8, ASCII y otras codificaciones ECI; establezca el valor deseado mediante `ECIEncoding`.

## Conclusión

Ahora dispone de un ejemplo completo y listo para producción que **reads DataMatrix barcode C#**, genera el código de barras en modo Auto y verifica el resultado, todo usando Aspose.BarCode para .NET. Experimente con diferentes textos, tamaños y configuraciones ECI para adaptarse a su escenario específico, y consulte la documentación oficial en [documentation](https://reference.aspose.com/barcode/net/) para una personalización más profunda.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2026-01-15  
**Probado con:** Aspose.BarCode 24.12 for .NET  
**Autor:** Aspose  

---