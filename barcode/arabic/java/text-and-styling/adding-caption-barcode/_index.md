---
date: 2025-12-27
description: تعلم كيفية إضافة تسمية توضيحية إلى صور الباركود في جافا باستخدام Aspose.BarCode.
  يوضح مثال مولد الباركود في جافا كيفية إنشاء صورة باركود بجافا بسهولة.
linktitle: Adding Caption to Barcode
second_title: Aspose.BarCode Java API
title: كيفية إضافة تسمية توضيحية إلى الباركود في جافا باستخدام Aspose.BarCode
url: /ar/java/text-and-styling/adding-caption-barcode/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة تسمية توضيحية إلى الباركود في جافا باستخدام Aspose.BarCode

## المقدمة

إذا كنت بحاجة إلى **كيفية إضافة تسمية توضيحية** إلى باركود لتحسين القابلية للقراءة والعلامة التجارية، فأنت في المكان الصحيح. في هذا الدرس سنستعرض الخطوات الدقيقة لإضافة تسميات توضيحية فوق وتحت صورة الباركود باستخدام Aspose.BarCode لجافا. في النهاية، ستحصل على باركود مُصمم بالكامل لا يقتصر على ترميز البيانات فقط بل يعرض نصًا مفيدًا — مثالي لملصقات المنتجات، أنظمة المخزون، أو أي سيناريو يستفيد فيه المستخدمون من سياق إضافي.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.BarCode for Java.  
- **هل يمكنني تغيير الخط واللون؟** نعم—كلا من عائلة خط التسمية ولون النص قابلان للتخصيص.  
- **ما أنواع الباركود التي تعمل؟** جميع الرموز المدعومة من Aspose.BarCode (مثل CODE_128، QR، DataMatrix).  
- **هل أحتاج إلى ترخيص للاختبار؟** يتوفر إصدار تجريبي مجاني؛ الترخيص التجاري مطلوب للإنتاج.  
- **كم يستغرق تنفيذ ذلك؟** عادةً أقل من 10 دقائق بمجرد إضافة المكتبة.

## ما هي التسمية التوضيحية في الباركود؟
التسمية التوضيحية هي نص عادي يظهر إما فوق أو تحت الرسم البياني للباركود. يمكنها نقل أسماء المنتجات، الأسعار، أو أي معلومات أخرى تكمل البيانات المشفرة.

## لماذا نضيف تسميات توضيحية باستخدام Aspose.BarCode؟
- **تحسين تجربة المستخدم:** يمكن للمستخدمين قراءة معنى الباركود فورًا دون الحاجة إلى مسحه.  
- **اتساق العلامة التجارية:** يمكنك تطبيق خطوطك، ألوانك، ومحاذاة لتتناسب مع دليل نمط الشركة.  
- **تحكم كامل:** تسمح لك API الخاصة بـ Aspose.BarCode بتبديل الرؤية، ضبط المحاذاة، وتنسيق كل تسمية توضيحية بشكل مستقل.

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من أن لديك:

