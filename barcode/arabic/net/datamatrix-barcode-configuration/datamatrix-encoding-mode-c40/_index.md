---
date: 2026-06-09
description: تعلم كيفية إنشاء رموز DataMatrix وحفظها كصورة PNG باستخدام ترميز C40
  مع Aspose.BarCode – دليل كامل لتوليد الرموز الشريطية في .NET Core.
keywords:
- how to generate datamatrix
- barcode generation .net core
- datamatrix c40 png
linktitle: وضع ترميز DataMatrix (C40)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  headline: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  type: TechArticle
- description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  name: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  steps:
  - name: Define the Directory Path
    text: Set the folder where the PNG image will be stored. Replace the placeholder
      with an actual path on your machine.
  - name: Set Up Barcode Generation
    text: Create a `BarcodeGenerator` instance, specify `EncodeTypes.DataMatrix`,
      and provide the data you want to encode.
  - name: Customize Barcode
    text: Configure the X‑dimension (pixel width of the modules) and switch the encoding
      mode to C40.
  - name: Save the Barcode Image
    text: Finally, save the generated barcode as a PNG file. This is the concrete
      answer to **how to save png** with Aspose.BarCode. When you run the program,
      you’ll find `DataMatrixEncodeModeC40.png` in the folder you specified, ready
      to be used in reports, labels, or web pages.
  type: HowTo
