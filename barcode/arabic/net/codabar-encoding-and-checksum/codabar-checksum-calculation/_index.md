---
date: 2026-01-04
description: تعلم كيفية إضافة قيمة التحقق عند إنشاء باركود Codabar باستخدام Aspose.BarCode
  لـ .NET. دليل خطوة بخطوة يغطي وضعيات التحقق Mod10 و Mod16.
linktitle: Codabar Checksum Calculation
second_title: Aspose.BarCode .NET API
title: كيفية إضافة المجموع الاختباري إلى باركودات كودابار باستخدام Aspose.BarCode
  لـ .NET
url: /ar/net/codabar-encoding-and-checksum/codabar-checksum-calculation/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة مجموع تحقق إلى رموز الباركود Codabar باستخدام Aspose.BarCode لـ .NET

Codabar هو نظام ترميز شريطي خطي واسع الانتشار، خاصة في اللوجستيات والمكتبات والرعاية الصحية. إضافة مجموع تحقق إلى رمز الباركود Codabar يحسن بشكل كبير من سلامة البيانات عن طريق اكتشاف أخطاء النسخ قبل أن تصبح مشكلة. في هذا الدرس ستتعلم **كيفية إضافة مجموع تحقق** عند إنشاء رمز باركود Codabar باستخدام Aspose.BarCode لـ .NET، وسترى وضعيات مجموع التحقق Mod10 وMod16 قيد التنفيذ.

## إجابات سريعة
- **ماذا يعني “إضافة مجموع تحقق” لرمز Codabar؟** يضيف أرقامًا للكشف عن الأخطاء تتحقق من صحة البيانات المشفرة.
- **ما وضعيات مجموع التحقق المدعومة؟** Mod10 (الشائع) وMod16 (للحالات التي تتطلب دقة أعلى).
- **هل أحتاج إلى ترخيص لاستخدام هذه الميزة؟** نعم، يلزم وجود ترخيص صالح لـ Aspose.BarCode لـ .NET للاستخدام في بيئة الإنتاج.
- **ما إصدارات .NET المتوافقة؟** المكتبة تعمل مع .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.
- **أين يمكنني العثور على الصور المولدة؟** يتم حفظها في المجلد الذي تحدده في المتغير `path`.

## ما هو “كيفية إضافة مجموع تحقق” في Codabar؟
إضافة مجموع تحقق تعني تكوين مولد الباركود لحساب وإلحاق رقم (أو أرقام) إضافية بناءً على البيانات التي تقدمها. يتم التحقق من هذه المعلومات الإضافية بواسطة القارئات، مما يقلل من فرص الأخطاء في القراءة.

## لماذا توليد باركود Codabar مع مجموع تحقق؟
- **تحسين الموثوقية:** يكتشف أخطاء الأحرف الفردية ومعظم أخطاء التبديل.
- **الامتثال:** بعض الصناعات (مثل بنوك الدم) تتطلب باركودات مفعلة بمجموع تحقق.
- **المرونة:** يتيح لك Aspose.BarCode التبديل بين Mod10 وMod16 بتغيير خاصية واحدة فقط.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من توفر ما يلي:

