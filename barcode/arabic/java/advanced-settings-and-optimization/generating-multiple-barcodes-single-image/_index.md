---
date: 2026-04-03
description: تعلم كيفية إنشاء رمز QR في جافا وتوليد عدة باركودات على صورة واحدة باستخدام
  Aspose.BarCode للغة جافا. يتضمن الإعداد، الكود، واستكشاف الأخطاء وإصلاحها.
keywords:
- create qr code java
- aspose barcode java
- generate barcodes java
linktitle: إنشاء عدة رموز شريطية على صورة واحدة
second_title: Aspose.BarCode Java API
title: إنشاء رمز QR باستخدام Java – توليد عدة باركودات على صورة واحدة
url: /ar/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء رمز QR Java – إنشاء عدة باركودات على صورة واحدة

## مقدمة

في هذا الدرس، ستتعلم **كيفية إنشاء رمز QR Java** ودمج عدة أنواع مختلفة من الباركود في صورة واحدة باستخدام **Aspose.BarCode for Java**. سواء كنت تحتاج إلى ملصق QR مدمج، أو باركود للمنتج، أو مزيج من الرموز الثنائية الأبعاد والرموز الخطية، يوجهك هذا الدليل خلال كل خطوة — من إعداد المشروع إلى حفظ الصورة المدمجة النهائية — حتى تتمكن من بدء دمج توليد الباركود في تطبيقات Java الخاصة بك على الفور.

## إجابات سريعة
- **ما المكتبة التي يجب أن أستخدمها؟** Aspose.BarCode for Java توفر مجموعة الرموز الأكثر اكتمالاً.  
- **هل يمكنني توليد أنواع مختلفة من الباركود معًا؟** نعم، يمكنك خلط CODE_39 و QR و AZTEC وغيرها على لوحة واحدة.  
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تعمل للاختبار؛ يلزم ترخيص تجاري للإنتاج.  
- **ما نسخة Java المدعومة؟** Java 8 وما فوق متوافقة بالكامل.  
- **هل يمكن تكوين تنسيق الإخراج؟** يمكنك تصدير الصورة المدمجة كـ PNG أو JPEG أو BMP، إلخ.  

## ما هو إنشاء رمز QR Java؟

إنشاء رمز QR في Java يعني تحويل سلسلة نصية إلى مصفوفة ثنائية الأبعاد يمكن مسحها بواسطة الهواتف الذكية أو قارئات الباركود. **Aspose.BarCode for Java** يتولى الترميز والعرض، مما يتيح لك التركيز على منطق الأعمال بدلاً من معالجة الصور منخفضة المستوى.

## لماذا تستخدم Aspose.BarCode Java لتوليد الباركود في Java؟

- **دعم واسع للرموز** – من الرموز الخطية الكلاسيكية إلى المصفوفات الثنائية الأبعاد الحديثة.  
- **عرض عالي الجودة** – مخرجات مضادة للتعرجات تعمل على أي جهاز.  
- **واجهة برمجة تطبيقات بسيطة** – إنشاء، تخصيص، ودمج الباركودات ببضع نداءات للطرق فقط.  
- **بدون تبعيات خارجية** – كل شيء يعمل على JVM دون مكتبات أصلية.  

## المتطلبات المسبقة

قبل الغوص في الدرس، تأكد من توفر المتطلبات التالية:

