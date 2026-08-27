---
date: 2026-04-12
description: تعلم كيفية إنشاء رمز شريطي Code128 بأعمدة فارغة في Java باستخدام Aspose.BarCode.
  يوضح لك هذا الدليل كيفية إنشاء صور رموز شريطية Java بسرعة.
keywords:
- create code128 barcode
- generate barcode java
- barcode generator java example
- java generate barcode image
linktitle: إنشاء رمز شريطي بأشرطة فارغة
second_title: Aspose.BarCode Java API
title: كيفية إنشاء باركود Code128 بأشرطة فارغة في جافا
url: /ar/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء باركود Code128 بأشرطة فارغة في Java

## مقدمة

إن دمج توليد الباركود في تطبيقات Java هو طلب شائع، سواء كنت تبني أنظمة جرد، أو منصات حجز تذاكر، أو حلول نقاط البيع. باستخدام **Aspose.BarCode for Java**، يمكنك **إنشاء صور باركود Code128** ببضع أسطر من الشيفرة فقط. في هذا البرنامج التعليمي سنستعرض الخطوات **لإنشاء صور باركود Java** التي تحتوي على أشرطة فارغة (غير مملوءة)، مما يمنحك تحكمًا كاملاً في النمط البصري للباركود.

## إجابات سريعة
- **Which library?** Aspose.BarCode for Java  
- **Primary use case?** Creating Code128 barcodes with empty bars for custom UI designs  
- **Prerequisites?** Java JDK 8+, Aspose.BarCode JAR, write access to a folder for the output image  
- **Typical implementation time?** 5‑10 minutes for a basic example  
- **Can I customize colors?** Yes – the API provides extensive styling options  

## ما هو باركود Code128؟

Code128 هو نظام باركود خطي عالي الكثافة يقوم بترميز مجموعة أحرف ASCII بالكامل. يُستخدم على نطاق واسع في اللوجستيات والشحن والتجزئة لأنه يمكنه تمثيل البيانات الحرفية والعددية بشكل مضغوط. بشكل افتراضي، يقوم Aspose.BarCode بعرض أشرطة Code128 كـ rectangles صلبة؛ ضبط خاصية **FilledBars** إلى `false` يحولها إلى أشرطة فارغة (محددة بالحدود)، وهو مفيد للعلامة التجارية ذات الطابع التصميمي.

## لماذا تستخدم Aspose.BarCode for Java؟

- **Rich feature set** – supports over 50 barcode types, including QR, DataMatrix, and PDF417.  
- **No external dependencies** – a single JAR works on any Java runtime.  
- **Fine‑grained control** – you can adjust bar width, colors, fonts, and the `FilledBars` property.  
- **Cross‑platform** – works on Windows, Linux, and macOS without native libraries.  

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من أن لديك:

1. **Java Development Environment** – JDK 8 or later installed and `JAVA_HOME` configured.  
2. **Aspose.BarCode for Java** – download the latest JAR from the [download page](https://releases.aspose.com/barcode/java/).  
3. **Document Directory** – a folder on your computer where the generated barcode image will be saved.  

## استيراد الحزم

في مشروع Java الخاص بك، استورد الفئات التي ستحتاجها للعمل مع Aspose.BarCode:

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

هذه الاستيرادات تمنحك الوصول إلى مولد الباركود، تعداد صيغ الصورة، ومعالجة الاستثناءات.

## الخطوة 1: إعداد دليل الموارد

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

استبدل `"Your Document Directory"` بالمسار المطلق للمجلد الذي أنشأته في المتطلبات المسبقة. هذا هو المكان الذي سيُكتب فيه ملف PNG.

## الخطوة 2: إنشاء كائن مولد باركود Code128

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

هنا نقوم بإنشاء مثيل `BarcodeGenerator` باستخدام رموز **CODE_128** والنص التجريبي `"TEXT"`. هذا مثال **barcode generator Java** يمكنك تعديله لأي سلسلة تحتاج إلى ترميزها.

## الخطوة 3: ضبط خاصية FilledBars إلى False

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

عن طريق ضبط `FilledBars` إلى `false`، سيظهر الباركود المولد بأشرطة فارغة بدلاً من الصلبة، محققًا التأثير البصري المطلوب.

## الخطوة 4: حفظ صورة الباركود

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

طريقة `save` تكتب الباركود إلى الدليل المحدد بصيغة PNG. يمكنك تغيير `BarCodeImageFormat.PNG` إلى `JPG` أو `BMP` أو `TIFF` إذا احتجت نوع صورة مختلف.

## حالات الاستخدام الشائعة

- **Custom branding** – empty bars can be overlaid with background patterns or colors.  
- **Print‑ready assets** – generate high‑resolution PNGs for inclusion in invoices or shipping labels.  
- **Dynamic generation** – create barcodes on the fly in web services or desktop applications.  

## نصائح استكشاف الأخطاء وإصلاحها

- **Invalid path** – ensure `dataDir` ends with a file separator (`/` or `\\`) or concatenate using `File.separator`.  
- **License required** – a trial works for evaluation, but a full license is needed for production.  
- **Unsupported characters** – Code128 supports the full ASCII set; avoid Unicode characters unless you switch to a different symbology.  

## الخاتمة

لقد تعلمت الآن كيفية **إنشاء باركود Code128** بصور أشرطة فارغة باستخدام Aspose.BarCode for Java. هذه الطريقة المبسطة تتيح لك توليد رسومات باركود قابلة للتخصيص بسرعة، سواء كنت تبني أداة جرد سطح مكتب أو واجهة برمجة تطبيقات سحابية.

## الأسئلة الشائعة

### Is Aspose.BarCode compatible with all Java development environments?
Yes, Aspose.BarCode is designed to seamlessly integrate with any Java IDE or build system, including Maven, Gradle, and plain JAR projects.

### Can I customize the appearance of the generated barcode?
Absolutely! Apart from `FilledBars`, you can modify colors, bar width, margins, and even add human‑readable text using the extensive API.

### Is a trial version available for Aspose.BarCode?
Yes, you can explore the capabilities of Aspose.BarCode by obtaining a free trial [here](https://releases.aspose.com/).

### How can I get support for Aspose.BarCode?
For any queries or assistance, visit the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13).

### Where can I find detailed documentation for Aspose.BarCode?
The comprehensive documentation is available [here](https://reference.aspose.com/barcode/java/).

**Additional Questions**

**Q: How do I generate a barcode image in a different format, such as JPEG?**  
A: Change the second argument of `save` to `BarCodeImageFormat.JPEG`.

**Q: Can I generate multiple barcodes in a loop?**  
A: Yes – instantiate a new `BarcodeGenerator` inside your loop or reuse the same instance with a new `CodeText`.

---

**Last Updated:** 2026-04-12  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}