1. **Aspose.BarCode لـ .NET** – قم بتحميل أحدث نسخة من [هنا](https://releases.aspose.com/barcode/net/).  
2. **بيئة تطوير C#** – Visual Studio أو VS Code أو أي بيئة تطوير تدعم .NET.

الآن بعد أن تم إعداد كل شيء، دعنا نستعرض التنفيذ خطوة بخطوة.

## استيراد المساحات الاسمية

أضف مساحة الأسماء المطلوبة في أعلى ملف C# الخاص بك لتتمكن من الوصول إلى فئات توليد الباركود:

```csharp
using Aspose.BarCode.Generation;
```

## الخطوة 1: تهيئة مولد الباركود

أنشئ كائنًا من `BarcodeGenerator`، حدد نظام الترميز Codabar، وقدم البيانات التي تريد ترميزها. تذكر استبدال `"Your Directory Path"` بالمجلد الفعلي الذي تريد حفظ الصور فيه.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarChecksum:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

## الخطوة 2: توليد باركود Codabar **بدون** مجموع تحقق

إذا كنت بحاجة إلى باركود بسيط (بدون مجموع تحقق)، اضبط خيار مجموع التحقق على `Default`. هذا مفيد للأنظمة القديمة التي لا تتوقع رقمًا إضافيًا.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Default;
gen.Save($"{path}CodabarChecksumNone.png", BarCodeImageFormat.Png);
```

## الخطوة 3: توليد باركود Codabar مع مجموع تحقق **Mod10**

فعّل مجموع التحقق واختر خوارزمية Mod10. هذه هي وضعية مجموع التحقق الأكثر شيوعًا لرموز Codabar.

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod10;
gen.Save($"{path}CodabarChecksumMod10.png", BarCodeImageFormat.Png);
```

## الخطوة 4: توليد باركود Codabar مع مجموع تحقق **Mod16**

للتطبيقات التي تتطلب قدرة أعلى على اكتشاف الأخطاء، انتقل إلى Mod16. التغيير في الكود بسيط—فقط قم بتحديث `CodabarChecksumMode`.

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod16;
gen.Save($"{path}CodabarChecksumMod16.png", BarCodeImageFormat.Png);
```

بهذه الخطوات الأربعة البسيطة تعلمت **كيفية إضافة مجموع تحقق** إلى رموز الباركود Codabar وكيفية التبديل بين وضعيات Mod10 وMod16 باستخدام Aspose.BarCode لـ .NET.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|--------|-----|
| الصورة المولدة فارغة | `path` يشير إلى مجلد غير موجود | تأكد من وجود المجلد أو استخدم `Directory.CreateDirectory(path)` قبل الحفظ |
| لم يتم تطبيق مجموع التحقق | ترك `IsChecksumEnabled` على `Default` | اضبط `IsChecksumEnabled = EnableChecksum.Yes` قبل الحفظ |
| وضعية مجموع التحقق خاطئة | استخدام قيمة تعداد غير صحيحة | استخدم `CodabarChecksumMode.Mod10` أو `CodabarChecksumMode.Mod16` حسب الحاجة |

## الخلاصة

في هذا الدليل غطينا **كيفية إضافة مجموع تحقق** عند توليد باركود Codabar باستخدام Aspose.BarCode لـ .NET، وعرضنا وضعيات مجموع التحقق Mod10 وMod16، وأبرزنا لماذا تعتبر الباركودات المفعلة بمجموع تحقق ضرورية لسلامة البيانات. لا تتردد في تجربة سلاسل بيانات مختلفة واستكشاف مجموعة الخيارات الغنية لتخصيص الباركود التي يوفرها Aspose.

إذا واجهت أي صعوبات، فإن مجتمع Aspose.BarCode جاهز للمساعدة على [منتدى Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

## أسئلة شائعة

**س: هل يمكنني استخدام مجموع تحقق Mod16 لباركودات كتب المكتبة؟**  
**ج:** بالتأكيد. يوفر Mod16 كشفًا أقوى للأخطاء، وهو مفيد في بيئات ذات تدفق عالي مثل المكتبات.

**س: هل يؤثر تفعيل مجموع التحقق على سرعة المسح؟**  
**ج:** الرقم الإضافي يضيف وقت معالجة ضئيل؛ معظم القارئات تتعامل معه دون تأخير ملحوظ.

**س: كيف يمكنني التحقق من مجموع التحقق برمجيًا؟**  
**ج:** بعد توليد الباركود، يمكنك إعادة حساب مجموع التحقق باستخدام نفس `CodabarChecksumMode` ومقارنته بالحرف الأخير من السلسلة المشفرة.

**س: هل يمكن تخصيص مظهر رقم مجموع التحقق؟**  
**ج:** نعم. استخدم إعدادات مظهر `BarcodeGenerator` (مثل `BarHeight`، `ForeColor`) لتنسيق كامل الباركود، بما في ذلك رقم مجموع التحقق.

**س: ماذا لو احتجت إلى توليد عدة باركودات داخل حلقة؟**  
**ج:** أنشئ كائنًا واحدًا من `BarcodeGenerator`، وقم بتحديث خاصية `CodeText` لكل تكرار، ثم استدعِ `Save` مع اسم ملف فريد في كل مرة.

**آخر تحديث:** 2026-01-04  
**تم الاختبار مع:** Aspose.BarCode 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}