- تثبيت Java Development Kit (JDK).  
- تحميل مكتبة Aspose.BarCode لجافا وإضافتها إلى مشروعك. يمكنك العثور على رابط التحميل [هنا](https://releases.aspose.com/barcode/java/).  
- بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse.

## استيراد الحزم

في ملف Java الخاص بك، استورد الفئات المطلوبة من Aspose.BarCode وفئة AWT `Color`:

```java
import com.aspose.barcode.*;
import java.awt.*;
```

## الخطوة 1: إعداد المستند ودلائل الموارد

حدد المكان الذي تريد تخزين صورة الباركود المُولدة فيه. عدل المسارات لتتناسب مع بيئتك.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

## الخطوة 2: إنشاء كائن Barcode Generator

أنشئ `BarcodeGenerator` باستخدام الرموز المطلوبة (مثلاً CODE_128) والنص الذي تريد ترميزه.

```java
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

## الخطوة 3: تكوين التسمية التوضيحية فوق الباركود

حدد التسمية التي تظهر فوق الباركود. يمكنك التحكم في المحاذاة، النص، الرؤية، عائلة الخط، الحجم، واللون.

```java
bb.getParameters().getCaptionAbove().setAlignment(TextAlignment.LEFT);
bb.getParameters().getCaptionAbove().setText("Aspose.Demo");
bb.getParameters().getCaptionAbove().setVisible(true);
bb.getParameters().getCaptionAbove().getFont().setFamilyName("Pristina");
bb.getParameters().getCaptionAbove().getFont().getSize().setPoint(14);
bb.getParameters().getCaptionAbove().setTextColor(Color.RED);
```

## الخطوة 4: تكوين التسمية التوضيحية تحت الباركود

وبالمثل، عرّف التسمية تحت الباركود. لا تتردد في استخدام محاذاة أو تنسيق مختلف إذا لزم الأمر.

```java
bb.getParameters().getCaptionBelow().setAlignment(TextAlignment.RIGHT);
bb.getParameters().getCaptionBelow().setText("Aspose.Demo");
bb.getParameters().getCaptionBelow().setVisible(true);
bb.getParameters().getCaptionBelow().getFont().setFamilyName("Pristina");
bb.getParameters().getCaptionBelow().getFont().getSize().setPoint(14);
bb.getParameters().getCaptionBelow().setTextColor(Color.RED);
```

## الخطوة 5: حفظ صورة الباركود

أخيرًا، احفظ الباركود (مع التسميات) إلى ملف صورة. يتم استنتاج الصيغة من امتداد الملف.

```java
bb.save(dataDir + "barcodeCaption.jpg");
```

يمكنك تكرار الخطوات أعلاه لتجربة خطوط، ألوان، أو محاذاة مختلفة، أو لإنشاء عدة صور باركود داخل حلقة.

## المشكلات الشائعة والنصائح

- **التسمية غير مرئية؟** تأكد من استدعاء `setVisible(true)` للتسمية التي تريد عرضها.  
- **ألوان غير صحيحة؟** استخدم ثوابت `java.awt.Color` أو أنشئ ألوانًا مخصصة باستخدام `new Color(r, g, b)`.  
- **مشكلات في المسار؟** تحقق من أن `dataDir` يشير إلى مجلد قابل للكتابة موجود؛ وإلا سيتسبب `bb.save()` في رمي `IOException`.  
- **نصيحة أداء:** أعد استخدام كائن `BarcodeGenerator` واحد عند توليد العديد من الباركودات؛ غير فقط `EncodeTypes` أو `codetext` حسب الحاجة.

## الأسئلة المتكررة (FAQs)

### هل يمكنني تخصيص نمط خط تسميات الباركود؟
نعم، يمكنك تخصيص عائلة الخط، الحجم، واللون لكل من التسمية فوق وتحت الباركود.

### هل Aspose.BarCode متوافق مع رموز باركود مختلفة؟
بالطبع! يدعم Aspose.BarCode مجموعة واسعة من الرموز، مما يضمن المرونة في إنشاء الباركود.

### كيف يمكنني دمج Aspose.BarCode في مشروع جافا الخاص بي؟
يمكنك اتباع دليل التكامل التفصيلي المتاح [هنا](https://reference.aspose.com/barcode/java/) للحصول على تعليمات خطوة بخطوة.

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.BarCode لجافا؟
نعم، يمكنك الوصول إلى النسخة التجريبية المجانية [هنا](https://releases.aspose.com/) لاستكشاف جميع الميزات قبل الشراء.

### أين يمكنني الحصول على مساعدة إذا واجهت مشاكل؟
منتدى مجتمع Aspose.BarCode هو مكان ممتاز للدعم والنقاش. زر المنتدى [هنا](https://forum.aspose.com/c/barcode/13).

---

**آخر تحديث:** 2025-12-27  
**تم الاختبار مع:** Aspose.BarCode for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}