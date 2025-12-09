---
date: 2025-12-08
description: تعلم كيفية إنشاء مستندات PDF بلغة Java وإضافة الباركود باستخدام Aspose.BarCode.
  دليل خطوة بخطوة لإنشاء وتضمين الباركود في ملفات PDF.
linktitle: Adding Barcode to PDF Document
second_title: Aspose.BarCode Java API
title: كيفية إنشاء مستند PDF بلغة Java مع باركود باستخدام Aspose.BarCode
url: /ar/java/barcode-basics/adding-barcode-to-pdf-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء مستند PDF Java مع باركود باستخدام Aspose.BarCode

## المقدمة

إنشاء مستندات PDF Java تحتوي على باركود يمكن قراءته آليًا هو طلب شائع لأنظمة الجرد، ملصقات الشحن، وتدفقات العمل الآمنة للوثائق. في هذا البرنامج التعليمي ستتعلم **كيفية إنشاء مستندات PDF Java** وتضمين باركود مباشرةً في الملف باستخدام **Aspose.BarCode for Java**. سنستعرض كل خطوة — من توليد صورة الباركود إلى إدراجها في ملف PDF موجود — حتى تتمكن من إضافة وظيفة الباركود إلى تطبيقات Java الخاصة بك في دقائق.

## إجابات سريعة
- **ما المكتبة التي أحتاجها؟** Aspose.BarCode for Java (بالإضافة إلى Aspose.PDF لمعالجة PDF).  
- **هل يمكنني توليد أي نوع من الباركود؟** نعم — يدعم Aspose.BarCode أكثر من 50 رموزًا، بما في ذلك Code 39، QR، DataMatrix، وأكثر.  
- **هل أحتاج إلى ترخيص للتطوير؟** ترخيص مؤقت يكفي للتقييم؛ الترخيص الكامل مطلوب للإنتاج.  
- **هل الكود متوافق مع Java 8+؟** بالتأكيد — الـ API تستهدف Java 8 وما بعدها.  
- **كم من الوقت تستغرق العملية؟** تقريبًا 10‑15 دقيقة لسيناريو “إضافة باركود إلى PDF” الأساسي.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من توفر ما يلي:

