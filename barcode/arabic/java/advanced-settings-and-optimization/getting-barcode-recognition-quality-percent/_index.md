---
date: 2025-11-30
description: تعلم كيفية تقييم جودة قراءة الباركود في Java باستخدام Aspose.Barcode.
  دليل خطوة بخطوة لاسترجاع نسبة جودة التعرف.
linktitle: Getting Barcode Recognition Quality in Percent
second_title: Aspose.Barcode Java API
title: Aspose.Barcode Java – الحصول على جودة التعرف على الباركود بالنسبة المئوية
url: /ar/java/advanced-settings-and-optimization/getting-barcode-recognition-quality-percent/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Barcode Java – الحصول على جودة التعرف على الباركود بالنسبة المئوية

## مقدمة

إذا كنت بحاجة إلى **تقييم جودة قراءة الباركود** في تطبيق Java، فإن **Aspose.Barcode Java** يوفر واجهة برمجة تطبيقات بسيطة تُعيد جودة التعرف كنسبة مئوية. في هذا البرنامج التعليمي سنستعرض الخطوات الدقيقة المطلوبة لاسترجاع تلك النسبة، نشرح لماذا هذه المقياس مهم، ونوضح لك كيفية دمج الاستدعاء في قاعدة الشيفرة الحالية لديك.

## إجابات سريعة
- **ماذا يعني “جودة القراءة”؟** إنها درجة الثقة (0‑100 ٪) التي تُعطيها المكتبة لكل باركود مُفكّك.  
- **ما هو إصدار المكتبة المطلوب؟** أي إصدار حديث من Aspose.Barcode Java (العينة تستخدم أحدث سلسلة 24.x).  
- **هل أحتاج إلى ترخيص؟** ترخيص مؤقت يكفي للاختبار؛ الترخيص الكامل مطلوب للإنتاج.  
- **هل يمكنني قراءة جميع أنواع الباركود؟** نعم – علم `DecodeType.ALL_SUPPORTED_TYPES` يُفعِّل كل الصيغ التي تدعمها Aspose.Barcode.  
- **هل قيمة الجودة موثوقة لرموز QR؟** بالتأكيد – يُطبق نفس خوارزمية الثقة على الرموز أحادية وثنائية الأبعاد.

## ما هو Aspose.Barcode Java وكيفية تقييم جودة قراءة الباركود؟

**Aspose.Barcode Java** هي مكتبة مُدارة بالكامل تتيح للمطورين إنشاء، قراءة، وتحليل الباركود دون الاعتماد على مكوّنات خارجية. أحد أهم أدوات التشخيص لديها هو مقياس **جودة القراءة**، الذي يُظهر مدى ثقة المحرك في فك الرمز. هذا المقياس أساسي عندما تحتاج إلى اتخاذ قرار بقبول الفحص، طلب إعادة الالتقاط، أو تشغيل منطق معالجة الأخطاء.

## لماذا نستخدم Aspose.Barcode Java لجودة قراءة الباركود؟

- **درجات ثقة متسقة** عبر جميع الرموز المدعومة.  
- **لا توجد ملفات DLL أصلية** – مكتبة Java صافية، لذا تعمل على أي منصة متوافقة مع JVM.  
- **تحكم دقيق**: يمكنك استرجاع الجودة لكل باركود على حدة، وليس مجرد نتيجة عامة بنجاح/فشل.  
- **محرك قراءة مُحسّن للأداء** يتدرّج من سطح المكتب إلى خدمات السحابة.

## المتطلبات المسبقة

قبل البدء، تأكد من وجود ما يلي:

- **بيئة تطوير Java** – JDK 8 أو أحدث، مع IDE المفضلة لديك (IntelliJ, Eclipse, VS Code، إلخ).  
- **مكتبة Aspose.Barcode Java** – حمّل أحدث ملف JAR من الموقع الرسمي: [Aspose.Barcode for Java](https://releases.aspose.com/barcode/java/).  
- **صورة باركود تجريبية** – يستخدم البرنامج التعليمي الصورة `code39Extended.jpg` الموجودة في المجلد `BarcodeReader/advanced_features/`.

الآن بعد أن تم إعداد كل شيء، دعنا ننتقل إلى الشيفرة.

## استيراد المساحات الاسمية

الاستيرادات التالية تمنحك الوصول إلى فئات القارئ والنتيجة اللازمة لاستخراج الجودة.

```java
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
```

### الخطوة 1: تعيين مسار دليل الموارد

عرّف المجلد الذي يحتوي على الصورة التجريبية. `Utils.getDataDir` هي دالة مساعدة تُعيد المسار المطلق للمشروع الحالي.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GetBarCodeRecognitionQualityInPercent.class)
        + "BarcodeReader/advanced_features/";
