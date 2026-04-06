---
date: 2026-03-02
description: Aprende cómo generar códigos de barras con Aspose.BarCode para .NET,
  incluidos consejos de generación de códigos de barras en Visual Studio, en esta
  guía paso a paso sobre la configuración de la relación ancho‑estrecho.
linktitle: One-Dimensional Wide-Narrow Ratio Configuration
second_title: Aspose.BarCode .NET API
title: Cómo generar código de barras – Configuración de la relación ancho‑estrecho
url: /es/net/one-dimensional-barcode-types/one-dimensional-wide-narrow-ratio-configuration/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configuración de la Relación Ancha‑Estrecha Unidimensional

## Respuestas rápidas
- **¿Qué controla la relación ancha‑estrecha?** Define el ancho relativo de las barras “anchas” frente a las barras “estrechas” en un código de barras 1D.  
- **¿Qué tipo de código de barras se usa en el ejemplo?** Code 39 Extended, una simbología popular para datos alfanuméricos.  
- **¿Puedo cambiar la relación en tiempo de ejecución?** Sí, solo establezca `gen.Parameters.Barcode.WideNarrowRatio` al valor deseado antes de guardar.  
- **¿Necesito una licencia para esta función?** La relación ancha‑estrecha funciona con la versión de prueba gratuita; una licencia completa desbloquea todas las opciones de renderizado.  
- **¿Es compatible con .NET Core?** Absolutamente, Aspose.BarCode soporta .NET Framework, .NET Core y .NET 5/6+.

## ¿Qué es una relación ancha‑estrecha?
En los códigos de barras unidimensionales cada barra es “ancha” o “estrecha”. La relación (p. ej., 2 o 5) determina cuántas veces es más ancha una barra ancha comparada con una barra estrecha. Ajustar esta relación puede mejorar la legibilidad en impresoras o escáneres de baja resolución.

## ¿Por qué usar Aspose.BarCode para .NET?
* **Control total** – Cada aspecto visual, incluida la relación ancha‑estrecha, puede establecerse programáticamente.  
* **Multiplataforma** – Funciona en Visual Studio, Visual Studio Code y cualquier runtime de .NET.  
* **Sin dependencias externas** – No se necesitan DLLs nativas ni herramientas de terceros.  
* **Documentación y soporte completos** – Incluye ejemplos, foros y guías rápidas.

## Requisitos previos

Antes de sumergirnos en el mundo de los códigos de barras con Aspose.BarCode para .NET, debe contar con los siguientes requisitos:

### 1. Entorno Visual Studio
- Asegúrese de tener Visual Studio instalado en su sistema para trabajar con aplicaciones .NET.

