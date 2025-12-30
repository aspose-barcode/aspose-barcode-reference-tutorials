---
date: 2025-12-30
description: تعلم كيفية إنشاء باركود جافا باستخدام Aspose.BarCode. يوضح لك هذا الدليل
  خطوة بخطوة كيفية تعيين نص باركود مخصص، وضبط العرض، وحفظ الصورة.
linktitle: Setting Code Text
second_title: Aspose.BarCode Java API
title: 'إنشاء باركود Java: تعيين نص الرمز باستخدام Aspose.BarCode'
url: /ar/java/text-and-styling/setting-code-text/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء باركود Java: تعيين نص الرمز باستخدام Aspose.BarCode

## المقدمة

في هذا البرنامج التعليمي، ستتعلم كيفية **إنشاء باركود Java** باستخدام مكتبة Aspose.BarCode Java. سواءً كنت تبني نظام جرد، أو حل تتبع مستندات، أو أي تطبيق يحتاج إلى باركود، فإن هذا الدليل يرافقك خطوة بخطوة—من إنشاء باركود **Code128** إلى تخصيص نص الرمز وضبط عرض الخط. في النهاية ستحصل على صورة جاهزة يمكنك تضمينها في أي مكان تحتاجه.

## إجابات سريعة
- **ما المكتبة التي يجب استخدامها؟** Aspose.BarCode for Java.  
- **ما نوع الباركود المعروض؟** CODE_128.  
- **كيف يمكنني تعيين نص باركود مخصص؟** استخدم مُنشئ `BarcodeGenerator` أو طريقة `setCodeText`.  
- **هل يمكنني تغيير عرض الخط؟** نعم، عبر `XDimension` بالمليمترات.  
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم، يلزم الحصول على ترخيص تجاري.

## المتطلبات المسبقة

قبل الغوص في البرنامج التعليمي، تأكد من توفر ما يلي:

- فهم أساسي لبرمجة Java.  
- بيئة تطوير Java تعمل مثبتة.  
- مكتبة Aspose.BarCode for Java. يمكنك تنزيلها **[هنا](https://releases.aspose.com/barcode/java/)**.  
- محرر شفرة، مثل IntelliJ IDEA أو Eclipse.  

## استيراد الحزم

ابدأ باستيراد الحزم الضرورية إلى مشروع Java الخاص بك. هذه الحزم أساسية للعمل مع Aspose.BarCode.

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```

الآن، دعنا نستكشف عملية تعيين نص الرمز باستخدام Aspose.BarCode في Java. اتبع الخطوات التالية:

## برنامج تعليمي لمولد الباركود: إنشاء باركود Code128

### الخطوة 1: إنشاء نسخة من `BarcodeGenerator`

```java
// The path to the documents directory.
String path = "Your Directory Path";
// The path to the resource directory.
String dataDir = "Your Document Directory";
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
```

هنا، نقوم بإنشاء نسخة من `BarcodeGenerator`، مع تحديد رمزية الباركود (**CODE_128**) و**نص الباركود المخصص** `"12345678"`.

### الخطوة 2: تعديل عرض الباركود للنص المخصص

```java
generator.getParameters().getBarcode().getXDimension().setMillimeters(0.5f);
```

قم بتعديل عرض الخطوط وفقًا لتفضيلك. في هذا المثال، **نعدل عرض الباركود** إلى `0.5` مم، وهو مناسب لمعظم أحجام الملصقات.

### الخطوة 3: حفظ صورة الباركود

```java
generator.save(dataDir + "setCodeText.jpg");
```

احفظ صورة الباركود التي تم إنشاؤها في الدليل المحدد. في هذه الحالة، يتم حفظ الملف باسم **`setCodeText.jpg`** داخل دليل المستندات الخاص بك.

## لماذا تستخدم Aspose.BarCode for Java؟

- **API شامل** – يدعم أكثر من 60 نوعًا من رموز الباركود، بما في ذلك Code128، QR، DataMatrix، وغيرها.  
- **تصيير عالي الجودة** – يولد صورًا واضحة بصيغ PNG، JPEG، SVG، وPDF.  
- **تخصيص سهل** – غيّر النص، الحجم، الألوان، وحتى أضف تسميات قابلة للقراءة البشرية ببضع أسطر من الشيفرة.  
- **متعدد المنصات** – يعمل على Windows، Linux، وmacOS مع أي بيئة تشغيل Java 8+.

## المشكلات الشائعة والحلول

| المشكلة | الحل |
|-------|----------|
| **الباركود غير واضح** | قم بزيادة دقة الصورة أو صدّر إلى صيغ المتجه (SVG, PDF). |
| **النص مقطوع** | تأكد من أن `XDimension` (عرض الخط) و `BarHeight` كافيان للرمز المختار. |
| **الترخيص غير مفعّل** | ضع ملف الترخيص الخاص بك (`Aspose.BarCode.lic`) في جذر المشروع وحمّله باستخدام `License license = new License(); license.setLicense("Aspose.BarCode.lic");`. |

## الأسئلة المتكررة (FAQs)

### هل يمكنني استخدام Aspose.BarCode for Java في المشاريع التجارية؟
نعم، Aspose.BarCode for Java هو منتج تجاري. يمكنك العثور على تفاصيل الترخيص **[هنا](https://purchase.aspose.com/buy)**.

### هل يتوفر نسخة تجريبية مجانية؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية **[هنا](https://releases.aspose.com/)**.

### أين يمكنني العثور على وثائق Aspose.BarCode for Java؟
الوثائق متاحة **[هنا](https://reference.aspose.com/barcode/java/)**.

### كيف أحصل على الدعم لـ Aspose.BarCode for Java؟
قم بزيارة **[منتدى Aspose.BarCode](https://forum.aspose.com/c/barcode/13)** للحصول على الدعم.

### هل يمكنني استخدام ترخيص مؤقت لأغراض الاختبار؟
نعم، يمكنك الحصول على ترخيص مؤقت **[هنا](https://purchase.aspose.com/temporary-license/)**.

## أسئلة متكررة إضافية

**س:** *ما الفرق بين `CODE_128` وأنواع Code128 الأخرى؟*  
**ج:** `CODE_128` هو الرمز القياسي الذي يختار تلقائيًا أكثر طرق الترميز كفاءة (A أو B أو C) بناءً على النص المدخل.

**س:** *هل يمكنني تغيير صيغة الإخراج إلى PNG بدلاً من JPEG؟*  
**ج:** بالتأكيد. استخدم `generator.save(dataDir + "setCodeText.png", com.aspose.barcode.BarcodeImageFormat.PNG);`.

**س:** *هل يمكن إضافة تسمية قابلة للقراءة البشرية أسفل الباركود؟*  
**ج:** نعم. اضبط `generator.getParameters().getBarcode().getCaption().setTopMargin(5);` وحدد نص التسمية.

**س:** *هل يدعم Aspose.BarCode الأحرف Unicode؟*  
**ج:** نعم. قدم النص بصيغة UTF‑8 وتأكد من أن الرمز المختار يدعم مجموعة الأحرف.

**س:** *كيف يمكنني إنشاء عدة باركودات داخل حلقة؟*  
**ج:** أنشئ نسخة جديدة من `BarcodeGenerator` داخل الحلقة، عيّن النص لكل تكرار، واستدعِ `save` باسم ملف فريد.

**آخر تحديث:** 2025-12-30  
**تم الاختبار مع:** Aspose.BarCode 24.12 for Java  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}