---
date: 2026-04-05
description: تعلم كيفية إنشاء صورة باركود كودابار في جافا مع التحقق من المجموع، وشاهد
  مثالًا على قارئ باركود جافا باستخدام Aspose.BarCode. اتبع هذا الدليل خطوة بخطوة
  لتوليد الباركودات والتعرف عليها.
keywords:
- create codabar barcode java
- java barcode reader example
- codabar checksum
- aspose barcode java
linktitle: تطبيق التحقق من المجموع لـ CodaBar
second_title: Aspose.BarCode Java API
title: كيفية إنشاء صورة باركود كودابار في جافا مع قيمة التحقق
url: /ar/java/checksum-and-validation/applying-checksum-codabar/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء صورة باركود كودابار جافا مع التحقق من المجموع

## المقدمة

في هذا الدرس، ستقوم **بإنشاء صور باركود كودابار جافا** مع تحقق من المجموع Mod 10 باستخدام Aspose.BarCode لجافا. سنستعرض عملية إنشاء باركود CodaBar، وتمكين التحقق من المجموع، ثم التحقق منه باستخدام **مثال قارئ باركود جافا**. في النهاية، ستحصل على مقتطف جاهز للاستخدام يمكنك إدراجه في أي مشروع جافا، سواء كنت تبني نظام مكتبة، أو طابعة ملصقات مختبر طبي، أو حل نقاط بيع تجاري.

## إجابات سريعة
- **ماذا يفعل التحقق من المجموع؟** يتحقق من سلامة بيانات الباركود أثناء المسح.  
- **ما المكتبة المطلوبة؟** Aspose.BarCode لجافا.  
- **هل أحتاج إلى ترخيص للتطوير؟** ترخيص مؤقت يعمل للاختبار؛ ترخيص كامل مطلوب للإنتاج.  
- **هل يمكنني تخصيص مظهر الباركود؟** نعم – يمكن تغيير اللون والحجم والخط عبر معلمات المولد.  
- **هل هذا متوافق مع جميع إصدارات جافا؟** المكتبة تدعم جافا 8 وما بعدها.

## كيفية إنشاء باركود كودابار جافا

فيما يلي دليل مختصر خطوة بخطوة يوضح **سبب أهمية كل سطر**، حتى تتمكن من تعديل الكود لمشاريعك بثقة.

### ما هو باركود كودابار؟

CodaBar هو رموز خطية (أحادية البعد) تُستخدم على نطاق واسع في المكتبات، وبنوك الدم، وتجارة التجزئة. يقوم بترميز البيانات الرقمية وبعض الأحرف الخاصة، مما يجعله مثالياً للعلامات البسيطة القابلة للقراءة آلياً. إضافة تحقق من المجموع (Mod 10) يحسن دقة القراءة، خاصةً على الطباعة منخفضة الجودة.

### لماذا نستخدم Aspose.BarCode لجافا؟

Aspose.BarCode يقدم **مثال قارئ باركود جافا** الذي يج abstracts التفاصيل منخفضة المستوى لإنشاء الباركود والتعرف عليه. يوفر:
* تحكم كامل في أوضاع التحقق من المجموع.  
* تكامل سلس مع بيئات تطوير جافا (IDE).  
* وثائق شاملة ودعم سريع.  

### المتطلبات المسبقة

قبل أن نبدأ، تأكد من أن لديك:
- Java Development Kit (JDK) 8 أو أحدث مثبت.  
- مكتبة Aspose.BarCode لجافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/barcode/java/).  
- إلمام أساسي بمفاهيم برمجة جافا.  

### استيراد الحزم

في مشروع جافا الخاص بك، استورد الفئات اللازمة للعمل مع Aspose.BarCode:

```java
import java.io.IOException;

import com.aspose.barcode.CodabarChecksumMode;
import com.aspose.barcode.EnableChecksum;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.ChecksumValidation;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.barcode.generation.BarcodeGenerator;
```

### دليل خطوة بخطوة

#### الخطوة 1: إعداد البيئة

