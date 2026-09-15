---
date: 2026-04-08
description: تعلم كيفية قراءة الباركود وترتيبه بترتيب محدد باستخدام Aspose.BarCode
  للغة Java. يوضح هذا الدليل خطوة بخطوة كيفية استخدام Aspose، وقارئ الباركود في Java،
  وفك تشفير باركود Code128.
keywords:
- how to read barcodes
- java barcode reader
- aspose barcode java
linktitle: قراءة وفرز الباركود بترتيب محدد
second_title: Aspose.BarCode Java API
title: كيفية قراءة الباركود بترتيب محدد باستخدام جافا
url: /ar/java/document-barcode-recognition/reading-sorting-barcodes-specific-order/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية قراءة الباركود بترتيب محدد باستخدام Java

## مقدمة

إذا كنت بحاجة إلى **كيفية قراءة الباركود** ثم ترتيبها في تسلسل معين، فإن Aspose.BarCode for Java يوفر لك طريقة نظيفة وعالية الأداء للقيام بذلك. في العديد من تطبيقات Java—أنظمة المخزون، حلول الشحن، أو نقاط البيع—يعد قراءة عدة باركودات وفرزها حسب قيمتها النصية مطلبًا شائعًا. يشرح هذا البرنامج التعليمي العملية بالكامل، من إعداد البيئة إلى عرض النتائج المرتبة، حتى تتمكن من دمج معالجة الباركود بسرعة وثقة.

## إجابات سريعة
- **ما المكتبة التي تتعامل مع قراءة الباركود؟** Aspose.BarCode for Java  
- **ما نوع الباركود المستخدم في المثال؟** CODE_128  
- **هل أحتاج إلى ترخيص للتطوير؟** ترخيص مؤقت يعمل للاختبار؛ الترخيص الكامل مطلوب للإنتاج.  
- **هل يمكنني الفرز بمعايير أخرى؟** نعم—قم بتعديل الـ comparator للفرز حسب الموقع أو الثقة، إلخ.  
- **ما نسخة Java المطلوبة؟** Java 8 أو أحدث (أي JDK يدعم مكتبة Aspose).

## ما هو “كيفية قراءة الباركود” في Java؟

قراءة الباركود تعني فك تشفير النمط البصري إلى سلسلة البيانات الأصلية. توفر Aspose.BarCode فئة `BarCodeReader` التي تج abstracts المعالجة منخفضة المستوى للصور، مما يتيح لك التركيز على منطق الأعمال مثل الفرز أو التحقق.

## لماذا تستخدم Aspose.BarCode for Java؟

- **فك تشفير قوي** – يدعم أكثر من 50 نوعًا من الرموز، بما في ذلك Code 128، QR، DataMatrix، والمزيد.  
- **دقة عالية** – خوارزميات محسنة تقلل الأخطاء حتى في الصور منخفضة الدقة.  
- **واجهة برمجة تطبيقات بسيطة** – بضع أسطر من الشيفرة تنقلك من الصورة إلى النص.  
- **متعدد المنصات** – يعمل على أي بيئة تشغيل Java، من سطح المكتب إلى الخوادم.

## المتطلبات المسبقة

قبل الغوص في الشيفرة، تأكد من توفر المتطلبات التالية:

- مجموعة تطوير Java (JDK): يتطلب Aspose.BarCode for Java وجود JDK فعال. يمكنك تنزيل أحدث نسخة [هنا](https://www.oracle.com/java/technologies/javase-downloads.html).

- مكتبة Aspose.BarCode: تأكد من حصولك على مكتبة Aspose.BarCode. يمكنك الحصول عليها من [رابط التنزيل](https://releases.aspose.com/barcode/java/).

## استيراد الحزم

ابدأ باستيراد الحزم الضرورية إلى مشروع Java الخاص بك. هذه الحزم توفر الفئات والطرق الأساسية للعمل مع الباركود.

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;

import java.awt.Point;
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;
```

الآن، دعنا نفصل الشيفرة في دليل خطوة بخطوة:

## الخطوة 1: إعداد دليل الموارد

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

استبدل `"Your Document Directory"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

## الخطوة 2: تحديد مسار صورة الباركود وتهيئة القارئ

```java
String path = dataDir + "barcode.png";
List<FoundBarCodes> found = new ArrayList<FoundBarCodes>();

// Initialize BarCodeReader with the specified path and decode type
BarCodeReader reader = new BarCodeReader(path, DecodeType.CODE_128);
```

## الخطوة 3: قراءة الباركود وتخزين النتائج

```java
// Iterate through barcodes and store results
for (BarCodeResult result : reader.readBarCodes()) {
    found.add(new FoundBarCodes(result.getCodeText(), result.getRegion()));
}
```

## الخطوة 4: تعريف Comparator للفرز

```java
// Define a comparator for sorting barcodes based on code text
Comparator<FoundBarCodes> foundComparator = new Comparator<FoundBarCodes>() {
    @Override
    public int compare(FoundBarCodes e1, FoundBarCodes e2) {
        return e1.getCodeText().compareTo(e2.getCodeText());
    }
};
```

## الخطوة 5: فرز الباركود

```java
// Sort the list of barcodes using the defined comparator
found.sort(foundComparator);
```

## الخطوة 6: عرض الباركود المرتب

```java
// Display sorted barcodes with their coordinates
int i = 1;
for (FoundBarCodes barcode : found) {
    Point[] point = barcode.BarCodeRegion.getPoints();
    System.out.println("Codetext ( " + i + " ): " + barcode.CodeText);
    System.out.println("Top left coordinates: X = " + point[0].getX() + ", Y = " + point[0].getY());
    System.out.println("Bottom left coordinates: X = " + point[1].getX() + ", Y = " + point[1].getY());
    System.out.println("Bottom right coordinates: X = " + point[2].getX() + ", Y = " + point[2].getY());
    System.out.println("Top right coordinates: X = " + point[3].getX() + ", Y = " + point[3].getY());
    System.out.println();
    i++;
}
```

## الأخطاء الشائعة والنصائح

- **مسار الصورة غير صحيح** – تحقق من أن `dataDir` ينتهي بفاصل ملفات (`/` أو `\\`) حتى يتم حل المسار الكامل بشكل صحيح.  
- **نوع الباركود غير مدعوم** – إذا كنت بحاجة إلى فك تشفير رموز مختلفة، غيّر `DecodeType.CODE_128` إلى القيمة المناسبة من الـ enum (مثال: `DecodeType.QR`).  
- **الفرز بالقيمة الرقمية** – الـ comparator الافتراضي يفرز أبجديًا. للفرز الرقمي، حوّل `CodeText` إلى عدد صحيح داخل الـ comparator.  
- **تنظيف الموارد** – `BarCodeReader` يطبق `Closeable`. في الشيفرة الإنتاجية، احرص على وضعه داخل كتلة try‑with‑resources لضمان تحرير التدفق الأساسي.

## الأسئلة المتكررة

### س: أين يمكنني العثور على وثائق Aspose.BarCode for Java؟
الوثائق متاحة [هنا](https://reference.aspose.com/barcode/java/).

### س: كيف يمكنني تنزيل Aspose.BarCode for Java؟
يمكنك تنزيله من [رابط التنزيل](https://releases.aspose.com/barcode/java/).

### س: هل هناك نسخة تجريبية مجانية متاحة؟
نعم، يمكنك استكشاف نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).

### س: كيف أحصل على معلومات الترخيص المؤقت؟
يمكن الحصول على تراخيص مؤقتة [هنا](https://purchase.aspose.com/temporary-license/).

### س: أين يمكنني طلب الدعم أو طرح الأسئلة؟
زر منتدى الدعم [هنا](https://forum.aspose.com/c/barcode/13).

**آخر تحديث:** 2026-04-08  
**تم الاختبار مع:** Aspose.BarCode 24.10 for Java  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}