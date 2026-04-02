---
date: 2025-12-27
description: تعلم كيفية إنشاء رمز الباركود من نوع Data Matrix وكيفية ضبط موقع نص الباركود
  في Java باستخدام Aspose.BarCode. اتبع دليلنا خطوة بخطوة للحصول على تخصيص كامل.
linktitle: Setting Code Text Location
second_title: Aspose.BarCode Java API
title: إنشاء باركود مصفوفة البيانات وتحديد موقع نص الرمز في جافا
url: /ar/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء data matrix barcode وتحديد موقع نص الرمز في Java

## مقدمة

إنشاء رموز الباركود هو مطلب روتيني للمخزون والشحن والعديد من التطبيقات الأخرى القائمة على Java. باستخدام **Aspose.BarCode for Java** يمكنك **create data matrix barcode** بسرعة والتحكم في كل جانب بصري، بما في ذلك مكان ظهور النص القابل للقراءة من قبل الإنسان. في هذا الدرس سنستعرض الخطوات الدقيقة لـ **create data matrix barcode** ونوضح **how to set barcode text** فوق الرمز لتتوافق مع مواصفات التصميم الخاصة بك.

## إجابات سريعة
- **ما المكتبة المستخدمة؟** Aspose.BarCode for Java  
- **ما نوع الباركود المعروض؟** Data Matrix  
- **كيف تقوم بتحديد موقع نص الرمز؟** باستخدام `CodeLocation.ABOVE`  
- **هل تحتاج إلى ترخيص للإنتاج؟** نعم، يتطلب ترخيص تجاري  
- **هل يمكن تشغيل الكود على Java 8+؟** بالتأكيد، يدعم Java 8 والإصدارات الأحدث  

## ما هو Data Matrix barcode؟

رمز Data Matrix هو رمز ثنائي الأبعاد (2‑D) يخزن كميات كبيرة من البيانات في نمط مربع أو مستطيل مدمج. يُستخدم على نطاق واسع لتعليم العناصر الصغيرة، والإلكترونيات، والأجهزة الطبية لأنه يمكنه ترميز ما يصل إلى 2,335 حرفًا أبجديًا رقميًا.

## لماذا تحديد موقع نص الباركود؟

وضع النص القابل للقراءة من قبل الإنسان **فوق**، **تحت**، أو **بجانب** الباركود يساعد المستخدمين على التحقق بسرعة من البيانات المشفرة دون الحاجة إلى المسح. تعديل موقع النص يحسن اتساق واجهة المستخدم ويتماشى مع إرشادات العلامة التجارية.

## المتطلبات المسبقة

- معرفة أساسية ببرمجة Java.  
- تثبيت Java Development Kit (JDK).  
- بيئة تطوير متكاملة (IDE) مثل Eclipse أو IntelliJ IDEA.  
- مكتبة Aspose.BarCode for Java (قم بتنزيلها من [here](https://releases.aspose.com/barcode/java/)).  

## استيراد الحزم

أولاً، استورد الفئات الأساسية من Aspose.BarCode إلى مشروعك:

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## دليل خطوة بخطوة

### الخطوة 1: تعريف مسارات الدليل
حدد المكان الذي تريد قراءة/كتابة الملفات فيه. استبدل القيم النائبة بالمسارات الفعلية على جهازك.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### الخطوة 2: إنشاء كائن BarcodeGenerator
أنشئ مثيلًا لـ `BarcodeGenerator` بنوع **Data Matrix** وقدم نص الرمز الذي ترغب في ترميزه.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### الخطوة 3: كيفية تحديد موقع نص الباركود
استخدم تعداد `CodeLocation` لتحريك النص القابل للقراءة من قبل الإنسان. في هذا المثال نضعه **فوق** الباركود.

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

### الخطوة 4: حفظ صورة الباركود المُولدة
أخيرًا، احفظ صورة الباركود إلى القرص. سيحتوي الملف على رمز Data Matrix مع النص موضعًا فوقه.

```java
generator.save(dataDir + "codetextAbove.png");
```

## المشكلات الشائعة والحلول
- **النص غير ظاهر:** تأكد من أنك تستخدم نسخة من Aspose.BarCode تدعم `CodeLocation`.  
- **أخطاء مسار الملف:** تحقق من أن `dataDir` ينتهي بفاصل ملفات (`/` أو `\\`) المناسب لنظام التشغيل الخاص بك.  
- **أحرف غير مدعومة:** يمكن لـ Data Matrix ترميز مجموعة محدودة فقط من الأحرف؛ تجنب الرموز الخاصة غير الموجودة في معيار ISO/IEC 16022.  

## الأسئلة المتكررة (FAQs)

### س: هل يمكنني تخصيص مظهر الباركود المُولد؟
ج: نعم، توفر Aspose.BarCode خيارات تخصيص واسعة، تتيح لك التحكم في الألوان والهوامش وأنماط الخط.

### س: هل Aspose.BarCode متوافق مع Java 8 والإصدارات اللاحقة؟
ج: بالتأكيد، المكتبة تعمل مع Java 8 وجميع الإصدارات اللاحقة.

### س: كيف يمكنني دمج Aspose.BarCode في مشروع Java الحالي؟
ج: أضف ملفات JAR الخاصة بـ Aspose.BarCode إلى مسار الفئة (classpath) في مشروعك، استورد الحزم المطلوبة، وستكون جاهزًا لتوليد الباركود.

### س: هل هناك نسخة تجريبية متاحة لـ Aspose.BarCode؟
ج: نعم، يمكنك استكشاف إمكانيات Aspose.BarCode بالحصول على نسخة تجريبية مجانية [here](https://releases.aspose.com/).

### س: أين يمكنني طلب المساعدة أو الدعم لـ Aspose.BarCode؟
ج: زر [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) للحصول على مساعدة المجتمع والدعم الرسمي.

## أسئلة متكررة إضافية

**س: هل يمكنني إنشاء باركود بنص موضعه أسفل الرمز؟**  
ج: نعم، اضبط `CodeLocation.BELOW` في نفس طريقة `setLocation`.

**س: هل تدعم المكتبة باركودات 2‑D أخرى مثل QR Code؟**  
ج: بالتأكيد، فقط غيّر `EncodeTypes.DATA_MATRIX` إلى `EncodeTypes.QR`.

**س: كيف يمكنني تغيير حجم خط نص الباركود؟**  
ج: استخدم `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`.

## الخلاصة

لقد تعلمت الآن كيفية **create data matrix barcode** في Java والتحكم بدقة في **how to set barcode text** باستخدام Aspose.BarCode. جرّب قيم `CodeLocation` الأخرى وخيارات التنسيق لتتناسب مع متطلبات تصميم تطبيقك.

---

**آخر تحديث:** 2025-12-27  
**تم الاختبار باستخدام:** Aspose.BarCode for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}