أنشئ مشروع جافا جديد وأضف ملف Aspose.BarCode JAR إلى مسار البناء. حدد مجلدًا لحفظ الصور المولدة.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

#### الخطوة 2: إنشاء صورة باركود كودابار مع التحقق من المجموع

أنشئ كائن `BarcodeGenerator`، فعّل التحقق من المجموع، اختر وضع Mod 10، واحفظ الصورة.

```java
// Instantiate BarcodeGenerator object
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "1234567890");

// Set the EnableChecksum property to yes
generator.getParameters().getBarcode().setChecksumEnabled(EnableChecksum.YES);

// Set the CodabarChecksumMode
generator.getParameters().getBarcode().getCodabar().setCodabarChecksumMode(CodabarChecksumMode.MOD_10);

// Save the image on the system
generator.save(dataDir + "Codabar_Mod10.png");
```

#### الخطوة 3: مثال قارئ باركود جافا – التعرف على الباركود

الآن اقرأ الباركود مرة أخرى، مع تفعيل التحقق من المجموع لضمان صحة البيانات.

```java
// Initialize reader object
BarCodeReader reader = new BarCodeReader(dataDir + "Codabar_Mod10.png", DecodeType.CODABAR);

// Set ChecksumValidation property of the reader to On
reader.setChecksumValidation(ChecksumValidation.ON);

for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());

    // Get checksum value
    System.out.println("Checksum:" + result.getExtended().getOneD().getCheckSum());
}
```

تشغيل الكود سيطبع النص المفكك، نوع الرمز، والتحقق من المجموع المحسوب، مما يؤكد أن الباركود تم إنشاؤه والتحقق منه بنجاح.

### حالات الاستخدام الشائعة

- **إدارة المكتبة:** ترميز معرفات الكتب للمسح السريع عند الخروج.  
- **ملصقات بنك الدم:** ضمان تحديد المريض بدقة مع حماية التحقق من المجموع.  
- **ملصقات رفوف التجزئة:** طباعة باركود منخفض التكلفة وعالي السرعة لتتبع المخزون.  

### المشكلات الشائعة والحلول

| المشكلة | الحل |
|-------|----------|
| **فشل التحقق من المجموع** | تحقق من أن `EnableChecksum` مضبوطة على `YES` وأن `CodabarChecksumMode` يطابق الوضع المستخدم أثناء الإنشاء (Mod 10). |
| **خطأ الملف غير موجود** | تأكد من أن `dataDir` يشير إلى مجلد موجود وأن الصورة المولدة (`Codabar_Mod10.png`) محفوظة هناك قبل القراءة. |
| **إصدار جافا غير مدعوم** | استخدم جافا 8 أو أحدث؛ قد تفتقر الإصدارات القديمة إلى واجهات برمجة التطبيقات المطلوبة. |

## الأسئلة المتكررة

**س: هل Aspose.BarCode متوافق مع جميع إصدارات جافا؟**  
ج: تم تصميم Aspose.BarCode للعمل مع جافا 8 وما بعدها. تحقق من الوثائق الرسمية للحصول على توافق مفصل.

**س: هل يمكنني تخصيص مظهر الباركود المولد؟**  
ج: نعم، يمكنك تعديل الألوان، الخطوط، وتنسيق الصورة عبر واجهة برمجة معلمات المولد.

**س: هل تتوفر تراخيص مؤقتة لأغراض الاختبار؟**  
ج: نعم، يمكنك الحصول على ترخيص مؤقت لـ Aspose.BarCode من [هنا](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني العثور على دعم وموارد إضافية؟**  
ج: زر [منتدى Aspose.BarCode](https://forum.aspose.com/c/barcode/13) للحصول على دعم المجتمع والنقاشات.

**س: هل هناك نسخة تجريبية مجانية متاحة؟**  
ج: نعم، يمكنك استكشاف ميزات Aspose.BarCode بتحميل النسخة التجريبية المجانية من [هنا](https://releases.aspose.com/).

---

**آخر تحديث:** 2026-04-05  
**تم الاختبار مع:** Aspose.BarCode for Java 24.12  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}