- questions:
  - answer: C40 is a compact alphanumeric encoding scheme for DataMatrix symbols,
      ideal for text that includes letters, numbers, and a limited set of special
      characters.
    question: What is DataMatrix Encoding Mode (C40)?
  - answer: You can find the documentation [here](https://reference.aspose.com/barcode/net/).
      It provides detailed guidance on all barcode types and encoding options.
    question: Where can I find the Aspose.BarCode for .NET documentation?
  - answer: Yes, the library supports a wide range of .NET versions, from .NET Framework
      4.5+ to .NET 6 and later.
    question: Is Aspose.BarCode for .NET compatible with all .NET versions?
  - answer: Yes, you can explore a free trial of Aspose.BarCode for .NET by visiting
      [this link](https://releases.aspose.com/). It allows you to test the library’s
      features and capabilities.
    question: Can I try Aspose.BarCode for .NET before purchasing?
  - answer: You can find a supportive community and access support for Aspose.BarCode
      for .NET on the [Aspose forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: كيفية إنشاء صورة PNG لرمز DataMatrix باستخدام الترميز C40 مع Aspose.BarCode
url: /ar/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# وضع ترميز DataMatrix الرئيسي (C40) باستخدام Aspose.BarCode لـ .NET

## المقدمة

في هذا الدرس ستتعلم **كيفية إنشاء باركودات datamatrix** وحفظها كملفات PNG باستخدام وضع الترميز C40 مع Aspose.BarCode لـ .NET. سواءً كنت تبني نظام جرد، أو مولد ملصقات شحن، أو أي حل يتطلب رموزًا مدمجة وعالية الكثافة، فإن إتقان C40 يمنحك رموزًا أصغر دون التضحية بالقراءة. سنستعرض كل خطوة — من إعداد البيئة إلى إنتاج ملف PNG النهائي — حتى تتمكن من دمج الشيفرة مباشرةً في مشروعك.

## إجابات سريعة
- **ماذا يعني “كيفية إنشاء datamatrix”؟** إنشاء صورة باركود DataMatrix برمجيًا.  
- **ما وضع الترميز الذي يتم تغطيته؟** DataMatrix C40، مخطط أبجدي رقمي فعال.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للاختبار؛ يلزم ترخيص تجاري للإنتاج.  
- **هل يمكن تشغيل هذا على .NET Core؟** نعم، Aspose.BarCode يدعم بالكامل .NET Core، .NET 5، .NET 6 وما بعده.  
- **ما هو تنسيق الملف الناتج؟** PNG – تنسيق صورة غير مضغوط وصديق للويب.

## كيفية إنشاء DataMatrix باستخدام ترميز C40

حمّل بياناتك، اضبط المُولِّد، واستدعِ `Save` – هذه هي سير العمل الكامل في ثلاث خطوات مختصرة. تتولى فئة `BarcodeGenerator` إنشاء الرمز، بينما يحدد تعداد `BarCodeImageFormat.Png` لـ Aspose.BarCode كتابة النتيجة كملف PNG. تقوم `Save` بكتابة صورة الباركود المُولَّدة إلى مسار الملف المحدد بالتنسيق المختار. تُقدم هذه الفقرة إجابة مباشرة لكامل الحل قبل أن نتعمق في كل سطر من الشيفرة.

## ما هو وضع ترميز DataMatrix (C40)؟

`DataMatrixEncodeMode` هو تعداد يحدد أي مخطط ترميز يجب أن يستخدمه Aspose.BarCode لرموز DataMatrix. يختار الخيار `DataMatrixEncodeMode.C40` ترميز C40 الأبجدي الرقمي، الذي يجمع الحروف والأرقام ومجموعة محدودة من علامات الترقيم في عدد أقل من الوحدات، مما يقلل حجم الرمز الكلي مع الحفاظ على قابلية القراءة للنصوص الشائعة في الجرد. هذا المخطط الفعال مثالي عندما تحتاج إلى ترميز بيانات أبجدية رقمية بشكل مدمج.

## لماذا نستخدم Aspose.BarCode لـ .NET؟

يوفر Aspose.BarCode **أكثر من 30 معلمة قابلة للتكوين** للأبعاد، ومستويات تصحيح الأخطاء، ووضعيات الترميز، ويدعم **أكثر من 50 تنسيقًا للصور والباركود**. تعمل المكتبة على **.NET Framework 4.5+، .NET Core 2.0+، .NET 5/6+**، مما يتيح توليدًا بدون تبعيات يعمل على الخوادم، وأجهزة سطح المكتب، والأجهزة المحمولة على حدٍ سواء.

## المتطلبات المسبقة

1. **بيئة تطوير .NET** – Visual Studio، Rider، أو أي بيئة تطوير تدعم C#.  
2. **Aspose.BarCode لـ .NET** – مثبت عبر NuGet أو المثبت الرسمي. راجع [documentation](https://reference.aspose.com/barcode/net/) للتفاصيل.  
3. **معرفة أساسية بـ C#** – يجب أن تكون مرتاحًا مع المساحات الاسمية، الفئات، وتعليمات using.  
4. **مجلد بصلاحية كتابة** – دليل على جهازك حيث سيتم حفظ ملف PNG.

## استيراد المساحات الاسمية الضرورية

فئة `BarcodeGenerator` هي نقطة الدخول لإنشاء أي باركود. أضف مساحة الاسم المطلوبة في أعلى ملف C# الخاص بك لتتمكن من الوصول إلى واجهة برمجة التطبيقات الخاصة بالتوليد:

```csharp
using Aspose.BarCode.Generation;
```

## توليد الباركود خطوة بخطوة

فيما يلي دليل **خطوة بخطوة لإنشاء الباركود**. يتم شرح كل خطوة بلغة بسيطة، وتُحافظ على العناصر النائبة الأصلية دون تغيير لتسهيل النسخ واللصق.

### الخطوة 1: تحديد مسار الدليل
حدد المجلد الذي سيُحفظ فيه ملف PNG. استبدل العنصر النائب بمسار فعلي على جهازك.

```csharp
string path = "Your Directory Path";
```

### الخطوة 2: إعداد توليد الباركود
أنشئ كائنًا من `BarcodeGenerator`، حدد `EncodeTypes.DataMatrix`، وقدم البيانات التي تريد ترميزها.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### الخطوة 3: تخصيص الباركود
اضبط البُعد X (عرض البكسل للوحدات) وقم بتغيير وضع الترميز إلى C40.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### الخطوة 4: حفظ صورة الباركود
أخيرًا، احفظ الباركود المُولَّد كملف PNG. هذه هي الإجابة العملية على **كيفية حفظ png** باستخدام Aspose.BarCode.

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

عند تشغيل البرنامج، ستجد `DataMatrixEncodeModeC40.png` في المجلد الذي حددته، جاهزًا للاستخدام في التقارير أو الملصقات أو صفحات الويب.

## المشكلات الشائعة والنصائح

- **مسار غير صالح** – تأكد من وجود الدليل وأن لديك صلاحيات كتابة؛ وإلا ستطلق `gen.Save` استثناءً.  
- **وضع ترميز غير صحيح** – إذا كنت بحاجة إلى ترميز أحرف خارج مجموعة C40، فغيّر إلى `DataMatrixEncodeMode.Auto` أو وضع آخر مناسب.  
- **حجم الصورة** – اضبط `XDimension.Pixels` لزيادة أو تقليل حجم الباركود الكلي دون التأثير على قابلية القراءة.

## الأسئلة المتكررة

**س: ما هو وضع ترميز DataMatrix (C40)؟**  
ج: C40 هو مخطط ترميز أبجدي رقمي مدمج لرموز DataMatrix، مثالي للنص الذي يتضمن حروفًا وأرقامًا ومجموعة محدودة من الأحرف الخاصة.

**س: أين يمكنني العثور على وثائق Aspose.BarCode لـ .NET؟**  
ج: يمكنك العثور على الوثائق [هنا](https://reference.aspose.com/barcode/net/). توفر إرشادات مفصلة حول جميع أنواع الباركود وخيارات الترميز.

**س: هل Aspose.BarCode لـ .NET متوافق مع جميع إصدارات .NET؟**  
ج: نعم، تدعم المكتبة مجموعة واسعة من إصدارات .NET، من .NET Framework 4.5+ إلى .NET 6 وما بعده.

**س: هل يمكنني تجربة Aspose.BarCode لـ .NET قبل الشراء؟**  
ج: نعم، يمكنك تجربة نسخة تجريبية مجانية من Aspose.BarCode لـ .NET بزيارة [هذا الرابط](https://releases.aspose.com/). يتيح لك اختبار ميزات المكتبة وإمكاناتها.

**س: أين يمكنني الحصول على الدعم لـ Aspose.BarCode لـ .NET؟**  
ج: يمكنك العثور على مجتمع داعم والوصول إلى الدعم لـ Aspose.BarCode لـ .NET في [منتدى Aspose](https://forum.aspose.com/c/barcode/13).

## الخاتمة

باتباعك لهذا الدليل **الباركود خطوة بخطوة**، أصبحت الآن تعرف بالضبط **كيفية إنشاء باركودات datamatrix** وحفظها كملفات PNG باستخدام وضع الترميز C40 مع Aspose.BarCode لـ .NET. يمنحك هذا النهج تحكمًا كاملاً في مظهر الباركود وحجمه وتمثيل البيانات، مما يسهل دمج باركودات عالية الجودة في أي تطبيق .NET.

---

**Last Updated:** 2026-06-09  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [ترميز DataMatrix بالبايتات باستخدام Aspose.BarCode لـ .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [ترميز DataMatrix الرئيسي بـ ASCII باستخدام Aspose.BarCode لـ .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [كيفية إنشاء باركودات DataMatrix (ECC 200) باستخدام Aspose.BarCode لـ .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}