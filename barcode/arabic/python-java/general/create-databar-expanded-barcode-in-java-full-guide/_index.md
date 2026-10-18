---
category: general
date: 2026-10-18
description: إنشاء شيفرة باركود Databar الموسعة في Java باستخدام Aspose.BarCode. تعلم
  كيفية إنشاء Databar، ضبط الصفوف، وتصدير صورة الباركود بصيغة PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar expanded barcode
- how to generate databar
- barcode generator rows
- export barcode image
language: ar
lastmod: 2026-10-18
og_description: إنشاء باركود Databar موسع في جافا. اتبع هذا الدليل لتعلم كيفية إنشاء
  Databar، وتكوين الصفوف، وتصدير صورة الباركود بصيغة PNG.
og_image_alt: Screenshot of a Databar Expanded barcode saved as PNG
og_title: إنشاء باركود Databar Expanded في جافا – دليل خطوة بخطوة
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Create databar expanded barcode in Java with Aspose.BarCode. Learn
    how to generate databar, set rows, and export barcode image as PNG.
  headline: Create databar expanded barcode in Java – full guide
  type: TechArticle
tags:
- barcode
- Java
- Aspose
title: إنشاء شيفرة باركود Databar Expanded في جافا – دليل كامل
url: /ar/python-java/general/create-databar-expanded-barcode-in-java-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء شريط بيانات موسع (databar) في Java – دليل كامل

إذا كنت بحاجة إلى **إنشاء شريط بيانات موسع (databar) barcode** في Java، فإن هذا الدرس يوضح لك بالضبط **كيفية إنشاء صور databar** باستخدام مكتبة Aspose.BarCode. ستتعلم أيضًا كيفية تكوين **صفوف مولد الباركود** و **تصدير صورة الباركود** بصيغة PNG.

في الأقسام أدناه ستجد برنامجًا كاملاً قابلاً للتنفيذ، وشروحات خطوة بخطوة لكل استدعاء API، ونصائح للتعامل مع الحالات الطرفية الشائعة مثل الأحرف غير المدعومة أو أحجام التخطيط المخصصة. بنهاية هذا الدليل ستتمكن من إنتاج باركود Databar Expanded بأربعة أعمدة وثلاث صفوف وحفظه أينما تحتاج.

## المتطلبات المسبقة

* Java 17 أو أحدث (الكود يُترجم مع أي JDK 11+)
* Maven أو Gradle لإدارة التبعيات
* Aspose.BarCode for Java – أضف أحدث نسخة إلى ملف `pom.xml` أو `build.gradle`
* إلمام أساسي بطريقة `main` في Java ومفاهيم البرمجة الكائنية

```xml
<!-- Maven dependency -->
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-barcode</artifactId>
    <version>23.10</version>
</dependency>
```

> **نصيحة احترافية:** ترخيص التقييم المجاني يعمل للتطوير؛ استبدله بترخيص مدفوع قبل النشر في بيئة الإنتاج.

## إنشاء شريط بيانات موسع – الإعداد الأولي

الخطوة الأولى هي إنشاء كائن `BarcodeGenerator` من النوع `EncodeTypes.DatabarExpandedStacked` مع حمولة تجريبية. يمكن أن تكون هذه الحمولة أي سلسلة أبجدية رقمية تتوافق مع مواصفات Databar.

```java
import com.aspose.barcode.*;
import com.aspose.barcode.barcodeimageformat.*;
import com.aspose.barcode.encode.*;

public class DatabarExpandedDemo {

    public static void main(String[] args) throws Exception {
        // Step 1: Create a barcode generator for Databar Expanded Stacked with sample text
        BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
```

*لماذا هذا مهم*: `EncodeTypes.DatabarExpandedStacked` يخبر المكتبة باستخدام رموز Databar Expanded Stacked، التي تدعم سلاسل بيانات أطول من الـ Databar العادي.

## كيفية إنشاء databar بأعمدة مخصصة

يتيح لك Databar Expanded التحكم في عدد الأعمدة في التخطيط المكدس. ضبط الأعمدة مفيد عندما تحتاج إلى باركود مدمج لا يزال يتسع لعرض البيانات المطلوب.

```java
        // Step 2: Configure a 4‑column layout for the DataBar
        generator.getParameters().getBarcode().getDataBar().setColumns(4);
```

*شرح*: `setColumns(4)` يجبر المولد على تقسيم الباركود إلى أربعة أقسام عمودية. تقوم المكتبة تلقائيًا بضبط عرض الوحدة للحفاظ على حجم عام معقول.

## تصدير صورة الباركود بصيغة PNG – نسخة 4‑أعمدة

