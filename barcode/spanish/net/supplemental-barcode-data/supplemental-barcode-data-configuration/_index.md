---
date: 2026-03-07
description: Aprende cómo crear un código de barras EAN‑13 con datos suplementarios
  en C# usando Aspose.BarCode para .NET – genera rápidamente un PNG del código de
  barras.
linktitle: Supplemental Barcode Data Configuration
second_title: Aspose.BarCode .NET API
title: Crear código de barras EAN-13 con datos suplementarios – Aspose.BarCode
url: /es/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear código de barras EAN-13 con datos suplementarios – Aspose.BarCode para .NET

En este tutorial práctico **creará un código de barras EAN-13** que incluye datos suplementarios EAN‑2 o EAN‑5, y verá cómo **generar archivos PNG de códigos de barras** con solo unas pocas líneas de C#. Ya sea que esté construyendo un sistema de caja minorista, una aplicación logística o una herramienta simple de inventario, la capacidad de agregar información suplementaria hace que sus códigos de barras sean mucho más útiles.

## Respuestas rápidas
- **¿Qué significa “datos suplementarios”?** Dígitos extra (EAN‑2/EAN‑5) impresos al lado del código de barras principal, a menudo usados para precios o números de edición.  
- **¿Qué tipo de código de barras se utiliza?** EAN‑13 como símbolo principal, con suplementos opcionales EAN‑2 o EAN‑5.  
- **¿Puedo generar imágenes PNG?** Sí – el método `Save` le permite exportar directamente a PNG.  
- **¿Necesito una licencia para el desarrollo?** Una prueba gratuita funciona para pruebas; se requiere una licencia comercial para producción.  
- **¿Es compatible con .NET Core / .NET 6?** Absolutamente – Aspose.BarCode soporta todos los runtimes modernos de .NET.

## Requisitos previos

Antes de sumergirnos en el código, asegúrese de tener:

- Visual Studio (o cualquier IDE compatible con .NET).  
- Una copia de Aspose.BarCode para .NET – descárguela **[aquí](https://releases.aspose.com/barcode/net/)**.  
- Conocimientos básicos de C#.  
- Una carpeta con permisos de escritura donde se guardarán los archivos PNG generados.

## Importando espacios de nombres

Primero, añada el espacio de nombres Aspose.BarCode para poder acceder a las clases generadoras:

```csharp
using Aspose.BarCode.Generation;
```

> **Consejo profesional:** Si está usando .NET Core, añada el paquete NuGet `Aspose.BarCode` a su proyecto en lugar de referenciar el DLL manualmente.

## ¿Qué es un código de barras suplementario?

Un código de barras suplementario es una cadena numérica auxiliar impresa junto al código de barras principal.  
- **EAN‑2** – suplemento de dos dígitos, a menudo usado para números de edición en revistas.  
- **EAN‑5** – suplemento de cinco dígitos, comúnmente usado para extensiones de precio en artículos minoristas.

Agregar estos suplementos no cambia los datos primarios del EAN‑13; simplemente brinda contexto adicional que los escáneres pueden leer.

## ¿Por qué usar Aspose.BarCode para datos suplementarios?

- **API de una línea** – configure tanto el código de barras principal como su suplemento en un solo objeto.  
- **Control total sobre dimensiones** – ajuste la dimensión X, el espaciado del suplemento y el formato de imagen.  
- **Multiplataforma** – funciona en .NET Framework, .NET Core y .NET 5/6+.  

## Guía paso a paso

### Paso 1: Configurar el directorio de salida

Defina dónde se almacenarán los archivos PNG. Reemplace el marcador de posición con una ruta real en su máquina.

```csharp
string path = "Your Directory Path";
```

### Paso 2: Inicializar el generador de códigos de barras (Barcode Generator C#)

Cree una instancia de `BarcodeGenerator`, especificando **EAN‑13** como tipo principal y proporcionando la carga útil de 13 dígitos.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

### Paso 3: Ajustar dimensiones del código de barras

Ajuste finamente el tamaño visual del código de barras y el espacio reservado para el suplemento.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

### Paso 4: Añadir un suplemento EAN‑2

Establezca los datos suplementarios a un valor de dos dígitos (p. ej., “12”). Esto aparecerá a la derecha del código de barras principal.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

### Paso 5: Guardar el código de barras EAN‑2 como PNG

Exporte la imagen. El argumento `BarCodeImageFormat.Png` garantiza un archivo PNG de alta calidad.

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

### Paso 6: Cambiar a un suplemento EAN‑5

Cambie `SupplementData` a una cadena de cinco dígitos para extensiones de precio.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

### Paso 7: Guardar el código de barras EAN‑5 como PNG

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

> **Por qué funciona:** Se reutiliza la misma instancia de `BarcodeGenerator`, por lo que solo necesita modificar la propiedad `SupplementData` antes de cada llamada a `Save`. Esto mantiene el código conciso y evita la creación innecesaria de objetos.

## Problemas comunes y consejos

- **Ruta de directorio no válida** – asegúrese de que la carpeta exista y la aplicación tenga permisos de escritura.  
- **Longitud de suplemento incorrecta** – EAN‑2 espera exactamente 2 dígitos, EAN‑5 espera 5; de lo contrario se lanza una excepción.  
- **Imagen no visible** – verifique que se use `BarCodeImageFormat.Png`; otros formatos (p. ej., JPEG) pueden introducir artefactos de compresión que afecten la legibilidad del escáner.  

## Preguntas frecuentes

### ¿Puedo usar Aspose.BarCode para .NET en mi proyecto .NET Core?

Sí, Aspose.BarCode para .NET es totalmente compatible con .NET Core, .NET 5 y .NET 6.

### ¿Hay una prueba gratuita disponible para Aspose.BarCode para .NET?

Sí, puede probarlo gratis visitando **[este enlace](https://releases.aspose.com/)**.

### ¿Dónde puedo obtener una licencia temporal para Aspose.BarCode para .NET?

Puede obtener una licencia temporal en **[este enlace](https://purchase.aspose.com/temporary-license/)**.

### ¿Aspose.BarCode soporta una amplia gama de tipos de códigos de barras?

Absolutamente – soporta EAN‑13, QR Code, Code 128, DataMatrix, PDF‑417 y muchos más.

### ¿Puedo personalizar la apariencia de los códigos de barras generados?

Sí, puede modificar colores, fuentes, márgenes e incluso agregar imágenes de fondo usando la amplia API `Parameters`.

## Conclusión

Ahora sabe cómo **crear un código de barras EAN-13** con datos suplementarios EAN‑2 o EAN‑5 y **generar archivos PNG de códigos de barras** usando Aspose.BarCode para .NET. Este enfoque le brinda control total sobre las dimensiones del código de barras, el espaciado del suplemento y el formato de salida, lo que lo hace ideal para retail, logística y cualquier escenario donde se requiera información numérica adicional.

Para una exploración más profunda, consulte la guía de referencia completa: **[documentación de Aspose.BarCode para .NET](https://reference.aspose.com/barcode/net/)**.

---

**Última actualización:** 2026-03-07  
**Probado con:** Aspose.BarCode 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}