---
date: 2026-03-07
description: Aprenda a crear códigos de barras unidimensionales Databar codificados
  con GS1 en .NET usando Aspose.BarCode. Esta guía muestra cómo establecer GS1, configurar
  el generador de códigos de barras y generar códigos de barras rápidamente.
linktitle: One-Dimensional Databar GS1 Encoding
second_title: Aspose.BarCode .NET API
title: Crear codificación GS1 de Databar unidimensional con Aspose.BarCode
url: /es/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear codificación GS1 de Databar unidimensional con Aspose.BarCode

En este tutorial **creará códigos de barras databar unidimensional** que cumplen con el estándar GS1, usando la biblioteca Aspose.BarCode para .NET. Ya sea que necesite una validación estricta de GS1 o un código de barras más flexible, le guiaremos paso a paso—desde la instalación de la biblioteca hasta el manejo de excepciones de codificación—para que pueda generar códigos de barras fiables en sus propias aplicaciones.

## Respuestas rápidas
- **¿Qué significa “crear databar unidimensional”?** Significa generar un código de barras lineal (1‑D) de la familia Databar, usado frecuentemente en retail y logística.  
- **¿Cómo configuro la validación GS1?** Establezca `IsAllowOnlyGS1Encoding` a `true` en los parámetros de `DataBar`.  
- **¿Necesito una licencia?** Una versión de prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **¿Dónde puedo descargar la biblioteca?** Desde la página oficial de lanzamientos de Aspose (ver requisitos previos).

## ¿Qué es “crear databar unidimensional”?
Un Databar unidimensional (también conocido como RSS) es un código de barras lineal compacto que puede codificar datos numéricos, fechas o cadenas AI (Identificador de Aplicación). Cuando se combina con codificación GS1, el código de barras sigue una estructura de datos reconocida globalmente, lo que lo hace ideal para retail, salud y escenarios de cadena de suministro.

## ¿Por qué usar Aspose.BarCode para .NET?
Aspose.BarCode ofrece una API fluida, soporte total de GS1 y la capacidad de afinar cada aspecto visual del código de barras. Elimina la adivinanza del codificado de bajo nivel y le permite centrarse en la lógica de negocio.

## Requisitos previos

1. **Aspose.BarCode para .NET** – descárguela e instálela desde [aquí](https://releases.aspose.com/barcode/net/).  
2. **Su ruta de directorio** – reemplace `"Your Directory Path"` en los ejemplos por una carpeta donde tenga permiso de escritura.

## Importación de espacios de nombres

Agregue las sentencias `using` requeridas al inicio de su archivo C#:

```csharp
using Aspose.BarCode;
using System;
```

## Paso 1: Inicializar el generador de códigos de barras

Cree una instancia de `BarcodeGenerator` y especifique la simbología Databar Expanded:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## Paso 2: Cómo establecer GS1 – Generar un código de barras con validación estricta de GS1

Active la codificación solo GS1, asigne un texto de código compatible con GS1 y guarde la imagen:

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## Paso 3: Generación de código de barras con Aspose – Codificación variable (sin verificación GS1)

Si necesita un código de barras que **no** aplique las reglas GS1, desactive la verificación:

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## Paso 4: Verificación GS1 del generador de códigos de barras – Manejo de una excepción

Cuando `IsAllowOnlyGS1Encoding` es `true` pero el texto de código no es compatible con GS1, Aspose lanza una excepción. El siguiente patrón muestra cómo capturarla y registrarla:

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

### Errores comunes y consejos
- **Error:** Proporcionar una cadena no‑GS1 mientras la verificación GS1 está habilitada abortará la generación del código de barras.  
- **Consejo profesional:** Valide sus cadenas AI antes de asignarlas a `CodeText` para evitar errores en tiempo de ejecución.  
- **Tip:** Use rutas absolutas o `Path.Combine` para construir nombres de archivo de forma segura en todas las plataformas.

## Conclusión

Ahora sabe cómo **crear códigos de barras databar unidimensional** con codificación GS1, cómo activar o desactivar la verificación GS1 y cómo manejar las excepciones relacionadas, todo usando Aspose.BarCode para .NET. Siéntase libre de explorar opciones adicionales de estilo como tamaño, color y márgenes del código de barras mediante el objeto `Parameters.Barcode`.

Si encuentra algún problema, la documentación oficial y el foro de la comunidad son recursos excelentes:

- [Documentación de Aspose.BarCode](https://reference.aspose.com/barcode/net/)  
- [Foro de soporte de Aspose.BarCode](https://forum.aspose.com/c/barcode/13)

## Preguntas frecuentes

### 1. ¿Qué es la codificación GS1 en los códigos de barras?
La codificación GS1 es una forma estandarizada de estructurar datos (p. ej., identificadores de producto) dentro de un código de barras, garantizando interoperabilidad entre minoristas, fabricantes y proveedores logísticos.

### 2. ¿Puedo personalizar la apariencia de los códigos de barras generados?
Sí. Aspose.BarCode le permite ajustar tamaño, colores, márgenes e incluso agregar texto legible por humanos mediante la configuración `Parameters.Barcode`.

### 3. ¿Dónde puedo encontrar recursos y documentación adicional para Aspose.BarCode?
Puede encontrar documentación completa y ejemplos en [Documentación de Aspose.BarCode](https://reference.aspose.com/barcode/net/). Es un recurso valioso para aprender y solucionar problemas.

### 4. ¿Existe una versión de prueba disponible para Aspose.BarCode?
Sí, puede obtener una versión de prueba gratuita de Aspose.BarCode para .NET desde [aquí](https://releases.aspose.com/).

### 5. ¿Cómo puedo comprar una licencia para Aspose.BarCode para .NET?
Para adquirir una licencia de Aspose.BarCode para .NET, visite la [página de compra](https://purchase.aspose.com/buy) en el sitio web de Aspose.

---

**Última actualización:** 2026-03-07  
**Probado con:** Aspose.BarCode 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}