---
date: 2026-06-14
description: Aprenda cómo generar códigos de barras DotCode con Aspose.BarCode para
  .NET, cubriendo la relación de aspecto, modos de codificación, texto extendido y
  la inicialización del lector.
keywords:
- how to generate dotcode
- dotcode barcode configuration
- aspose barcode .net
linktitle: Cómo generar códigos de barras DotCode – Guía de configuración
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to generate DotCode barcodes with Aspose.BarCode for .NET,
    covering aspect ratio, encoding modes, extended text, and reader initialization.
  headline: How to Generate DotCode Barcodes – Configuration Guide
  type: TechArticle
- questions:
  - answer: Yes, set `BarCodeImageFormat = BarCodeImageFormat.Svg` on the generator
      to receive a scalable vector output.
    question: Can I generate DotCode barcodes in SVG format?
  - answer: Aspose.BarCode does not support direct logo embedding for DotCode, but
      you can overlay an image after generation using standard graphics libraries.
    question: Is it possible to embed a logo inside a DotCode symbol?
  - answer: The symbology includes built‑in Reed‑Solomon error correction; increasing
      rows/columns automatically raises the correction level.
    question: How does error correction work for DotCode?
  - answer: No, the same `BarCodeReader` can extract DotCode from PDF pages, images,
      or streams without additional tools.
    question: Do I need a separate library to read DotCode from a PDF?
  - answer: Up to **1 200** numeric or **800** alphanumeric characters, depending
      on the chosen rows/columns configuration.
    question: What is the maximum data size for a single DotCode symbol?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Cómo generar códigos de barras DotCode – Guía de configuración
url: /es/net/dotcode-barcode-configuration/
weight: 32
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo generar códigos de barras DotCode – Guía de configuración

## Introducción
**Cómo generar DotCode** los códigos de barras de forma rápida y fiable es un requisito común para los desarrolladores que crean soluciones de inventario, seguimiento o escaneo móvil. En este tutorial le guiaremos a través de cada opción de configuración que Aspose.BarCode para .NET ofrece para los símbolos DotCode: ajustes de relación de aspecto, modos de codificación Auto y Bytes, manejo de texto de código extendido, inicialización del lector, diseño de filas/columnas y modo de anexado estructurado. Al final podrá producir imágenes DotCode de tamaño perfecto y alta densidad que cumplen con los estándares de la industria e integran sin problemas en cualquier aplicación .NET.

## Respuestas rápidas
- **¿Cuál es la clase principal para crear un código de barras DotCode?** `BarcodeGenerator` with `EncodeTypes.DotCode`.
- **¿Qué propiedad controla la relación de aspecto?** `BarCodeImageAspectRatio`.
- **¿Puedo cambiar entre la codificación Auto y Bytes?** Yes, via `EncodeMode` property.
- **¿Se requiere un lector separado para DotCode?** No, the same `BarcodeGenerator` can decode when `ReadBarcode` is called.
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Cómo generar códigos de barras DotCode usando Aspose.BarCode para .NET?
`BarcodeGenerator` es la clase principal en Aspose.BarCode para crear imágenes de códigos de barras. Cargue el `BarcodeGenerator` con `EncodeTypes.DotCode`, establezca las propiedades deseadas (relación de aspecto, modo de codificación, filas/columnas, etc.) y llame a `GenerateBarCodeImage()`—la biblioteca devuelve un `System.Drawing.Image` listo para usar o una matriz de bytes. Este flujo de trabajo de un solo paso maneja todos los detalles de codificación de bajo nivel, admite formatos de salida como PNG, JPEG y SVG, y puede renderizar imágenes de hasta 10 000 × 10 000 px sin consumir memoria excesiva.

## ¿Qué es un código de barras DotCode?
Un código de barras DotCode es una simbología 2D de alta densidad y forma cuadrada que almacena hasta 1 200 caracteres numéricos o 800 alfanuméricos en una matriz compacta de puntos. Está optimizado para el etiquetado de paquetes pequeños y el escaneo móvil, ofreciendo tasas de lectura rápidas incluso con cámaras de baja resolución.