- فهم أساسي لبرمجة Java.  
- مجموعة تطوير Java (JDK) مثبتة على نظامك.  
- مكتبة Aspose.BarCode for Java تم تحميلها وإعدادها. يمكنك تحميلها [هنا](https://releases.aspose.com/barcode/java/).  
- بيئة تطوير متكاملة (IDE) مثل Eclipse أو IntelliJ IDEA.  

## استيراد الحزم

في مشروع Java الخاص بك، استورد الحزم اللازمة للوصول إلى وظائف Aspose.BarCode. أضف عبارات الاستيراد التالية في بداية فئة Java الخاصة بك:

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

## الخطوة 1: تعيين دليل الموارد

حدد المسار إلى دليل الموارد حيث سيتم حفظ الباركودات المولدة. هذا الدليل ضروري لتنظيم وإدارة صور الباركود الخاصة بك.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## الخطوة 2: إنشاء مجموعة من الباركودات

ابدأ بـ `HashMap` لتخزين بيانات الباركود. كل إدخال في المجموعة يمثل باركود بنوع الترميز الخاص به.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## الخطوة 3: توليد صور الباركود

تجول عبر المجموعة وولّد صور الباركود باستخدام مكتبة Aspose.BarCode. احفظ الصور في `ArrayList` لمزيد من المعالجة.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## الخطوة 4: إنشاء صورة مدمجة

حدد أقصى عرض وإجمالي ارتفاع صور الباركود. أنشئ `BufferedImage` لدمج صور الباركود الفردية في صورة ناتجة واحدة.

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

## حالات الاستخدام الشائعة لتوليد عدة باركودات

- **ملصقات التعبئة** – دمج رموز المنتج، الدفعة، والشحن على ملصق واحد.  
- **تذاكر الفعاليات** – تضمين معرفات QR و Data Matrix و Code 128 لمحطات المسح المختلفة.  
- **إدارة المخزون** – عرض SKU وبيانات علامة RFID والأرقام التسلسلية معًا لتدقيق سريع.  

## استكشاف الأخطاء وإصلاحها ونصائح

- **مشكلات حجم الصورة** – عدل المتغير `offset` لزيادة أو تقليل المسافة بين الباركودات.  
- **رمز غير مدعوم** – تحقق من أن نسخة Aspose.BarCode الخاصة بك تدعم نوع الباركود المطلوب.  
- **الأداء** – أعد استخدام كائن `Graphics` واحد إذا كنت تولد العديد من الصور داخل حلقة.  

## الأسئلة المتكررة

**س1: هل يمكنني تخصيص مظهر الباركودات الفردية في الصورة المولدة؟**  
A1: نعم، توفر Aspose.BarCode خيارات تخصيص واسعة لمظهر الباركود، مما يتيح لك تعديل نمط كل باركود وفقًا لتفضيلاتك.

**س2: هل Aspose.BarCode متوافق مع رموز الباركود المختلفة؟**  
A2: بالتأكيد! يدعم Aspose.BarCode مجموعة واسعة من الرموز، بما في ذلك CODE_39 و DATA_MATRIX و QR و CODE_128 و EAN_13 و AZTEC، كما هو موضح في هذا الدرس.

**س3: كيف يمكنني دمج Aspose.BarCode في مشروع Java الخاص بي؟**  
A3: ببساطة قم بتحميل مكتبة Aspose.BarCode for Java من [هنا](https://releases.aspose.com/barcode/java/) واتبع تعليمات التثبيت الواردة في الوثائق.

**س4: هل يمكنني استخدام Aspose.BarCode للتطبيقات التجارية؟**  
A4: نعم، يمكنك الحصول على ترخيص من [هنا](https://purchase.aspose.com/buy) لاستخدام Aspose.BarCode لأغراض تجارية.

**س5: هل هناك خيارات تجريبية متاحة لـ Aspose.BarCode؟**  
A5: بالتأكيد! يمكنك استكشاف ميزات Aspose.BarCode بالحصول على ترخيص تجريبي مجاني [هنا](https://releases.aspose.com/).

**س6: كيف يمكنني توليد رمز QR عالي الدقة للطباعة؟**  
A6: اضبط قيمة DPI المطلوبة على `BarcodeGenerator` قبل استدعاء `generateBarCodeImage()`، ثم احفظ الصورة بصيغة غير مضغوطة مثل PNG.

**س7: ماذا أفعل إذا ظهرت الصورة المدمجة مقطوعة؟**  
A7: تأكد من أن حسابات `offset` وحجم اللوحة تأخذ في الاعتبار جميع ارتفاعات الباركود؛ زيادة ارتفاع اللوحة أو تقليل أحجام الباركود الفردية يحل معظم مشاكل القطع.

---

**آخر تحديث:** 2026-04-03  
**تم الاختبار مع:** Aspose.BarCode for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}