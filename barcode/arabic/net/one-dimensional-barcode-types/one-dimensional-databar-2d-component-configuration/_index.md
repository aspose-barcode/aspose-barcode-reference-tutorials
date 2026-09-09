---
date: 2026-02-28
description: تعلم كيفية إنشاء مولد الباركود Aspose لباركود Databar أحادي البعد وثنائي
  الأبعاد في .NET. اتبع دليلنا خطوة بخطوة للإعداد والتخصيص.
linktitle: One-Dimensional Databar 2D Component Configuration
second_title: Aspose.BarCode .NET API
title: إنشاء مولد الباركود Aspose – إعداد Databar ثنائي الأبعاد
url: /ar/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تكوين مكوّن Databar ثنائي الأبعاد أحادي البُعد

في هذا البرنامج التعليمي ستقوم **بإنشاء مولّد باركود Aspose** لمكوّن Databar ثنائي الأبعاد أحادي البُعد باستخدام مكتبة Aspose.BarCode .NET. سواءً كنت تبني ملصقات تجزئة، بطاقات جرد، أو أي تطبيق يحتاج إلى بيانات مدمجة وعالية الكثافة، يرشّحك هذا الدليل عبر كل خطوة—من إعداد المشروع إلى حفظ الصور النهائية بصيغة PNG.

## إجابات سريعة
- **ماذا يفعل علم المكوّن ثنائي الأبعاد؟** يحدد للمولّد ما إذا كان سيضمّ رمزًا مركّبًا ثنائي الأبعاد داخل باركود Databar.  
- **هل يمكنني تغيير البُعد X؟** نعم، الخاصية `XDimension.Pixels` تتحكم في عرض الوحدة.  
- **ما صيغة الصورة المستخدمة في المثال؟** PNG، عبر `BarCodeImageFormat.Png`.  
- **هل أحتاج إلى ترخيص للتطوير؟** نسخة تجريبية مجانية تكفي للاختبار؛ يتطلب الترخيص التجاري للإنتاج.  
- **هل الكود متوافق مع .NET Core؟** بالتأكيد—Aspose.BarCode يدعم .NET Framework و .NET Core.

## ما هو مكوّن Databar ثنائي الأبعاد أحادي البُعد؟
مكوّن Databar ثنائي الأبعاد يجمع بين باركود خطي تقليدي ورمز مركّب صغير ثنائي الأبعاد، مما يتيح لك تخزين معلومات إضافية (مثل عنوان URL أو حقول بيانات أخرى) دون زيادة حجم الباركود الكلي.

## لماذا نستخدم Aspose.BarCode لهذا المهمة؟
- **تكامل كامل مع .NET** – يعمل بسلاسة مع مشاريع C#.  
- **واجهة برمجة تطبيقات غنية** – تعديل الأبعاد، تمكين/تعطيل المكوّن ثنائي الأبعاد، واختيار من بين العديد من صيغ الإخراج.  
- **بدون تبعيات خارجية** – المكتبة مكتفية ذاتيًا، مما يجعل النشر بسيطًا.

## المتطلبات المسبقة