```

### الخطوة 2: تهيئة كائن BarCodeReader

أنشئ مثيلًا من `BarCodeReader`، واشره إلى ملف الصورة واطلب منه تجربة **جميع أنواع الباركود المدعومة**.

```java
// Initialize the BarCodeReader object
BarCodeReader reader = new BarCodeReader(dataDir + "code39Extended.jpg",
        com.aspose.barcode.barcoderecognition.DecodeType.ALL_SUPPORTED_TYPES);
```

### الخطوة 3: قراءة الباركودات واسترجاع نسبة الجودة

قم بالتكرار عبر كل باركود مُكتشف، واطبع نصه، نوعه، ونسبة **جودة القراءة** التي تُعيدها الدالة `getReadingQuality()`.

```java
// Call the read method
for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println(result.getCodeText() + " Type: " + result.getCodeType());
    double percent = result.getReadingQuality();
    System.out.println("Percent: " + percent);
}
```

**ماذا يحدث هنا؟**  
- `readBarCodes()` تُعيد مجموعة من كائنات `BarCodeResult`، واحدة لكل باركود تم العثور عليه.  
- `getReadingQuality()` تُعيد قيمة `double` بين `0` و `100`، تمثّل مستوى الثقة.  
- يمكنك استخدام هذه القيمة لتحديد ما إذا كان الفحص مقبولًا أو إذا كان عليك طلب محاولة أخرى من المستخدم.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|-------|-----|
| **الجودة دائمًا 0** | الصورة منخفضة الدقة أو مشوشة جدًا. | استخدم مصدرًا بدقة أعلى أو طبّق معالجة مسبقة للصورة (مثل الشحذ). |
| **لم يتم اكتشاف أي باركود** | علم `DecodeType` غير صحيح. | تأكد من استخدام `DecodeType.ALL_SUPPORTED_TYPES` أو حدد النوع المحدد الذي تتوقعه. |
| **استثناء عند استدعاء `Utils.getDataDir`** | بنية المشروع تختلف عن العينة. | استبدل استدعاء المساعدة بمسار مطلق ثابت أو مسار نسبي يتوافق مع هيكلية مشروعك. |

## الأسئلة المتكررة

### س1: هل Aspose.Barcode متوافق مع جميع أنواع الباركود؟

ج1: تدعم Aspose.Barcode مجموعة واسعة من رموز الباركود، بما في ذلك 1‑D (Code‑39, Code‑128, UPC) و2‑D (QR, DataMatrix, PDF417).

### س2: هل يمكنني استخدام Aspose.Barcode لأغراض تجارية؟

ج2: نعم، يمكنك استخدام Aspose.Barcode في المشاريع الشخصية والتجارية على حد سواء. تفاصيل الترخيص متوفرة [هنا](https://purchase.aspose.com/buy).

### س3: كيف أحصل على ترخيص مؤقت لأغراض الاختبار؟

ج3: احصل على ترخيص مؤقت من بوابة Aspose [هنا](https://purchase.aspose.com/temporary-license/).

### س4: أين يمكنني العثور على دعم إضافي ومناقشات المجتمع؟

ج4: زر منتدى [Aspose.Barcode](https://forum.aspose.com/c/barcode/13) للحصول على دعم من الأقران والمساعدة الرسمية.

### س5: هل هناك أمثلة شيفرة إضافية في الوثائق؟

ج5: نعم، تتوفر عينات شيفرة شاملة في الوثائق الرسمية [هنا](https://reference.aspose.com/barcode/java/).

## الخلاصة

باستخدام **Aspose.Barcode Java**، يمكنك بسهولة استرجاع نسبة **جودة قراءة الباركود** لأي رمز مُمسوح. هذا المقياس يُمكِّنك من بناء منطق تحقق أذكى، تحسين تجربة المستخدم، والحفاظ على تكامل البيانات العالي في تطبيقات Java الخاصة بك.

---

**آخر تحديث:** 2025-11-30  
**تم الاختبار مع:** Aspose.Barcode Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}