## ¿Por qué usar DotCode con Aspose.BarCode?
Aspose.BarCode soporta **20+** tipos de códigos de barras 2D, incluido DotCode, y puede procesar archivos de más de **200 MB** sin cargar la imagen completa en memoria. La biblioteca garantiza una precisión de escaneo de **99.9 %** en cámaras de smartphones estándar y proporciona niveles de corrección de errores integrados para minimizar fallos de lectura.

## Requisitos previos
- .NET Framework 4.5 o superior, o .NET Core 3.1 / .NET 5+.
- Aspose.BarCode para .NET (se recomienda la última versión).
- Una clave de licencia temporal o completa (la versión de prueba funciona para desarrollo).

## Personalización de la relación de aspecto de DotCode
La **relación de aspecto** determina cómo se ve estirada o comprimida la matriz DotCode. Use la propiedad `BarCodeImageAspectRatio` para establecer un valor entre **0.5** (más alta) y **2.0** (más ancha). Una proporción de **1.0** produce un símbolo perfectamente cuadrado, que es el valor predeterminado y funciona mejor para la mayoría de los escáneres.

> **Consejo:** Al imprimir en etiquetas estrechas, una proporción de **0.75** a menudo mejora la legibilidad sin sacrificar la capacidad de datos.

## Modo de codificación DotCode (Auto)
En modo **Auto** la biblioteca analiza la cadena de entrada y selecciona automáticamente la codificación más eficiente (numérica, alfanumérica o de bytes). Esto maximiza la densidad de datos y reduce el tamaño total del símbolo.

> **Respuesta directa:** Establezca `EncodeMode = EncodeModes.Auto` en el `BarcodeGenerator` para que Aspose.BarCode decida la codificación óptima para sus datos, garantizando el DotCode más pequeño posible mientras se conservan todos los caracteres.

## Modo de codificación DotCode (Bytes)
Cuando necesita almacenar datos binarios o matrices de bytes pre‑codificadas, elija el modo **Bytes**. Esto obliga al generador a tratar la entrada como bytes crudos, evitando la detección automática del conjunto de caracteres.

> **Respuesta directa:** Use `EncodeMode = EncodeModes.Bytes` y proporcione una carga útil `byte[]` para incrustar información binaria como identificadores encriptados o archivos comprimidos directamente en el símbolo DotCode.

## Configuración de texto de código extendido DotCode
El texto de código extendido le permite adjuntar información suplementaria que no forma parte de la carga de datos principal pero que puede mostrarse junto al código de barras en informes o interfaces gráficas. Establezca la propiedad `ExtendedCodeText` a cualquier cadena (hasta **256** caracteres) y elija una fuente mediante `ExtendedCodeTextFont`.

> **Consejo profesional:** Combine el texto extendido con un tamaño de fuente más pequeño (p. ej., 8 pt) para mantener una huella visual reducida mientras sigue proporcionando contexto legible para humanos.

## Inicialización del lector DotCode
`BarCodeReader` es la clase utilizada para decodificar códigos de barras a partir de imágenes o flujos. Leer una imagen DotCode es tan sencillo como generarla. Instancie un `BarCodeReader` con el flujo de imagen y especifique `EncodeTypes.DotCode`. Llame a `ReadBarCode()` para obtener la cadena decodificada.

> **Respuesta directa:** `using (var reader = new BarCodeReader(imageStream, DecodeType.DotCode)) { if (reader.ReadBarCode()) { string data = reader.GetCodeText(); } }` – este bloque único decodifica el símbolo sin dependencias externas.

## Configuración de filas y columnas DotCode
DotCode permite un control explícito sobre el número de filas y columnas, lo que influye en el tamaño del símbolo y la capacidad de corrección de errores. Use las propiedades `Rows` y `Columns` para establecer valores entre **10** y **144**. Las matrices más grandes aumentan la capacidad de datos y la robustez.

> **Mejor práctica:** Para etiquetas de inventario que deben resistir un manejo brusco, configure **Rows = 64** y **Columns = 64** para añadir redundancia extra.

## Configuración del modo de anexado estructurado DotCode
Anexado estructurado permite dividir una carga útil grande en varios símbolos DotCode que pueden leerse secuencialmente. Establezca `StructuredAppend = true` y defina `StructuredAppendCount` y `StructuredAppendIndex` para cada parte.

