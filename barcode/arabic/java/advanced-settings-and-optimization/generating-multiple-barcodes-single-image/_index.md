---
title: إنشاء رموز شريطية متعددة على صورة واحدة في Java باستخدام Aspose.BarCode
linktitle: إنشاء رموز شريطية متعددة على صورة واحدة
second_title: Aspose.BarCode جافا API
description: قم بإنشاء رموز شريطية متعددة على صورة واحدة بسهولة باستخدام Aspose.BarCode لـ Java. اتبع دليلنا خطوة بخطوة للتكامل السلس.
weight: 19
url: /ar/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء رموز شريطية متعددة على صورة واحدة في Java باستخدام Aspose.BarCode

## مقدمة

في عالم برمجة Java الديناميكي، يعد إنشاء الرموز الشريطية وإدارتها بكفاءة أمرًا بالغ الأهمية لمختلف التطبيقات. يعمل Aspose.BarCode for Java على تبسيط هذه العملية، مما يسمح للمطورين بإنشاء رموز شريطية متعددة على صورة واحدة بسلاسة. سيرشدك هذا البرنامج التعليمي خلال خطوات تحقيق ذلك باستخدام Aspose.BarCode في بيئة Java.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:

- الفهم الأساسي لبرمجة جافا.
- تم تثبيت Java Development Kit (JDK) على نظامك.
- تم تنزيل وإعداد Aspose.BarCode لمكتبة Java. يمكنك تنزيله[هنا](https://releases.aspose.com/barcode/java/).
- بيئة تطوير متكاملة (IDE) مثل Eclipse أو IntelliJ IDEA.

## استيراد مساحات الأسماء

في مشروع Java الخاص بك، قم باستيراد مساحات الأسماء الضرورية للوصول إلى وظيفة Aspose.BarCode. أضف عبارات الاستيراد التالية في بداية فئة Java الخاصة بك:

```java
import java.awt.Color;
import java.awt.Graphics;
import java.awt.image.BufferedImage;
import java.io.File;
import java.util.ArrayList;
import java.util.HashMap;

import javax.imageio.ImageIO;

import com.aspose.barcode.BaseEncodeType;
import com.aspose.barcode.EncodeTypes;


import com.aspose.barcode.generation.BarcodeGenerator;
```

## الخطوة 1: قم بتعيين دليل الموارد

حدد المسار إلى دليل الموارد حيث سيتم حفظ الرموز الشريطية التي تم إنشاؤها. يعد هذا الدليل ضروريًا لتنظيم وإدارة صور الباركود الخاصة بك.

```java
// المسار إلى دليل الموارد.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## الخطوة 2: إنشاء مجموعة من الرموز الشريطية

قم بتهيئة HashMap لتخزين بيانات الباركود. يمثل كل إدخال في المجموعة رمزًا شريطيًا بنوع التشفير الخاص به.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## الخطوة 3: إنشاء صور الباركود

قم بالتكرار عبر المجموعة وإنشاء صور الباركود باستخدام مكتبة Aspose.BarCode. قم بتخزين الصور في ArrayList لمزيد من المعالجة.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## الخطوة 4: إنشاء صورة مدمجة

تحديد الحد الأقصى للعرض والارتفاع الإجمالي لصور الباركود. قم بإنشاء BufferedImage لدمج صور الباركود الفردية في صورة مخرجة واحدة.

```java
int maxWidth = 0;
int sumHeight = 0;
for (BufferedImage bmp : images) {
    sumHeight += bmp.getHeight();
    if (maxWidth < bmp.getWidth())
        maxWidth = bmp.getWidth();
}

int offset = 10;
BufferedImage resultBitmap = new BufferedImage(maxWidth + offset * 2, sumHeight + offset * images.size(),
        BufferedImage.TYPE_INT_ARGB);
Graphics g = resultBitmap.getGraphics();
g.setColor(Color.white);
g.fillRect(0, 0, resultBitmap.getWidth(), resultBitmap.getHeight());

int yPosition = offset;
for (int i = 0; i < images.size(); ++i) {
    BufferedImage currentBitmap = images.get(i);
    g.drawImage(currentBitmap, offset, yPosition, null);
    yPosition += currentBitmap.getHeight() + offset;
}
```
## الخطوة 5: حفظ النتيجة

احفظ الصورة المدمجة النهائية في موقع ملف محدد.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## خاتمة

تهانينا! لقد نجحت في إنشاء رموز شريطية متعددة على صورة واحدة باستخدام Aspose.BarCode لـ Java. تعمل هذه المكتبة القوية على تبسيط عملية التعامل مع الباركود، مما يجعلها أداة لا تقدر بثمن لمطوري Java.

## الأسئلة الشائعة

### س1: هل يمكنني تخصيص مظهر الرموز الشريطية الفردية في الصورة التي تم إنشاؤها؟

ج1: نعم، يوفر Aspose.BarCode خيارات تخصيص واسعة النطاق لمظهر الرمز الشريطي، مما يسمح لك بتخصيص نمط كل رمز شريطي حسب تفضيلاتك.

### س2: هل Aspose.BarCode متوافق مع رموز الباركود المختلفة؟

ج2: بالتأكيد! يدعم Aspose.BarCode نطاقًا واسعًا من الرموز، بما في ذلك CODE_39 وDATA_MATRIX وQR وCODE_128 وEAN_13 وAZTEC، كما هو موضح في هذا البرنامج التعليمي.

### س3: كيف يمكنني دمج Aspose.BarCode في مشروع Java الخاص بي؟

 ج3: ما عليك سوى تنزيل مكتبة Aspose.BarCode for Java من[هنا](https://releases.aspose.com/barcode/java/) واتبع تعليمات التثبيت المتوفرة في الوثائق.

### س4: هل يمكنني استخدام Aspose.BarCode للتطبيقات التجارية؟

 ج4: نعم، يمكنك الحصول على ترخيص من[هنا](https://purchase.aspose.com/buy) لاستخدام Aspose.BarCode لأغراض تجارية.

### س5: هل هناك أي خيارات تجريبية متاحة لـ Aspose.BarCode؟

 ج5: بالتأكيد! يمكنك استكشاف ميزات Aspose.BarCode من خلال الحصول على ترخيص تجريبي مجاني[هنا](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