### 2. Biblioteca Aspose.BarCode para .NET
- Debe tener la biblioteca Aspose.BarCode para .NET instalada. Puede descargarla desde el [sitio web](https://releases.aspose.com/barcode/net/).

### 3. Clave de licencia (Opcional)
- Si dispone de una clave de licencia, puede usarse para desbloquear funciones adicionales de la biblioteca. Puede obtener una licencia temporal desde [aquí](https://purchase.aspose.com/temporary-license/).

Ahora que tiene los requisitos listos, vamos a crear códigos de barras unidimensionales con configuración de relación ancha‑estrecha usando Aspose.BarCode para .NET.

## Importar espacios de nombres

Primero, debe incluir los espacios de nombres necesarios en su proyecto para acceder a las funciones de Aspose.BarCode para .NET. Puede hacerlo añadiendo las siguientes sentencias using al inicio de su código:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Paso 1: Definir la ruta del directorio

Comience definiendo la ruta donde desea guardar las imágenes de códigos de barras generados. Puede hacerlo con el siguiente código:

```csharp
string path = "Your Directory Path";
```

Reemplace `"Your Directory Path"` con la ruta real del directorio donde desea guardar las imágenes de los códigos de barras.

## Paso 2: Crear un código de barras unidimensional con relación ancha‑estrecha

Ahora, vamos a crear un código de barras unidimensional con configuración de relación ancha‑estrecha usando Aspose.BarCode para .NET. En este ejemplo, utilizaremos el tipo de codificación Code39Extended y estableceremos los datos a `"ASPOSE"`:

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code39Extended, "ASPOSE");
```

Esta línea de código inicializa un generador de códigos de barras con el tipo de codificación y los datos especificados.

## Paso 3: Establecer la relación ancha/estrecha

La relación ancha‑estrecha determina la proporción entre los elementos anchos y estrechos en el código de barras. En este paso, estableceremos la relación ancha‑estrecha a **2**:

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 2;
```

Y luego, guardaremos la imagen del código de barras generado en la ruta especificada:

```csharp
gen.Save($"{path}WideNarrow2Code39.png", BarCodeImageFormat.Png);
```

## Paso 4: Ajustar la relación ancha‑estrecha

Puede experimentar con diferentes relaciones ancha‑estrecha para lograr la apariencia deseada del código de barras. Por ejemplo, si desea un código de barras más ancho, establezca la relación ancha‑estrecha a **5**:

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 5;
```

Y guarde la imagen del código de barras:

```csharp
gen.Save($"{path}WideNarrow5Code39.png", BarCodeImageFormat.Png);
```

Ahora ha creado con éxito códigos de barras unidimensionales con diferentes relaciones ancha‑estrecha usando Aspose.BarCode para .NET. Esta biblioteca le brinda la flexibilidad de generar códigos de barras adaptados a sus requisitos específicos.

## Problemas comunes y soluciones
- **Imagen no guardada** – Verifique que la variable `path` apunte a una carpeta existente y que su aplicación tenga permisos de escritura.  
- **El código de barras aparece distorsionado** – Pruebe una relación más baja (p. ej., 2) para impresoras de baja resolución; relaciones más altas pueden causar artefactos de impresión.  
- **Caracteres no soportados** – Code 39 Extended soporta el conjunto completo de ASCII; asegúrese de que su cadena de datos no contenga caracteres de control prohibidos.

## Conclusión

Aspose.BarCode para .NET es una biblioteca versátil que simplifica la generación y personalización de códigos de barras en sus aplicaciones .NET. En este tutorial, cubrimos los conceptos básicos para crear códigos de barras unidimensionales con configuración de relación ancha‑estrecha. Con la capacidad de ajustar finamente varios parámetros, puede crear códigos de barras que se adapten perfectamente a sus necesidades, ya sea que esté construyendo una función de **cómo generar código de barras** en una aplicación de escritorio o un servicio de **generación de códigos de barras visual studio**.

## Preguntas frecuentes

### 1. ¿Cómo puedo obtener una licencia para Aspose.BarCode para .NET?
Puede comprar una licencia en el [Aspose website](https://purchase.aspose.com/buy).

### 2. ¿Puedo usar Aspose.BarCode para .NET sin una licencia?
Sí, puede usarla con una licencia temporal, que brinda funcionalidad limitada.

### 3. ¿Es Aspose.BarCode para .NET compatible con .NET Core?
Sí, Aspose.BarCode para .NET es compatible con .NET Core y .NET Framework.

### 4. ¿Existen limitaciones en los tipos de códigos de barras que puedo generar?
Aspose.BarCode para .NET soporta una amplia gama de simbologías de códigos de barras, incluyendo QR Code, Code 39 y muchas más.

### 5. ¿Cómo puedo obtener soporte o hacer preguntas sobre Aspose.BarCode para .NET?
Puede visitar el [foro de Aspose.BarCode](https://forum.aspose.com/c/barcode/13) para soporte y discusiones.

### Preguntas y respuestas adicionales

**P: ¿Cambiar la relación ancha‑estrecha afecta la velocidad de escaneo?**  
R: Una relación más alta puede hacer las barras más gruesas, lo que puede mejorar la legibilidad en escáneres de baja calidad pero puede aumentar ligeramente la cantidad de datos que el escáner procesa.

**P: ¿Puedo establecer la relación para otras simbologías como Code128?**  
R: Sí, la propiedad `WideNarrowRatio` se aplica a todas las simbologías 1D que soportan elementos anchos y estrechos.

---

**Last Updated:** 2026-03-02  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}