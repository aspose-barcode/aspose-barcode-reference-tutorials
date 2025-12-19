---
date: 2025-12-19
description: تعلم كيفية قراءة الباركود باستخدام Aspose.BarCode للغة Java، وترتيبه
  بترتيب محدد، وشاهد مثالًا كاملاً لاكتشاف الباركود بلغة Java.
linktitle: Reading and Sorting Barcodes in Specific Order
second_title: Aspose.BarCode Java API
title: كيفية قراءة الباركود وترتيبه بترتيب محدد في جافا
url: /ar/java/document-barcode-recognition/reading-sorting-barcodes-specific-order/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية قراءة الباركود وترتيبه بترتيب محدد في جافا

## المقدمة

في تطبيقات جافا الحديثة، **كيفية قراءة الباركود** بكفاءة هي سؤال شائع. سواء كنت تعالج قوائم المخزون، أو ملصقات الشحن، أو تذاكر الفعاليات، فإن حل الباركود الموثوق يمكنه توفير ساعات من العمل اليدوي. في هذا الدرس سنوضح لك كيفية قراءة الباركود وترتيبه بترتيب محدد باستخدام **Aspose.BarCode for Java**. ستحصل على مثال كامل جاهز للتنفيذ يوضح اكتشاف الباركود، استخراج نص الكود، ومنطق الفرز المخصص.

## إجابات سريعة
- **ما المكتبة التي يجب أن أستخدمها؟** Aspose.BarCode for Java
- **هل يمكنني فرز الباركود بعد قراءته؟** نعم – فقط احفظ النتائج وطبق Comparator
- **هل أحتاج إلى ترخيص للتطوير؟** نسخة تجريبية مجانية تعمل للاختبار؛ الترخيص التجاري مطلوب للإنتاج
- **ما نسخة جافا المدعومة؟** Java 8 وما بعدها
- **هل هذا مثال على اكتشاف الباركود في جافا؟** بالتأكيد – الكود يقرأ باركود CODE_128 ويقوم بفرزه

## ما هو “كيفية قراءة الباركود” في جافا؟
قراءة الباركود تعني فك تشفير النمط البصري لصورة الباركود إلى قيمته النصية الأساسية. توفر Aspose.BarCode محرك **قراءة الباركود aspose** عالي الأداء يدعم عشرات الأنماط، بما في ذلك CODE_128، QR، DataMatrix، وأكثر.

## لماذا تستخدم Aspose.BarCode لقراءة الباركود aspose؟
- **دقة عالية** – يعمل حتى مع الصور منخفضة الدقة
- **API بسيط** – بضع أسطر من الكود تنقلك من الصورة إلى النص
- **متعدد المنصات** – يعمل على أي بيئة متوافقة مع JVM
- **دعم فرز مدمج** – يمكنك بسهولة دمج القراءة مع مجموعات جافا

## المتطلبات المسبقة

قبل الغوص في الكود، تأكد من توفر المتطلبات التالية:

- Java Development Kit (JDK): يتطلب Aspose.BarCode for Java وجود JDK فعال. يمكنك تنزيل أحدث نسخة [هنا](https://www.oracle.com/java/technologies/javase-downloads.html).
- مكتبة Aspose.BarCode: تأكد من حصولك على مكتبة Aspose.BarCode. يمكنك الحصول عليها من [رابط التحميل](https://releases.aspose.com/barcode/java/).

## استيراد الحزم

ابدأ باستيراد الحزم الضرورية إلى مشروع جافا الخاص بك. هذه الحزم توفر الفئات والطرق الأساسية للعمل مع الباركود.

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

الآن، دعنا نقسم الكود إلى دليل خطوة بخطوة:

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

## المشكلات الشائعة والحلول

| المشكلة | سبب حدوثها | الحل |
|-------|----------------|-----|
| **لم يتم اكتشاف أي باركود** | `DecodeType` غير صحيح أو صورة منخفضة الجودة | تحقق من أن الصورة تحتوي على باركود CODE_128 واستخدم `DecodeType` المناسب. يمكنك أيضًا تجربة `DecodeType.ALL` للاكتشاف التلقائي. |
| **ترتيب فرز غير صحيح** | Comparator يقارن السلاسل حرفيًا | إذا كنت بحاجة إلى فرز رقمي، حوّل `CodeText` إلى `int` قبل المقارنة. |
| **خطأ Null pointer على `BarCodeRegion`** | مسار الصورة غير صحيح أو الملف غير موجود | تأكد من أن `path` يشير إلى ملف PNG صالح وأن الملف قابل للقراءة من قبل JVM. |

## الأسئلة المتكررة

**س: أين يمكنني العثور على وثائق Aspose.BarCode for Java؟**  
ج: الوثائق متاحة [هنا](https://reference.aspose.com/barcode/java/).

**س: كيف يمكنني تحميل Aspose.BarCode for Java؟**  
ج: يمكنك تحميله من [رابط التحميل](https://releases.aspose.com/barcode/java/).

**س: هل هناك نسخة تجريبية مجانية متاحة؟**  
ج: نعم، يمكنك تجربة النسخة التجريبية المجانية [هنا](https://releases.aspose.com/).

**س: كيف أحصل على معلومات الترخيص المؤقت؟**  
ج: يمكن الحصول على تراخيص مؤقتة [هنا](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني طلب الدعم أو طرح الأسئلة؟**  
ج: زر منتدى الدعم [هنا](https://forum.aspose.com/c/barcode/13).

## أسئلة إضافية (محسّنة بالذكاء الاصطناعي)

**س: هل يمكنني استخدام هذا الكود مع أنواع باركود أخرى؟**  
ج: بالتأكيد. غيّر `DecodeType.CODE_128` إلى أي رموز مدعومة، مثل `DecodeType.QR` أو `DecodeType.DATA_MATRIX`.

**س: هل يدعم Aspose.BarCode معالجة دفعات من الصور المتعددة؟**  
ج: نعم. قم بالتكرار عبر مجموعة من مسارات الملفات وأعد استخدام نفس منطق `BarCodeReader` لكل صورة.

**س: كيف يمكنني تحسين الأداء لمجموعات الصور الكبيرة؟**  
ج: أعد استخدام كائن `BarCodeReader` حيثما أمكن وعالج الصور بشكل متوازي باستخدام `ExecutorService` في جافا.

## الخلاصة

في هذا الدرس أظهرنا **كيفية قراءة الباركود** باستخدام Aspose.BarCode for Java، وتخزين كل نتيجة، وفرز القائمة بترتيب مخصص. باتباع دليل الخطوة بخطوة، يمكنك دمج اكتشاف الباركود القوي والفرز في أي تطبيق جافا—سواء كان لإدارة المخزون، أو اللوجستيات، أو تذاكر الفعاليات.

---

**آخر تحديث:** 2025-12-19  
**تم الاختبار مع:** Aspose.BarCode for Java 24.11 (latest at time of writing)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}