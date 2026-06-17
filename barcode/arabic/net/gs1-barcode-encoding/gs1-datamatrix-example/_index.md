---
date: 2026-02-22
description: تعلم كيفية إنشاء صورة الباركود باستخدام C# و Aspose.BarCode لـ .NET وتوليد
  باركودات GS1 DataMatrix بسرعة وكفاءة.
linktitle: GS1 DataMatrix Example
second_title: Aspose.BarCode .NET API
title: إنشاء صورة الباركود C# – مثال GS1 DataMatrix
url: /ar/net/gs1-barcode-encoding/gs1-datamatrix-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# مثال GS1 DataMatrix

إذا كنت تبحث عن طريقة موثوقة **create barcode image C#** في تطبيقات .NET الخاصة بك، فإن Aspose.BarCode for .NET يجعل العملية بسيطة. تدعم هذه المكتبة القوية مجموعة واسعة من الرموز، بما في ذلك GS1 DataMatrix، وتوفر API نظيف يتيح لك التركيز على منطق عملك بدلاً من تفاصيل الباركود منخفضة المستوى. خلال الدقائق القليلة القادمة، سنستعرض مثالًا كاملاً عمليًا يوضح لك كيفية إنشاء شريط GS1 DataMatrix، تخصيص مظهره، وحفظه كملف صورة.

## إجابات سريعة
- **ما الذي يولده المثال؟** شريط GS1 DataMatrix يحتوي على بيانات منتج نموذجية.  
- **ما المكتبة المستخدمة؟** Aspose.BarCode for .NET.  
- **هل يمكنني تغيير تنسيق الإخراج؟** نعم، يمكنك الحفظ بصيغة PNG أو JPEG أو BMP، إلخ.  
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تكفي للاختبار؛ يلزم ترخيص تجاري للإنتاج.  
- **هل الكود متوافق مع .NET Core؟** بالتأكيد – نفس الـ API يعمل على .NET Framework و .NET Core/5/6.

## ما هو شريط GS1 DataMatrix؟
GS1 DataMatrix هو شريط ثنائي الأبعاد يشفّر معلومات على مستوى المنتج (مثل GTIN، الرقم التسلسلي، ومعرفات التطبيقات الإضافية). يُستخدم على نطاق واسع في التجزئة، الرعاية الصحية، واللوجستيات لتخزين بيانات مضغوطة وعالية الكثافة.

## لماذا تستخدم Aspose.BarCode لإنشاء صورة باركود C#؟
- **API كامل المميزات** – يدعم معايير GS1، تصحيح الأخطاء، والتحكم في الحجم.  
- **بدون تبعيات خارجية** – مكتبة .NET صافية، سهلة التكامل.  
- **متعدد المنصات** – يعمل على Windows و Linux و macOS.  
- **توثيق شامل** – يتضمن أمثلة مثل هذا لتبدأ بسرعة.

## المتطلبات المسبقة

قبل أن نغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات التالية جاهزة:

1. **Aspose.BarCode for .NET** – تحتاج إلى تثبيت Aspose.BarCode for .NET. إذا لم تقم بذلك بعد، يمكنك [download it here](https://releases.aspose.com/barcode/net/).  
2. **بيئة التطوير** – يجب أن تكون لديك بيئة تطوير .NET مُعدة على نظامك (Visual Studio، VS Code، أو أي IDE تفضله).

الآن بعد أن أصبحت المتطلبات جاهزة، لنبدأ في إنشاء شفرات GS1 DataMatrix.

## استيراد مساحات الأسماء

أولاً، استورد مساحات الأسماء الضرورية للعمل مع Aspose.BarCode for .NET. هذه المساحات تمنحك الوصول إلى إمكانيات إنشاء الباركود.

```csharp
using Aspose.BarCode;
using System;
```

## كيفية إنشاء صورة باركود C# – دليل خطوة بخطوة

### الخطوة 1: إعداد مولد الباركود

للبدء، أنشئ كائن `BarcodeGenerator` وحدد رموز **GS1 DataMatrix** مع البيانات التي تريد ترميزها. في هذا المثال نُشفّر السلسلة **"(01)12345678901231(21)ASPOSE(30)9876"**، والتي تتبع تنسيق معرف التطبيق GS1.

```csharp
// The path to the documents directory.
string path = "Your Directory Path";
System.Console.WriteLine("Gs1DataMatrixExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1DataMatrix, "(01)12345678901231(21)ASPOSE(30)9876");
```

*نصيحة احترافية:* استبدل البيانات النموذجية بمعرفات GS1 الخاصة بك لتتناسب مع كتالوج منتجاتك.

### الخطوة 2: تخصيص خصائص الباركود

يمكنك تعديل مظهر الباركود باستخدام كائن `Parameters`. هنا نضبط البُعد X (حجم أصغر وحدة) إلى 8 بكسل، ونحدد حجم المصفوفة بـ 36 عمودًا × 12 صفًا. عدّل هذه القيم لتلبية متطلبات المسح الخاصة بك.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 8;
gen.Parameters.Barcode.DataMatrix.Columns = 36;
gen.Parameters.Barcode.DataMatrix.Rows = 12;
```

*لماذا تعديل X‑dimension؟* زيادة X‑dimension تجعل الباركود أسهل في القراءة على الأجهزة منخفضة الدقة، بينما قيمة أصغر تقلل حجم الصورة.

### الخطوة 3: حفظ صورة الباركود

أخيرًا، احفظ الباركود المُنشأ على القرص. يستخدم المثال PNG، لكن يمكنك الاختيار من JPEG، GIF، BMP، وغيرها من الصيغ المدعومة من قبل Aspose.BarCode.

```csharp
gen.Save($"{path}Gs1DataMatrixExample.png", BarCodeImageFormat.Png);
```

عند تشغيل الكود، ستجد **Gs1DataMatrixExample.png** في المجلد المحدد، جاهزًا للاستخدام في الملصقات، التغليف، أو التطبيقات الرقمية.

## حالات الاستخدام الشائعة
- **وسم منتجات التجزئة** – ترميز GTIN، أرقام الدفعات، وتواريخ الانتهاء.  
- **تتبع الأدوية** – تلبية المتطلبات التنظيمية باستخدام بيانات متوافقة مع GS1.  
- **لوجستيات المستودعات** – تخزين موقع المعلومات والمخزون بشكل مضغوط.

## استكشاف الأخطاء وإصلاحها والنصائح
- **تنسيق البيانات غير صحيح** – تأكد من أن السلسلة تتبع صيغة معرف التطبيق GS1؛ وإلا قد لا يكون الباركود قابلًا للمسح.  
- **مشكلات حجم الصورة** – إذا ظهرت الصورة غير واضحة، زد قيمة `XDimension.Pixels`.  
- **أخطاء الترخيص** – النسخة التجريبية صالحة للتقييم، لكن الترخيص الكامل مطلوب للنشر الإنتاجي.

## الأسئلة المتكررة

### ما هو GS1 DataMatrix؟
GS1 DataMatrix هو رمز شريطي ثنائي الأبعاد يُستخدم لتشفير بيانات متعلقة بالمنتجات وتحديد هويتها، خاصة في صناعات التجزئة والرعاية الصحية.

### هل Aspose.BarCode for .NET مناسب لأنواع أخرى من الباركود؟
نعم، يدعم Aspose.BarCode for .NET مجموعة واسعة من أنواع الباركود، مما يجعله متعدد الاستخدامات لتطبيقات مختلفة.

### هل يمكنني إنشاء باركود بصيغ صور أخرى غير PNG؟
نعم، يتيح لك Aspose.BarCode for .NET حفظ الباركود المُنشأ بصيغ صور متعددة مثل JPEG، GIF، و BMP، بالإضافة إلى PNG.

### هل أحتاج إلى ترخيص لاستخدام Aspose.BarCode for .NET؟
نعم، يلزم وجود ترخيص صالح للاستخدام التجاري لـ Aspose.BarCode for .NET. يمكنك الحصول على ترخيص من [Aspose website](https://purchase.aspose.com/buy).

### أين يمكنني الحصول على الدعم لـ Aspose.BarCode for .NET؟
يمكنك العثور على إجابات لأسئلتك وطلب الدعم في [Aspose.BarCode for .NET forum](https://forum.aspose.com/c/barcode/13).

## أسئلة إضافية (محسّنة بالذكاء الاصطناعي)

**س: كيف يمكنني إنشاء شريط DataMatrix في C# بدون تنسيق GS1؟**  
ج: استخدم `EncodeTypes.DataMatrix` بدلاً من `EncodeTypes.GS1DataMatrix` وقدم سلسلة البيانات العادية إلى `BarcodeGenerator`.

**س: هل يمكنني تغيير ألوان الباركود برمجيًا؟**  
ج: نعم، اضبط `gen.Parameters.Barcode.ForeColor` و `gen.Parameters.Barcode.BackColor` لتخصيص ألوان المقدمة والخلفية.

**س: هل من الممكن تضمين الباركود المُنشأ مباشرةً في ملف PDF؟**  
ج: بالتأكيد – استخرج الباركود ككائن `System.Drawing.Image` وأضفه إلى PDF باستخدام Aspose.PDF أو أي مكتبة PDF أخرى.

**س: ما إصدارات .NET المدعومة؟**  
ج: يدعم Aspose.BarCode for .NET .NET Framework 4.5+، .NET Core 3.1+، .NET 5، .NET 6، وما بعده.

**س: كيف يمكنني تحسين موثوقية المسح للملصقات الصغيرة؟**  
ج: زد البُعد X، أضف مناطق هادئة (`gen.Parameters.Barcode.Margin`)، وتأكد من وجود تباين كافٍ بين الباركود والخلفية.

## الخلاصة

في هذا البرنامج التعليمي، استكشفنا كيفية **create barcode image C#** باستخدام Aspose.BarCode for .NET لإنشاء شريط GS1 DataMatrix. ببضع أسطر من الكود فقط يمكنك دمج باركود عالي الجودة في تطبيقاتك، سواء كنت تبني حلول تجزئة، أنظمة رعاية صحية، أو منصات لوجستية. استكشف المكتبة أكثر لاكتشاف رموز إضافية، خيارات عرض متقدمة، وسيناريوهات تكامل مختلفة.

لمزيد من المعلومات والتوثيق التفصيلي، يرجى الرجوع إلى [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2026-02-22  
**تم الاختبار باستخدام:** Aspose.BarCode for .NET (latest version)  
**المؤلف:** Aspose