1. **التثبيت** – تأكد من تثبيت Aspose.BarCode لـ .NET. حمّله من الموقع [هنا](https://releases.aspose.com/barcode/net/).  
2. **معرفة أساسية** – الإلمام بـ C# وتطوير .NET سيساعدك على متابعة الخطوات.  
3. **بيئة التطوير** – Visual Studio، Rider، أو أي محرر يدعم C#.

مع تغطية هذه الأساسيات، لنبدأ بتكوين مكوّن Databar ثنائي الأبعاد.

## استيراد المساحات الاسمية

أول شيء تحتاج إلى فعله هو استيراد مساحة الاسم Aspose.BarCode لتتمكن من الوصول إلى فئاتها.

```csharp
using Aspose.BarCode;
```

## تحديد مسار الإخراج

حدد أين سيتم حفظ صور الباركود التي تم إنشاؤها على نظام الملفات الخاص بك.

```csharp
string path = "Your Directory Path";
```

استبدل `"Your Directory Path"` بمسار مجلد فعلي على جهازك.

## إنشاء مولّد باركود

أنشئ كائن `BarcodeGenerator` بنوع Databar Expanded وقدم البيانات التي تريد ترميزها.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

يمكنك استبدال البيانات النموذجية بمعرف تطبيق GS1 الخاص بك أو أي حمولة أخرى.

## كيفية إنشاء مولّد باركود Aspose لمكوّن Databar أحادي البُعد ثنائي الأبعاد

الآن قم بتكوين الخصائص البصرية وعلم المكوّن ثنائي الأبعاد، ثم احفظ الصور.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;

// Disable 2D component flag
gen.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
gen.Save($"{path}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);

// Enable 2D component flag
gen.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
gen.Save($"{path}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

- **XDimension** يتحكم في عرض كل وحدة من الباركود.  
- ضبط `Is2DCompositeComponent` إلى **false** ينتج Databar خطيًا نقيًا.  
- ضبطه إلى **true** يضيف الرمز المركّب ثنائي الأبعاد، وهو مفيد لترميز بيانات إضافية.

## المشكلات الشائعة والنصائح

- **مسار غير صالح** – تأكد من وجود المجلد وأن التطبيق يملك صلاحيات الكتابة.  
- **استثناء الترخيص** – إذا ظهرت رسالة تحذير ترخيص، قم بتطبيق ترخيص Aspose قبل إنشاء الباركود.  
- **الصورة غير مرئية** – تحقق من أن `BarCodeImageFormat` يتطابق مع امتداد الملف الذي تستخدمه.

## الخلاصة

لقد تعلمت الآن كيفية **إنشاء مولّد باركود Aspose** لمكوّن Databar أحادي البُعد ثنائي الأبعاد، مع تبديل علم المكوّن ثنائي الأبعاد وضبط البُعد X. يتيح لك هذا النهج المرن تعديل الباركود ليتناسب مع مجموعة واسعة من السيناريوهات التجارية. لمزيد من التخصيص المتعمق، استكشف وثائق Aspose.BarCode الكاملة: [توثيق Aspose.BarCode لـ .NET](https://reference.aspose.com/barcode/net/).

إذا احتجت إلى المزيد من الأمثلة أو واجهت تحديات، فإن مجتمع Aspose مكان رائع لطرح الأسئلة.

## الأسئلة المتكررة

### هل Aspose.BarCode لـ .NET متوافق مع أنواع الباركود المختلفة؟
- نعم، يدعم Aspose.BarCode لـ .NET مجموعة واسعة من أنواع الباركود، مما يجعله متعدد الاستخدامات لتطبيقات مختلفة.

### هل يمكنني تخصيص مظهر الباركود المُولد؟
- بالتأكيد! يمكنك تعديل حجم الباركود، لونه، والعديد من الخصائص البصرية الأخرى لتناسب احتياجاتك.

### هل هناك خيارات ترخيص متاحة لـ Aspose.BarCode لـ .NET؟
- نعم، تقدم Aspose خيارات ترخيص لتلبية متطلبات مختلفة. يمكنك استكشافها على الموقع الإلكتروني.

### هل Aspose.BarCode مناسب للمبتدئين والمطورين ذوي الخبرة؟
- تم تصميم Aspose.BarCode ليكون سهل الاستخدام، مما يجعله مناسبًا لكل من المبتدئين والمطورين ذوي الخبرة.

### أين يمكنني الحصول على الدعم والمساعدة بشأن Aspose.BarCode لـ .NET؟
- يمكنك طلب المساعدة والتفاعل مع المجتمع في [منتدى دعم Aspose.BarCode لـ .NET](https://forum.aspose.com/c/barcode/13).

## أسئلة شائعة

**س: هل يمكنني توليد باركود بصيغ غير PNG؟**  
ج: نعم، تدعم طريقة `Save` صيغ BMP، JPEG، GIF، TIFF، وغيرها عبر تحديد `BarCodeImageFormat` المناسب.

**س: كيف أطبق لونًا مخصصًا على الباركود؟**  
ج: استخدم `gen.Parameters.Barcode.ForeColor` و `gen.Parameters.Barcode.BackColor` لتحديد ألوان المقدمة والخلفية.

**س: هل يمكن تضمين شعار داخل صورة الباركود؟**  
ج: توفر Aspose.BarCode خاصية `Image` حيث يمكنك وضع شعار فوق الباركود بعد توليده.

**س: ما إصدارات .NET المدعومة؟**  
ج: تعمل المكتبة مع .NET Framework 4.5+، .NET Core 3.1+، .NET 5+، و .NET 6+.

**س: كيف يمكن تحسين موثوقية القراءة للطباعة منخفضة الدقة؟**  
ج: زيادة قيمة `XDimension` وضمان تباين كافٍ بين الباركود والخلفية.

---

**آخر تحديث:** 2026-02-28  
**تم الاختبار مع:** Aspose.BarCode 24.12 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}