---
category: general
date: 2026-09-10
description: Crea un código de barras PDF417 en C# rápidamente. Aprende cómo habilitar
  el modo compacto, establecer columnas y generar un PNG con BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- enable compact mode
- barcode generator C#
- how to generate barcode
- how to set columns
language: es
lastmod: 2026-09-10
og_description: Crea un código de barras PDF417 en C# activando el modo compacto,
  configurando columnas y guardándolo como PNG. Sigue la guía completa paso a paso.
og_image_alt: Screenshot of a compact PDF417 barcode generated with C#
og_title: Crear código de barras PDF417 en C# – tutorial de modo compacto
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create PDF417 barcode in C# quickly. Learn how to enable compact mode,
    set columns, and generate a PNG with BarcodeGenerator.
  headline: How to create PDF417 barcode in C# with compact mode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Cómo crear un código de barras PDF417 en C# con modo compacto
url: /es/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un código de barras PDF417 en C# con modo compacto

Si necesitas **crear un código de barras PDF417** en una aplicación .NET, esta guía te muestra exactamente cómo hacerlo. Verás cómo **activar el modo compacto**, establecer el número de columnas y guardar el resultado como una imagen PNG usando la biblioteca BarcodeGenerator para C#.

Generar un código de barras es un requisito común para el seguimiento de inventario, sistemas de boletos y aplicaciones de escaneo móvil. Al final de este tutorial tendrás un ejemplo autónomo y ejecutable que produce un código de barras PDF417 compacto listo para uso en producción.

## Requisitos previos

* .NET 6.0 o posterior instalado (el código también funciona con .NET Framework 4.7+)
* Una versión reciente de la biblioteca **BarcodeGenerator** (p. ej., Aspose.BarCode para .NET)
* Un IDE o editor como Visual Studio 2022 o VS Code
* Permiso de escritura en una carpeta donde se guardará el PNG

No se requieren paquetes NuGet adicionales más allá de la propia biblioteca de códigos de barras.

## Paso 1: Crear un generador de código de barras PDF417

El primer paso es instanciar un objeto `BarcodeGenerator` con el enum `EncodeTypes.Pdf417` y el texto que deseas codificar. Este objeto controla todo el proceso de generación.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

*Por qué es importante*: El valor `EncodeTypes.Pdf417` indica a la biblioteca que use la simbología PDF417, mientras que el segundo argumento proporciona la carga útil. Puedes reemplazar `"Compact mode"` por cualquier cadena alfanumérica que necesites codificar.

## Paso 2: Establecer la dimensión X (ancho del módulo)

La dimensión X controla el ancho de cada pequeño cuadrado (módulo) en el código de barras. Valores más bajos producen una imagen más compacta, lo cual es útil cuando el espacio es limitado.

```csharp
// Step 2: Set the X dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Un valor de `2` píxeles es un buen equilibrio entre legibilidad y compacidad para la mayoría de los escáneres basados en pantalla.

## Paso 3: Definir el número de columnas

PDF417 puede organizar los datos en una cuadrícula de filas y columnas. Ajustar el número de columnas cambia la relación de aspecto del código de barras.

```csharp
// Step 3: Define the number of columns for the PDF417 barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

Establecer **how to set columns** a `3` produce un código de barras corto y ancho que encaja bien en una etiqueta. Puedes experimentar con valores de `1` a `30` según la cantidad de datos y el escáner objetivo.

## Paso 4: Activar el modo compacto

El modo compacto elimina filas de relleno innecesarias, haciendo el código de barras más pequeño sin perder la integridad de los datos. Este es el paso clave para un **PDF417 compacto**.

```csharp
// Step 4: Enable compact mode by truncating the barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

Cuando `Truncate` es `true`, la biblioteca calcula automáticamente el número mínimo de filas necesario para almacenar los datos, por lo que la imagen final se ve “ajustada”.

## Paso 5: Guardar el código de barras generado como una imagen PNG

Finalmente, escribe el código de barras en un archivo. PNG conserva los bordes nítidos necesarios para un escaneo fiable.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Reemplaza `YOUR_DIRECTORY` con una ruta absoluta o relativa a la que tu aplicación pueda escribir. Después de la ejecución, encontrarás un archivo `CompactPdf417.png` que contiene el código de barras.

### Código fuente completo

Unir todos los pasos te brinda un programa único, listo para ejecutar:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

        // Set the X dimension (module width) in pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the number of columns for the PDF417 barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;

        // Enable compact mode by truncating the barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("CompactPdf417.png", BarCodeImageFormat.Png);

        Console.WriteLine("PDF417 barcode created successfully.");
    }
}
```

