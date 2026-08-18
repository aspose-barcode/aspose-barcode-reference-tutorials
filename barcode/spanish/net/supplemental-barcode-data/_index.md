---
date: 2026-03-07
description: Aprende cómo crear códigos de barras EAN‑2 y generar códigos de barras
  en .NET usando Aspose.BarCode para .NET. ¡Domina la personalización de datos complementarios
  del código de barras hoy mismo!
linktitle: Supplemental Barcode Data
second_title: Aspose.BarCode .NET API
title: Crear código de barras EAN-2 con Aspose.BarCode para .NET
url: /es/net/supplemental-barcode-data/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear código de barras EAN-2 con Aspose.BarCode para .NET

## Introducción

Si eres un desarrollador .NET que busca **crear un código de barras EAN-2** y desbloquear el poder de los datos de código de barras suplementarios, estás en el lugar correcto. En esta guía completa te acompañaremos paso a paso con todo lo que necesitas saber, desde la configuración básica hasta el ajuste fino del espacio alrededor de tus símbolos. Ya sea que estés construyendo un nuevo sistema de inventario o mejorando una aplicación de punto de venta existente, dominar estas funciones hará que tus proyectos de generación de códigos de barras .NET sean más flexibles y confiables.

## Respuestas rápidas
- **¿Qué puedo generar?** Códigos de barras suplementarios EAN‑2 y EAN‑5.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **¿Cuánto código se necesita?** Solo unas pocas líneas: Aspose.BarCode se encarga del trabajo pesado.  
- **¿Puedo personalizar el espaciado?** Sí, puedes controlar la X‑dimension y el espacio suplementario directamente.

## ¿Qué son los datos de código de barras suplementarios?

Los datos de código de barras suplementarios se refieren a los pequeños símbolos adicionales (EAN‑2, EAN‑5) que aparecen junto a un código de barras principal, típicamente usados para números de edición, extensiones de precio u otra información auxiliar. Aspose.BarCode para .NET te permite generar estos símbolos programáticamente, dándote control total sobre su apariencia y ubicación.

## ¿Por qué usar Aspose.BarCode para .NET?

- **Integración completa con .NET** – funciona con C#, VB.NET y F#.  
- **Renderizado de alta calidad** – produce códigos de barras escaneables a cualquier resolución.  
- **Personalización extensa** – desde el tipo de simbología hasta X‑dimension, zonas silenciosas y espacio suplementario.  
- **Sin dependencias externas** – biblioteca totalmente administrada, fácil de desplegar.

## Configuración de datos de código de barras suplementarios

Comencemos adentrándonos en el ámbito de la configuración de datos de código de barras suplementarios. Aspose.BarCode para .NET te ofrece las herramientas para generar códigos suplementarios sin esfuerzo, dándote control completo sobre los códigos EAN‑2 y EAN‑5. ¿Pero cómo se empieza?

Primero, descarga e instala Aspose.BarCode para .NET. Puedes explorar una prueba gratuita para probar sus potentes funciones. Una vez configurado, sigue nuestra guía paso‑a‑paso, que te llevará a través del proceso, asegurando que domines la configuración de datos de código de barras suplementarios con facilidad.

Al final de esta sección, tendrás una comprensión sólida de cómo crear códigos de barras EAN‑2 y EAN‑5, convirtiéndote en un desarrollador .NET más versátil.

## ¿Cómo crear un código de barras EAN-2? (Pasos de configuración)

1. **Instanciar el generador de códigos de barras** – elige la clase `BarcodeGenerator` y establece la simbología a `EncodeTypes.EAN13` (u otro tipo principal).  
2. **Habilitar la parte suplementaria** – asigna la propiedad `SupplementData` a la cadena numérica deseada (p. ej., `"12"` para un suplemento EAN‑2).  
3. **Ajustar la configuración visual** – opcionalmente modifica `XDimension`, `BarHeight` y `QuietZone` para que coincidan con los requisitos de tu diseño.  
4. **Guardar o renderizar** – llama a `Save` para escribir la imagen en un archivo o flujo.