> **Respuesta directa:** Habilite `StructuredAppend` en cada `BarcodeGenerator`, asigne un índice único (comenzando en 1) y establezca el recuento total; la biblioteca incrustará automáticamente la información de enlace necesaria.

## Problemas comunes y soluciones
- **Código de barras ilegible en pantallas de baja resolución:** Aumente la propiedad `Resolution` a al menos **300 dpi** antes de la generación.
- **Advertencias de truncamiento de datos:** Verifique que la longitud de entrada no exceda el máximo para las filas/columnas seleccionadas; ajuste el tamaño o cambie al modo Bytes si es necesario.
- **Expiración de la licencia durante el desarrollo:** Utilice una licencia temporal obtenida del portal de Aspose; reemplácela con una clave permanente antes del despliegue en producción.

## Preguntas frecuentes

**P: ¿Puedo generar códigos de barras DotCode en formato SVG?**  
A: Sí, establezca `BarCodeImageFormat = BarCodeImageFormat.Svg` en el generador para recibir una salida vectorial escalable.

**P: ¿Es posible incrustar un logotipo dentro de un símbolo DotCode?**  
A: Aspose.BarCode no soporta la incrustación directa de logotipos para DotCode, pero puede superponer una imagen después de la generación usando bibliotecas gráficas estándar.

**P: ¿Cómo funciona la corrección de errores para DotCode?**  
A: La simbología incluye corrección de errores Reed‑Solomon integrada; aumentar filas/columnas eleva automáticamente el nivel de corrección.

**P: ¿Necesito una biblioteca separada para leer DotCode de un PDF?**  
A: No, el mismo `BarCodeReader` puede extraer DotCode de páginas PDF, imágenes o flujos sin herramientas adicionales.

**P: ¿Cuál es el tamaño máximo de datos para un solo símbolo DotCode?**  
A: Hasta **1 200** numéricos o **800** alfanuméricos, según la configuración de filas/columnas elegida.

---

**Última actualización:** 2026-06-14  
**Probado con:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose  

## Tutoriales de configuración de códigos de barras DotCode
### [Personalizar la relación de aspecto DotCode](./dotcode-aspect-ratio-customization/)
Aprenda a personalizar la relación de aspecto del código de barras DotCode usando Aspose.BarCode para .NET. Cree códigos de barras a medida para sus aplicaciones sin esfuerzo.
### [Modo de codificación DotCode (Auto)](./dotcode-encoding-mode-auto/)
Explore el modo de codificación DotCode (Auto) en Aspose.BarCode para .NET, una herramienta poderosa para la generación de códigos de barras. Aprenda cómo generar códigos de barras DotCode paso a paso. Consulte la documentación, descargue la biblioteca y obtenga licencias temporales.
### [Modo de codificación DotCode (Bytes)](./dotcode-encoding-mode-bytes/)
Aprenda la codificación DotCode con Aspose.BarCode para .NET: Guía paso a paso para generar códigos de barras.
### [Configuración de texto de código extendido DotCode](./dotcode-extended-code-text-configuration/)
Genere la configuración de texto de código extendido DotCode con facilidad usando Aspose.BarCode para .NET. Siga nuestra guía paso a paso para una creación eficiente de códigos de barras.
### [Inicialización del lector DotCode](./dotcode-reader-initialization/)
Aprenda cómo inicializar el lector DotCode usando Aspose.BarCode para .NET. Cree códigos de barras DotCode con facilidad para diversas aplicaciones.
### [Configuración de filas y columnas DotCode](./dotcode-rows-columns-configuration/)
Aprenda a configurar filas y columnas DotCode con Aspose.BarCode para .NET. Genere códigos de barras 2D precisos y personalizables sin esfuerzo.
### [Configuración del modo de anexado estructurado DotCode](./dotcode-structured-append-mode-configuration/)
Aprenda a configurar el modo de anexado estructurado DotCode con Aspose.BarCode para .NET y crear códigos de barras eficientes.

## Tutoriales relacionados
- [Personalizar la relación de aspecto DotCode con Aspose.BarCode para .NET](/barcode/net/dotcode-barcode-configuration/dotcode-aspect-ratio-customization/)
- [Configuración de texto de código extendido DotCode con Aspose.BarCode para .NET](/barcode/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Modo de codificación DotCode (Auto) en Aspose.BarCode para .NET](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}