Ejecutar este programa genera `CompactPdf417.png` en la misma carpeta que el ejecutable. Abre la imagen con cualquier visor; deberías ver un código de barras PDF417 denso y de alto contraste listo para escanear.

## Cómo activar el modo compacto en otros escenarios

* **Generación por lotes** – Al crear muchos códigos de barras, establece `Truncate` una vez en el generador y reutilízalo para cada nueva carga útil.
* **Diferentes formatos de imagen** – El mismo método `Save` funciona con `BarCodeImageFormat.Jpeg` o `BarCodeImageFormat.Bmp` si necesitas otro tipo de archivo.
* **Recuento de columnas dinámico** – Si la longitud de la cadena codificada varía, calcula un número óptimo de columnas basado en la longitud de la cadena y la resolución del escáner.

## Cómo establecer columnas para casos de uso específicos

* **Impresión de etiquetas** – Usa un recuento bajo de columnas (p. ej., `2`‑`5`) para mantener el código de barras lo suficientemente corto como para caber en etiquetas estrechas.
* **Escaneo móvil** – Recuentos de columnas más altos (`10`‑`15`) producen códigos de barras más altos que son más fáciles de enfocar para las cámaras de los teléfonos.
* **Compensación de corrección de errores** – Más columnas reducen el número de filas, lo que puede afectar la corrección de errores incorporada del código de barras. Prueba con tu escáner objetivo para encontrar el punto óptimo.

## Errores comunes y consejos profesionales

| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| El código de barras es ilegible | Dimensión X demasiado baja (p. ej., `1` píxel) | Aumentar `XDimension.Pixels` a al menos `2` |
| La imagen es demasiado grande | Columnas establecidas demasiado altas para una carga corta | Reducir `Pdf417.Columns` o habilitar `Truncate` |
| El archivo PNG está vacío | La carpeta de salida no existe o carece de permiso de escritura | Asegúrate de que el directorio exista y el proceso tenga derechos de escritura |
| El escáner informa “datos corruptos” | Truncate deshabilitado mientras se usan muchas columnas | Habilitar `Truncate` o reducir el número de columnas |

## Verificando el resultado

Puedes verificar el código de barras con cualquier aplicación escáner de PDF417 (existen muchas apps gratuitas para Android/iOS). Abre `CompactPdf417.png` en la app y confirma que el texto decodificado coincida con la carga original (“Compact mode”). Si el texto difiere, revisa nuevamente la bandera `Truncate` y la configuración de columnas.

## Próximos pasos

* **Integrar con ASP.NET Core** – Devolver el PNG directamente desde una acción de controlador en lugar de guardarlo en disco.
* **Agregar texto legible** – Usa `barcodeGenerator.Parameters.Barcode.CodeTextParameters` para mostrar la cadena codificada debajo del código de barras.
* **Explorar otras simbologías** – La misma clase `BarcodeGenerator` admite QR, Code128, DataMatrix y más. Cambia `EncodeTypes` para probarlas.

---

### Conclusión

Ahora sabes cómo **crear un código de barras PDF417** en C# mientras **activas el modo compacto**, controlas **cómo establecer columnas**, y utilizas la API **barcode generator C#** para **generar un código de barras** que cumpla con las limitaciones de tamaño del mundo real. Aplica estos pasos a cualquier proyecto .NET que necesite códigos de barras compactos y de alta densidad, y extiende el patrón a otros formatos de códigos de barras según sea necesario. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Crear código de barras PDF417 en C# – Guía completa paso a paso](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Cómo establecer el nivel de error en el código de barras PDF417 – Guía completa](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Cómo guardar un código de barras en C# – Generar códigos de barras PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}