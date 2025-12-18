---
date: 2025-12-18
description: تعلم كيفية إنشاء صورة باركود كودابار وشاهد مثال قارئ باركود جافا باستخدام
  Aspose.BarCode. قم بإنشاء وتعرف على الباركود بسهولة مع هذا الدليل خطوة بخطوة.
linktitle: Applying Checksum for CodaBar
second_title: Aspose.BarCode Java API
title: كيفية إنشاء صورة باركود كودابار مع التحقق من المجموع في جافا
url: /ar/java/checksum-and-validation/applying-checksum-codabar/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء صورة باركود Codabar مع checksum في Java

## المقدمة

في هذا الدرس، ستتعلم كيفية **إنشاء صورة باركود Codabar** مع checksum في Java باستخدام Aspose.BarCode. سنستعرض خطوات توليد باركود CodaBar، تمكين الـ checksum، ثم قراءته مرة أخرى باستخدام **مثال قارئ باركود java**. في النهاية، ستحصل على مقتطف شفرة جاهز يمكنك إدراجه في أي مشروع Java.

## إجابات سريعة
- **ماذا يفعل checksum؟** يتحقق من سلامة بيانات الباركود أثناء المسح.  
- **ما المكتبة المطلوبة؟** Aspose.BarCode for Java.  
- **هل أحتاج إلى ترخيص للتطوير؟** ترخيص مؤقت يكفي للاختبار؛ الترخيص الكامل مطلوب للإنتاج.  
- **هل يمكنني تخصيص مظهر الباركود؟** نعم – يمكن تغيير اللون، الحجم، والخط عبر معلمات المولد.  
- **هل هذا متوافق مع جميع إصدارات Java؟** المكتبة تدعم Java 8 وما فوق.

## ما هو باركود CodaBar؟

CodaBar هو رمز خطي (أحادي‑الأبعاد) يُستخدم على نطاق واسع في المكتبات، بنوك الدم، وتجارة التجزئة. يشفّر بيانات رقمية وبعض الأحرف الخاصة، مما يجعله مثالياً للبطاقات القابلة للقراءة الآلية البسيطة. إضافة checksum (Mod 10) يحسن دقة القراءة، خاصةً على الطباعة منخفضة الجودة.

## لماذا نستخدم Aspose.BarCode for Java؟

Aspose.BarCode يقدم **مثال قارئ باركود java** يُبسط التفاصيل التقنية لتوليد الباركود والتعرف عليه. يوفر:

* تحكم كامل في أوضاع checksum.  
* تكامل سلس مع بيئات تطوير Java.  
* وثائق ودعم موسع.  

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من وجود ما يلي:

- مجموعة تطوير Java (JDK) مثبتة على جهازك.  
- مكتبة Aspose.BarCode for Java. يمكنك تحميلها من [هنا](https://releases.aspose.com/barcode/java/).  
- فهم أساسي لبرمجة Java.  

## استيراد الحزم

في مشروع Java الخاص بك، استورد الفئات اللازمة للعمل مع Aspose.BarCode:

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

## دليل خطوة بخطوة

### الخطوة 1: إعداد البيئة

أنشئ مشروع Java جديد وأضف ملف JAR الخاص بـ Aspose.BarCode إلى مسار البناء. حدد مجلدًا سيتم حفظ الصور المولدة فيه.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### الخطوة 2: توليد صورة باركود CodaBar مع checksum

أنشئ كائن `BarcodeGenerator`، فعّل الـ checksum، اختر وضع Mod 10، واحفظ الصورة.

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

### الخطوة 3: مثال قارئ باركود Java – التعرف على الباركود

الآن اقرأ الباركود مرة أخرى، مع تفعيل التحقق من checksum لضمان صحة البيانات.

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

تشغيل الشيفرة سيظهر النص المفكك، نوع الرمز، والـ checksum المحسوب، مؤكدًا أن الباركود تم توليده والتحقق منه بنجاح.

## المشكلات الشائعة والحلول

| المشكلة | الحل |
|-------|----------|
| **فشل التحقق من checksum** | تأكد من أن `EnableChecksum` مضبوط على `YES` وأن `CodabarChecksumMode` يطابق الوضع المستخدم أثناء التوليد (Mod 10). |
| **خطأ ملف غير موجود** | تأكد من أن `dataDir` يشير إلى مجلد موجود وأن الصورة المولدة (`Codabar_Mod10.png`) تم حفظها هناك قبل القراءة. |
| **إصدار Java غير مدعوم** | استخدم Java 8 أو أحدث؛ الإصدارات الأقدم قد تفتقر إلى واجهات برمجة التطبيقات المطلوبة. |

## الأسئلة المتكررة

**س: هل Aspose.BarCode متوافق مع جميع إصدارات Java؟**  
ج: تم تصميم Aspose.BarCode للعمل مع Java 8 وما فوق. راجع الوثائق الرسمية للحصول على تفاصيل التوافق.

**س: هل يمكنني تخصيص مظهر الباركود المولّد؟**  
ج: نعم، يمكنك تعديل الألوان، الخطوط، وتنسيق الصورة عبر واجهة برمجة معلمات المولد.

**س: هل تتوفر تراخيص مؤقتة لأغراض الاختبار؟**  
ج: نعم، يمكنك الحصول على ترخيص مؤقت لـ Aspose.BarCode من [هنا](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني العثور على دعم وموارد إضافية؟**  
ج: زر منتدى [Aspose.BarCode](https://forum.aspose.com/c/barcode/13) للحصول على دعم المجتمع والنقاشات.

**س: هل هناك نسخة تجريبية مجانية؟**  
ج: نعم، يمكنك استكشاف ميزات Aspose.BarCode بتحميل النسخة التجريبية المجانية من [هنا](https://releases.aspose.com/).

---

**آخر تحديث:** 2025-12-18  
**تم الاختبار مع:** Aspose.BarCode for Java 24.12  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}