> *Consejo profesional:* Mantén la longitud de los datos suplementarios exactamente en 2 dígitos para EAN‑2 y 5 dígitos para EAN‑5; de lo contrario el código de barras podría volverse ilegible.

## Personalización del espacio del código de barras suplementario

En el mundo de los códigos de barras, la personalización es clave, y ahí es donde Aspose.BarCode para .NET brilla. Ahora, centrémonos en la personalización del espacio del código de barras suplementario. Este aspecto se trata de controlar la X‑Dimension y el espacio suplementario en tus códigos.

Una vez más, comenzarás instalando Aspose.BarCode para .NET y aprovechando la prueba gratuita. Luego, seguirás nuestras indicaciones sobre cómo ajustar el espacio en tus códigos de barras. Esta personalización puede ser increíblemente útil para diversas aplicaciones, desde la gestión de inventario hasta sistemas de punto de venta.

La libertad de adaptar tus códigos de barras a necesidades específicas es una habilidad valiosa, y esta sección se asegurará de que estés bien equipado.

## ¿Cómo personalizar el espacio suplementario?

- **X‑Dimension** – define el ancho de un módulo único; valores mayores aumentan el tamaño total del código de barras.  
- **Espacio suplementario** – la separación entre el código de barras principal y la parte suplementaria; se ajusta mediante la propiedad `SupplementSpace`.  
- **Zona silenciosa** – el margen en blanco obligatorio alrededor de todo el código de barras; mantenlo al menos en 10 unidades de X‑Dimension para un escaneo fiable.

Experimenta con estos ajustes en un proyecto de prueba hasta lograr el equilibrio visual requerido por tu hardware de escaneo.

## Casos de uso comunes

| Escenario | Por qué los datos suplementarios ayudan |
|----------|------------------------------------------|
| **Extensiones de precio en retail** | EAN‑5 puede codificar la información de precio directamente en la etiqueta. |
| **Números de edición de revistas** | EAN‑2 identifica la edición, permitiendo una clasificación rápida. |
| **Logística y seguimiento** | Añadir un pequeño suplemento a un código principal brinda datos de ruta adicionales sin expandir el tamaño de la etiqueta. |

## Tutoriales de datos de código de barras suplementarios
### [Configuración de datos de código de barras suplementarios](./supplemental-barcode-data-configuration/)
Genera datos de código de barras suplementarios con Aspose.BarCode para .NET. Personaliza códigos EAN-2 y EAN-5 sin esfuerzo. Guía paso a paso para desarrolladores .NET.
### [Personalización del espacio del código de barras suplementario](./supplemental-barcode-space-customization/)
Personaliza códigos de barras fácilmente con Aspose.BarCode para .NET. Controla X‑Dimension y espacio suplementario. ¡Prueba la versión gratuita!

## Preguntas frecuentes

**P: ¿Puedo generar tanto EAN‑2 como EAN‑5 con el mismo código?**  
R: Sí. Simplemente cambia la longitud de `SupplementData` (2 dígitos para EAN‑2, 5 dígitos para EAN‑5) y la biblioteca renderizará la simbología correcta.

**P: ¿Necesito calcular valores de checksum para el suplemento?**  
R: No. Aspose.BarCode calcula y agrega automáticamente el checksum requerido.

**P: ¿Hay un límite de cuántos códigos de barras puedo generar en un bucle?**  
R: La biblioteca está optimizada para generación masiva; solo ten en cuenta el uso de memoria al manejar colecciones de imágenes muy grandes.

**P: ¿Cómo incrusto el código de barras en un documento PDF o Word?**  
R: Guarda el código de barras como imagen (PNG, JPEG, etc.) y luego insértalo usando la API de generación de documentos que prefieras (p. ej., Aspose.PDF o Aspose.Words).

**P: ¿Qué hago si mi escáner no puede leer la parte suplementaria?**  
R: Verifica que `SupplementSpace` sea al menos 2 X‑Dimension unidades y que la zona silenciosa cumpla con las especificaciones del escáner.

---

**Última actualización:** 2026-03-07  
**Probado con:** Aspose.BarCode para .NET 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}