بمجرد تعريف التخطيط، يمكنك تصدير الباركود إلى ملف. PNG هو التنسيق الموصى به غير الفاقد لمعظم سيناريوهات واجهة المستخدم.

```java
        // Step 3: Save the 4‑column barcode image
        generator.save("output/DatabarExpandedCols4.png", BarCodeImageFormat.Png);
```

طريقة `save` تكتب الصورة إلى الدليل المحدد. إذا لم يكن الدليل موجودًا، سيقوم Java بإنشائه تلقائيًا.

## تكوين صفوف مولد الباركود

بالإضافة إلى الأعمدة، يدعم رموز Databar Expanded Stacked تخطيطًا قائمًا على الصفوف. التحويل من الأعمدة إلى الصفوف يمكن أن يحسن قابلية القراءة في الطباعة عالية الدقة.

```java
        // Step 4: Create a new generator for the same data (demonstrates a different layout)
        BarcodeGenerator rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

        // Step 5: Configure a 3‑row layout for the DataBar
        rowGenerator.getParameters().getBarcode().getDataBar().setRows(3);
```

*لماذا نستخدم الصفوف؟* تخطيط من 3 صفوف يوزع البيانات عموديًا، وهو مفيد للملصقات الضيقة حيث يكون الفضاء الأفقي محدودًا.

## تصدير صورة الباركود بصيغة PNG – نسخة 3‑صفوف

حفظ التخطيط الثاني يتبع نفس النمط كما في السابق. الحفاظ على أسماء الملفات مميزة يساعدك على مقارنة الاختلافات البصرية.

```java
        // Step 6: Save the 3‑row barcode image
        rowGenerator.save("output/DatabarExpandedRows3.png", BarCodeImageFormat.Png);
    }
}
```

### النتيجة المتوقعة

تشغيل البرنامج ينتج ملفين PNG:

| اسم الملف                     | وصف التخطيط                |
|------------------------------|----------------------------|
| `DatabarExpandedCols4.png`   | باركود مكدس من 4 أعمدة    |
| `DatabarExpandedRows3.png`   | باركود مكدس من 3 صفوف     |

كلا الصورتين تعرضان نفس السلسلة المشفرة، لكن الكثافة البصرية تختلف حسب إعدادات العمود/الصف.

## المشكلات الشائعة وكيفية تجنبها

| المشكلة                               | السبب                                   | الحل |
|--------------------------------------|------------------------------------------|------|
| الباركود يظهر ضبابيًا                | الحفظ بدقة DPI منخفضة                    | استخدم `generator.getParameters().setResolution(300)` قبل `save`. |
| النص مقطوع                           | الحمولة تتجاوز سعة Databar               | قلل الحمولة أو انتقل إلى `EncodeTypes.DatabarExpanded` (غير مكدس). |
| `NullPointerException` عند `setRows` | استخدام نسخة من Aspose.BarCode أقدم من 20.12 | قم بالترقية إلى أحدث نسخة من المكتبة. |

## تنويعات متقدمة (اختياري)

* **تغيير ألوان المقدمة/الخلفية** – استدعِ `generator.getParameters().getBarcode().setForeColor(Color.BLUE)` و `setBackColor(Color.WHITE)`.
* **إنشاء SVG بدلاً من PNG** – استبدل `BarCodeImageFormat.Png` بـ `BarCodeImageFormat.Svg`.
* **إدراج الباركود في PDF** – استخدم Aspose.PDF لإنشاء مستند وإضافة PNG كصورة.

## الخاتمة

أنت الآن تعرف **كيفية إنشاء شريط بيانات موسع (databar) barcode** في Java، **كيفية إنشاء databar** باستخدام كل من إعدادات الأعمدة والصفوف، وكيفية **تصدير صورة الباركود** بصيغة PNG. الكود الكامل جاهز للنسخ واللصق والتنفيذ في أي مشروع Java.

لا تتردد في تجربة تخطيطات أخرى، ألوان مختلفة، أو صيغ إخراج مختلفة. إذا وجدت هذا الدليل مفيدًا، ففكر في استكشاف وثائق Aspose.BarCode لمواضيع مثل *micro‑PDF417*، *تصحيح أخطاء QR code*، و *مسح الباركود*.

برمجة ممتعة!

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات التي تم توضيحها في هذا الدليل. كل مورد يتضمن أمثلة شاملة قابلة للتنفيذ مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك الخاصة.

- [كيفية إنشاء باركود في Java: إنشاء صورة باركود دقيقة](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)
- [دليل شريط بيانات موسع مكدس – كيفية الإنشاء وتحديد الحجم في C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [كيفية إنشاء باركود Databar متعدد الاتجاهات في C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}