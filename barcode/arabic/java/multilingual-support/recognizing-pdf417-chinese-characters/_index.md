---
date: 2025-12-25
description: تعلم كيفية استخراج النص من صور الباركود، وبشكل خاص PDF417 مع الأحرف الصينية،
  باستخدام Aspose.BarCode للغة Java. اتبع دليلنا خطوة بخطوة حول كيفية قراءة بيانات
  الباركود بكفاءة.
linktitle: 'Extract Text from Barcode: PDF417 Chinese Characters'
second_title: Aspose.BarCode Java API
title: 'استخراج النص من الباركود: PDF417 الأحرف الصينية في جافا'
url: /ar/java/multilingual-support/recognizing-pdf417-chinese-characters/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# استخراج النص من الباركود: PDF417 أحرف صينية في جافا

## مقدمة

إن دمج التعرف على الباركود في تطبيقات جافا مهارة قيمة، خاصة عندما تحتاج إلى **استخراج النص من الباركود** في صور تحتوي على بيانات متعددة اللغات. في هذا الدرس، سنرشدك لاستخدام Aspose.BarCode for Java للتعرف على باركودات PDF417 التي تحتوي على أحرف صينية. في النهاية، ستعرف بالضبط كيفية قراءة بيانات الباركود وفك تشفيرها إلى نص قابل للقراءة.

## إجابات سريعة
- **ما المكتبة التي تدعم PDF417 مع الأحرف الصينية؟** Aspose.BarCode for Java.  
- **ما مجموعة الأحرف المطلوبة لفك تشفير الصينية؟** MS936 (GBK).  
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** نعم، يلزم ترخيص تجاري.  
- **هل يمكن تشغيله على أي نسخة من جافا؟** يعمل مع Java 8 والإصدارات الأحدث.  
- **هل تتوفر نسخة تجريبية مجانية؟** بالتأكيد – قم بتحميلها من موقع Aspose.

## ما هو “استخراج النص من الباركود”؟

استخراج النص من الباركود يعني تحويل البيانات المشفرة مرة أخرى إلى شكلها الأصلي القابل للقراءة البشرية. بالنسبة لباركودات PDF417 التي تخزن أحرف صينية، يتضمن ذلك أيضًا اختيار ترميز الأحرف الصحيح بحيث تتطابق البايتات مع الحروف المناسبة.

## لماذا نستخدم Aspose.BarCode for Java؟

توفر Aspose.BarCode دعمًا قويًا لمجموعة واسعة من رموز الباركود، بما في ذلك PDF417، وتتعامل مع مجموعات الأحرف المعقدة مباشرةً. فهي تُجرد معالجة الصورة على مستوى منخفض، مما يتيح لك التركيز على منطق الأعمال بدلاً من تعقيدات فك الترميز.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من أن لديك:

1. **Java Development Kit (JDK)** – يُنصح بأحدث نسخة.  
2. **Aspose.BarCode for Java** – قم بتحميله من [here](https://releases.aspose.com/barcode/java/).  
3. **صورة باركود PDF417** تحتوي على أحرف صينية (مثال: `barcode.png`).

## استيراد الحزم

في مشروع جافا الخاص بك، استورد الفئات اللازمة للعمل مع Aspose.BarCode:

```java
import java.nio.ByteBuffer;
import java.nio.charset.Charset;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## الخطوة 1: تعيين دليل المستند

حدد المجلد الذي توجد فيه صورة الباركود الخاصة بك:

```java
String dataDir = "Your Document Directory";
```

استبدل `"Your Document Directory"` بالمس بالبحث عن رموز PDF417:

```java
BarCodeReader reader = new BarCodeReader(dataDir + "barcode.png", DecodeType.PDF_417);
```

## الخطوة 3: قراءة الباركود

قم بالتكرار عبر نتائج الكشف، استخرج مصفوفة البايتات الخام، وفك تشفيرها باستخدام مجموعة الأحرف GBK (MS936):

```java
for (BarCodeResult result : reader.readBarCodes()) {
    byte[] bytes = result.getCodeBytes();
    ByteBuffer bytebuf = ByteBuffer.wrap(bytes);
    System.out.println(Charset.forName("MS936").decode(bytebuf).toString());
}
```

هذه الحلقة **استخراج النص من الباركود** وتطبع الأحرف الصينية المفككة إلى وحدة التحكم.

## كيف تقرأ الباركود باستخدام PDF417؟

الكود أعلاه يوضح **كيفية قراءة الباركود** خطوة بخطوة:

1. **تهيئة** القارئ باستخدام `DecodeType` الصحيح.  
2. **التكرار** على كل `BarCodeResult` تم إرجاعه.  
3. **تحويل** البايتات الخام باستخدام مجموعة الأحرف المناسبة (`MS936` للصينية).  

إذا كان الباركود الخاص بك يحتوي على لغات أخرى، ما عليك سوى تغيير مجموعة الأحرف إلى ما يتطابق مع بياناتك.

## المشكلات الشائعة والحلول

| المشكلة | الحل |
|-------|----------|
| حروف مشوشة بعد فك الترميز | تحقق من أنك تستخدم مجموعة الأحرف الصحيحة (`MS936` لـ GBK). |
| لم يتم اكتشاف أي باركود | تأكد من جودة الصورة عالية وأن الباركود غير مائل؛ يمكنك معالجة الصورة مسبقًا إذا لزم الأمر. |
| تم إرجاع نتائج متعددة | يمكن لـ PDF417 تخزين مقاطع متعددة؛ قم بالتكرار عبر جميع النتائج كما هو موضح. |

## الأسئلة المتكررة (FAQs)

### هل يمكنني استخدام Aspose.BarCode for Java في المشاريع التجارية؟

نعم، يمكنك استخدام Aspose.BarCode for Java في المشاريع التجارية. للحصول على تفاصيل الترخيص، زر [here](https://purchase.aspose.com/buy).

### هل تتوفر نسخة تجريبية مجانية؟

نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.BarCode for Java [here](https://releases.aspose.com/).

### كيف يمكنني الحصول على الدعم لـ Aspose.BarCode؟

قم بزيارة منتدى Aspose.BarCode [here](https://forum.aspose.com/c/barcode/13) لأي دعم أو استفسارات.

### هل يمكنني الحصول على ترخيص مؤقت لأغراض الاختبار؟

نعم، يمكنك الحصول على ترخيص مؤقت [here](https://purchase.aspose.com/temporary-license/).

### أين يمكنني العثور على الوثائق؟

الوثائق متاحة [here](https://reference.aspose.com/barcode/java/).

**أسئلة وإجابات إضافية**

**س: ماذا لو كانت صورة الباركود بصيغة JPEG؟**  
ج: يعمل `BarCodeReader` مع صيغ JPEG، PNG، BMP، وغيرها من صيغ الصور الشائعة—فقط غيّر امتداد الملف وفقًا لذلك.

**س: هل يمكنني فك تشفير الباركود من تدفق بدلاً من ملف؟**  
ج: نعم، يمكنك تمرير `InputStream` إلى مُنشئ `BarCodeReader` لفك الترميز أثناء التشغيل.

**س: هل يدعم Aspose.BarCode مجموعات أحرف أخرى؟**  
ج: بالتأكيد. استخدم `Charset.forName("<your‑charset>")` لفك تشفير البايتات لـ UTF‑8، ISO‑8859‑1، إلخ.

## الخلاصة

لقد تعلمت الآن كيفية **استخراج النص من الباركود** في الصور، وبشكل خاص باركودات PDF417 التي تحتوي على أحرف صينية، باستخدام Aspose.BarCode for Java. تفتح هذه القدرة أبوابًا لأنظمة المخزون متعددة اللغات، وأتمتة المستندات، وأكثر. لا تتردد في تجربة رموز أخرى ومجموعات أحرف لتوسيع نطاق تطبيقك.

---

**آخر تحديث:** 2025-12-25  
**تم الاختبار مع:** Aspose.BarCode for Java 24.12  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}