- **Java Development Kit (JDK)** — أحدث نسخة مستقرة مثبتة.  
- **Aspose.BarCode for Java** — حمّلها من [صفحة التحميل](https://releases.aspose.com/barcode/java/).  
- **Aspose.PDF for Java** — مطلوبة لمعالجة ملفات PDF (تأتي مدمجة مع حزمة BarCode).  

## استيراد المساحات الاسمية

أولاً، استورد الفئات التي ستحتاجها. هذه الخطوة تُعد البيئة لتوليد الباركود ومعالجة PDF.

```java
// Import Aspose.BarCode namespaces
import com.aspose.pdf.*;
import com.aspose.pdf.facades.*;

import com.aspose.barcode.generation.*;
import com.aspose.barcode.*;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.InputStream;
import java.io.OutputStream;

import com.aspose.barcode.EncodeTypes;
```

## الخطوة 1: إعداد مشروع Java الخاص بك

أنشئ مشروع Java جديد في بيئة التطوير المفضلة لديك (IntelliJ IDEA، Eclipse، NetBeans، إلخ). أضف ملف **Aspose.BarCode.jar** (ومعتمداته) إلى مسار بناء المشروع. يضمن ذلك أن المترجم يستطيع العثور على الفئات المشار إليها أعلاه.

## الخطوة 2: توليد صورة الباركود – *كيفية إضافة باركود*

أنشئ كائن `BarcodeGenerator`، اختر رمزًا، واضبط نص الكود. هنا تقوم **بتحديد رمز الباركود** و**توليد كائنات باركود Java**.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD, "1234567");
generator.save(dataDir + "barcodeToPDF.bmp", BarCodeImageFormat.BMP);
```

> **نصيحة احترافية:** استبدل `EncodeTypes.CODE_39_STANDARD` بأي قيمة أخرى من `EncodeTypes` (مثل `QR`، `DATA_MATRIX`) لتوليد صيغ باركود مختلفة.

## الخطوة 3: إنشاء مستند PDF – *إضافة صورة PDF Java*

الآن سن **ننشئ مستند PDF** سيستضيف صورة الباركود. تجعل Aspose.PDF هذه العملية بسيطة.

```java
Document doc = new Document();
doc.getPages().add();
```

في هذه المرحلة لديك ملف PDF فارغ جاهز لاستقبال المحتوى.

## الخطوة 4: إضافة صورة الباركود إلى مستند PDF – *إضافة باركود إلى PDF موجود*

إذا كنت بحاجة إلى تضمين الباركود في **PDF موجود**، يمكنك فتح الملف باستخدام `PdfFileMend`. يربط الكود التالي ملف PDF، يُدرج صورة الباركود، ويحفظ النتيجة.

```java
PdfFileMend mender = new PdfFileMend();
mender.bindPdf(doc);
mender.addImage(in, 1, 100, 600, 200, 700);
mender.save(dataDir + "AddImage_out.pdf");
mender.close();
```

- `in` هو `InputStream` يشير إلى صورة الباركود التي أنشأتها مسبقًا.  
- المعاملات الرقمية (`1, 100, 600, 200, 700`) تحدد رقم الصفحة وموقعها (إحداثيات X، Y، العرض، الارتفاع). عدّلها لتناسب تخطيطك.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|--------|------|
| **الصورة لا تظهر** | إحداثيات غير صحيحة أو رقم صفحة خاطئ. | تحقق من رقم الصفحة (`1` للصفحة الأولى) وتأكد من أن تدفق الصورة لم يُغلق قبل `addImage`. |
| **نوع باركود غير مدعوم** | استخدام رمز غير مشمول في الترخيص. | افحص ملف الترخيص؛ قم بالترقية إذا لزم الأمر. |
| **FileNotFoundException** | مسار `dataDir` غير صحيح. | استخدم مسارًا مطلقًا أو `System.getProperty("user.dir")` لبناء الدليل ديناميكيًا. |

## الأسئلة المتكررة

**س: هل يمكنني تخصيص مظهر الباركود في مستند PDF؟**  
ج: نعم. يتيح لك Aspose.BarCode تغيير الألوان، الخطوط، الهوامش، وحتى إضافة نص قابل للقراءة البشرية. اضبط خصائص `BarcodeGenerator` قبل الحفظ.

**س: هل Aspose.BarCode متوافق مع رموز باركود مختلفة؟**  
ج: بالتأكيد. يدعم أكثر من 50 رمزًا، بما في ذلك Code 128، QR، DataMatrix، PDF417، وغيرها.

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.BarCode؟**  
ج: زر [صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/) على موقع Aspose لطلب ترخيص تجريبي لمدة 30 يومًا.

**س: أين يمكنني طلب المساعدة والدعم بخصوص استفسارات Aspose.BarCode؟**  
ج: منتدى [Aspose.BarCode](https://forum.aspose.com/c/barcode/13) هو مجتمع نشط يمكنك طرح الأسئلة فيه ومشاركة الحلول.

**س: هل يمكن تجربة Aspose.BarCode for Java مجانًا قبل الشراء؟**  
ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من [صفحة الإصدارات](https://releases.aspose.com/) واستكشاف جميع الميزات دون الحاجة إلى ترخيص.

## الخاتمة

أنت الآن تعرف **كيفية إنشاء مستندات PDF Java** وتضمين باركود باستخدام Aspose.BarCode. هذه القدرة تُسهل سير العمل مثل توليد ملصقات الشحن، إنشاء فواتير آمنة، أو بناء أنظمة تتبع المخزون. جرّب رموزًا مختلفة، عدّل موضع الصورة، ودمج الكود في خدمات Java أكبر للاستفادة الكاملة من تقنية الباركود.

---

**آخر تحديث:** 2025-12-08  
**تم الاختبار مع:** Aspose.BarCode 24.11 for Java، Aspose.PDF 24.11 for Java  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}