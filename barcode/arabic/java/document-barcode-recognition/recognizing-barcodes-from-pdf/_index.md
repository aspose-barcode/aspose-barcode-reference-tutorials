---
date: 2026-04-08
description: تعلم كيفية قراءة الباركود من ملف PDF باستخدام Java و Aspose.BarCode.
  يوضح هذا الدليل أيضًا كيفية إنشاء صورة باركود باستخدام Java واستخراج الصور من ملف
  PDF باستخدام Java.
keywords:
- read barcode from pdf java
- generate barcode image java
- extract images from pdf java
linktitle: التعرف على الباركود من ملف PDF
second_title: Aspose.BarCode Java API
title: كيفية قراءة الباركود من ملف PDF في جافا باستخدام Aspose.BarCode
url: /ar/java/document-barcode-recognition/recognizing-barcodes-from-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قراءة الباركود من PDF جافا

## مقدمة

مرحبًا بكم في دليلنا خطوة بخطوة حول **كيفية قراءة الباركود من PDF في جافا** باستخدام Aspose.BarCode. الباركودات أساسية لأتمتة جمع البيانات، ومع Aspose.BarCode يمكنك اكتشافها بسهولة داخل مستندات PDF. في هذا البرنامج التعليمي سنرشدكم إلى كل ما تحتاجون إليه — من إعداد التراخيص إلى إنشاء صورة باركود جافا، إضافتها إلى PDF، استخراج الصور من PDF جافا، وأخيرًا قراءة الباركود مرة أخرى.

## إجابات سريعة
- **ما المكتبة التي أحتاجها؟** Aspose.BarCode for Java (plus Aspose.PDF for PDF handling).  
- **هل يمكنني إنشاء صورة باركود في جافا؟** نعم – تسمح لك فئة `BarcodeGenerator` بإنشاء صور PNG/JPEG.  
- **كيف يتم استخراج الصور من PDF؟** استخدم `PdfExtractor` من Aspose.PDF.  
- **ما نوع الباركود الذي تم توضيحه؟** CODE‑39 (قياسي).  
- **هل أحتاج إلى ترخيص؟** يلزم وجود ترخيص صالح لـ Aspose.BarCode و Aspose.PDF للاستخدام في الإنتاج.

## لماذا تستخدم Aspose.BarCode لجافا؟
- **دقة عالية** – يدعم عشرات الأنظمة ويعمل على الصور منخفضة الدقة.  
- **بدون تبعيات خارجية** – جافا صافية، لا مكتبات أصلية.  
- **تكامل كامل مع PDF** – دمج مع Aspose.PDF لقراءة أو تضمين الباركود مباشرة في ملفات PDF.

## المتطلبات المسبقة

قبل الغوص في الشيفرة، تأكد من أن لديك:

1. **رخصة Aspose.BarCode لجافا** – احصل عليها من [Aspose Purchase](https://purchase.aspose.com/buy).  
2. **رخصة Aspose.PDF** – مطلوبة لمعالجة PDF؛ يمكنك طلب رخصة [هنا](https://purchase.aspose.com/temporary-license/).  
3. **مكتبة Aspose.BarCode** – حمّل أحدث JAR من [هنا](https://releases.aspose.com/barcode/java/).  

الآن بعد أن حصلت على المتطلبات اللازمة، دعنا نستورد الحزم المطلوبة ونبدأ بالبرمجة.

## استيراد الحزم

في مشروع جافا الخاص بك، أضف استيرادات Aspose.BarCode و Aspose.PDF. هذه الكتلة لا تتغير عن البرنامج التعليمي الأصلي:

```java
import com.aspose.barcode.*;
import com.aspose.barcode.License;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.BaseDecodeType;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.pdf.*;
import com.aspose.pdf.facades.PdfExtractor;
import java.awt.image.BufferedImage;
import java.io.File;
import javax.imageio.ImageIO;
```

## الخطوة 1: إنشاء صورة باركود جافا

أولاً، نقوم بإنشاء صورة باركود سنقوم لاحقًا بتضمينها في PDF. هذا يوضح قدرة **generate barcode image java**.

```java
BarcodeGenerator builder = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_39_STANDARD);
builder.setCodeText("test123");
String strBarCodeImageSave = dataDir + "input_image1.jpg";
builder.save(strBarCodeImageSave);
```

## الخطوة 2: إنشاء PDF وإضافة صورة الباركود

بعد ذلك، نبني مستند PDF جديد ونُدرج صورة الباركود التي أنشأناها للتو.

```java
Document pdf1 = new Document();
Page page = pdf1.getPages().add();
BufferedImage originalImage = ImageIO.read(new File(strBarCodeImageSave));
page.getResources().getImages().add(originalImage);
pdf1.save(strPdfDoc);
```

## الخطوة 3: استخراج الصور من PDF جافا

مع جاهزية PDF، نحتاج إلى استخراج الصورة المدمجة مرة أخرى حتى يتم قراءة الباركود. هذا يستخدم **extract images from pdf java**.

```java
PdfExtractor extractor = new PdfExtractor();
extractor.bindPdf(strPdfDoc);
extractor.extractImage();
```

## الخطوة 4: التعرف على الباركود من الصور المستخرجة

أخيرًا، نمرّر كل صورة مستخرجة إلى `BarCodeReader` لاسترجاع النص المشفر.

```java
String suffix = ".jpg";
int imageCount = 1;

while (extractor.hasNextImage()) {
    System.out.println("Extracting image " + imageCount);
    strBarCodeImage = "tmpbarcode" + imageCount + suffix;
    extractor.getNextImage(strBarCodeImage);

    BarCodeReader reader = new BarCodeReader(strBarCodeImage, DecodeType.CODE_39_EXTENDED);

    for (BarCodeResult result : reader.readBarCodes()) {
        System.out.println("CodeText: " + result.getCodeText());
        System.out.println("Symbology type: " + result.getCodeType());
    }

    imageCount++;
}
```

كرر هذه الخطوات حسب الحاجة، مع تعديل أسماء الملفات والمسارات لتتناسب مع بنية مشروعك.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|--------|-----|
| **لم يتم اكتشاف أي باركود** | جودة الصورة منخفضة جدًا أو الباركود صغير جدًا. | زيادة دقة الصورة عند الحفظ (`builder.save(..., BarCodeImageFormat.JPEG, 300)`). |
| **`PdfExtractor` يطرح استثناء** | ملف PDF غير موجود أو المسار غير صحيح. | تحقق من أن `strPdfDoc` يشير إلى ملف موجود وأن التطبيق لديه أذونات القراءة. |
| **لم يتم تطبيق الترخيص** | مكونات Aspose تعمل في وضع التجربة، مما يحد من الإخراج. | حمّل ملفات الترخيص في بداية برنامجك: `new License().setLicense("Aspose.BarCode.lic");` وبنفس الطريقة لـ Aspose.PDF. |

## الأسئلة المتكررة (FAQs)

### س: هل يمكنني استخدام Aspose.BarCode لجافا بدون ترخيص؟
على الرغم من إمكانية استخدام Aspose.BarCode بدون ترخيص، يُنصح بالحصول على ترخيص للحصول على الوظائف الكاملة والامتثال لشروط الترخيص.

### س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.BarCode لجافا؟
يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

### س: هل هناك أي قيود على أنواع الباركود المدعومة من قبل Aspose.BarCode؟
يدعم Aspose.BarCode مجموعة واسعة من أنواع الباركود. راجع الوثائق للحصول على القائمة الكاملة.

### س: هل هناك نسخة تجريبية متاحة لـ Aspose.BarCode لجافا؟
نعم، يمكنك تنزيل النسخة التجريبية من [هنا](https://releases.aspose.com/).

### س: أين يمكنني طلب الدعم أو طرح الأسئلة حول Aspose.BarCode لجافا؟
قم بزيارة منتدى Aspose.BarCode [المنتدى](https://forum.aspose.com/c/barcode/13) للحصول على الدعم والنقاشات.

## الخاتمة

تهانينا! لقد تعلمت كيفية **قراءة الباركود من PDF في جافا** باستخدام Aspose.BarCode، وكيفية **إنشاء صورة باركود جافا**، وكيفية **استخراج الصور من PDF جافا** للمعالجة الإضافية. لا تتردد في استكشاف ميزات إضافية مثل المعالجة الدفعية، التعامل مع أنظمة باركود مختلفة، أو التكامل مع منتجات Aspose الأخرى. للحصول على تفاصيل أعمق، راجع [الوثائق](https://reference.aspose.com/barcode/java/) الرسمية.

---

**Last Updated:** 2026-04-08  
**Tested With:** Aspose.BarCode for Java 24.12, Aspose.PDF for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}