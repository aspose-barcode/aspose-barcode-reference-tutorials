---
date: 2026-03-07
description: تعلم كيفية إنشاء رمز شريطي EAN-13 مع بيانات إضافية في C# باستخدام Aspose.BarCode
  لـ .NET – أنشئ صورة PNG للرمز الشريطي بسرعة.
linktitle: Supplemental Barcode Data Configuration
second_title: Aspose.BarCode .NET API
title: إنشاء باركود EAN-13 مع بيانات إضافية – Aspose.BarCode
url: /ar/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء باركود EAN-13 مع بيانات إضافية – Aspose.BarCode for .NET

في هذا الدرس العملي ستقوم **بإنشاء باركود EAN-13** يتضمن بيانات إضافية EAN‑2 أو EAN‑5، وسترى كيف **تولّد ملفات PNG للباركود** ببضع أسطر فقط من C#. سواءً كنت تبني نظام دفع تجزئة، أو تطبيق لوجستي، أو أداة جرد بسيطة، فإن القدرة على إضافة معلومات إضافية تجعل الباركود أكثر فائدة.

## إجابات سريعة
- **ماذا يعني “البيانات الإضافية”؟** أرقام إضافية (EAN‑2/EAN‑5) تُطبع بجانب الباركود الرئيسي، غالبًا ما تُستخدم للسعر أو أرقام الإصدارات.  
- **ما نوع الباركود المستخدم؟** EAN‑13 كرمز أساسي، مع إضافات اختيارية EAN‑2 أو EAN‑5.  
- **هل يمكنني إخراج صور PNG؟** نعم – طريقة `Save` تسمح لك بالتصدير مباشرة إلى PNG.  
- **هل أحتاج إلى ترخيص للتطوير؟** نسخة تجريبية مجانية تكفي للاختبار؛ يتطلب الترخيص التجاري للإنتاج.  
- **هل هذا متوافق مع .NET Core / .NET 6؟** بالتأكيد – Aspose.BarCode يدعم جميع بيئات .NET الحديثة.

## المتطلبات المسبقة

قبل الغوص في الشيفرة، تأكد من أن لديك:

- Visual Studio (أو أي بيئة تطوير متوافقة مع .NET).  
- نسخة من Aspose.BarCode for .NET – حمّلها **[هنا](https://releases.aspose.com/barcode/net/)**.  
- معرفة أساسية بـ C#.  
- مجلد قابل للكتابة حيث سيتم حفظ ملفات PNG المُولدة.

## استيراد مساحات الأسماء

أولاً، أضف مساحة الأسماء Aspose.BarCode حتى تتمكن من الوصول إلى فئات المولد:

```csharp
using Aspose.BarCode.Generation;
```

> **نصيحة احترافية:** إذا كنت تستخدم .NET Core، أضف حزمة NuGet `Aspose.BarCode` إلى مشروعك بدلاً من الإشارة إلى ملف DLL يدويًا.

## ما هو الباركود الإضافي؟

الباركود الإضافي هو سلسلة رقمية مساعدة تُطبع بجانب الباركود الرئيسي.

- **EAN‑2** – ملحق من رقمين، غالبًا ما يُستخدم لأرقام الإصدارات في المجلات.  
- **EAN‑5** – ملحق من خمسة أرقام، يُستخدم عادةً لإضافات السعر على المنتجات التجزئة.

إضافة هذه الملحقات لا تغير البيانات الأساسية لـ EAN‑13؛ بل توفر سياقًا إضافيًا يمكن للماسحات قراءته.

## لماذا نستخدم Aspose.BarCode للبيانات الإضافية؟

- **واجهة برمجة تطبيقات من سطر واحد** – قم بتكوين كل من الباركود الرئيسي وملحقه في كائن واحد.  
- **تحكم كامل في الأبعاد** – ضبط بعد X، مسافة الملحق، وتنسيق الصورة.  
- **متعدد المنصات** – يعمل على .NET Framework، .NET Core، و .NET 5/6+.  

## دليل خطوة بخطوة

### الخطوة 1: إعداد دليل الإخراج

حدد مكان حفظ ملفات PNG. استبدل العنصر النائب بمسار حقيقي على جهازك.

```csharp
string path = "Your Directory Path";
```

### الخطوة 2: تهيئة مولد الباركود (Barcode Generator C#)

أنشئ مثيلًا من `BarcodeGenerator`، مع تحديد **EAN‑13** كنوع رئيسي وتوفير الحمولة المكونة من 13 رقمًا.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

### الخطوة 3: تعديل أبعاد الباركود

قم بضبط الحجم البصري للباركود والمسافة المخصصة للملحق بدقة.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

### الخطوة 4: إضافة ملحق EAN‑2

عيّن البيانات الإضافية إلى قيمة مكوّنة من رقمين (مثال: “12”). سيظهر ذلك إلى يمين الباركود الرئيسي.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

### الخطوة 5: حفظ باركود EAN‑2 كملف PNG

صدّر الصورة. يضمن الوسيط `BarCodeImageFormat.Png` الحصول على ملف PNG عالي الجودة.

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

### الخطوة 6: التحويل إلى ملحق EAN‑5

غيّر قيمة `SupplementData` إلى سلسلة مكوّنة من خمسة أرقام لإضافات السعر.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

### الخطوة 7: حفظ باركود EAN‑5 كملف PNG

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

> **لماذا يعمل هذا:** يتم إعادة استخدام نفس مثيل `BarcodeGenerator`، لذا تحتاج فقط إلى تعديل خاصية `SupplementData` قبل كل استدعاء `Save`. هذا يبقي الشيفرة مختصرة ويتجنب إنشاء كائنات غير ضرورية.

## المشكلات الشائعة والنصائح

- **مسار دليل غير صالح** – تأكد من وجود المجلد وأن التطبيق يمتلك أذونات الكتابة.  
- **طول الملحق غير صحيح** – EAN‑2 يتطلب بالضبط رقمين، وEAN‑5 يتطلب 5 أرقام؛ وإلا سيتم رمي استثناء.  
- **الصورة غير مرئية** – تحقق من استخدام `BarCodeImageFormat.Png`؛ قد تتسبب الصيغ الأخرى (مثل JPEG) في تشويه الضغط الذي يؤثر على قابلية القراءة بالماسحات.  

## الأسئلة المتكررة

### هل يمكنني استخدام Aspose.BarCode for .NET في مشروع .NET Core الخاص بي؟
نعم، Aspose.BarCode for .NET متوافق بالكامل مع .NET Core، .NET 5، و .NET 6.

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.BarCode for .NET؟
نعم، يمكنك تجربتها مجانًا بزيارة **[هذا الرابط](https://releases.aspose.com/)**.

### من أين يمكنني الحصول على ترخيص مؤقت لـ Aspose.BarCode for .NET؟
يمكنك الحصول على ترخيص مؤقت من **[هذا الرابط](https://purchase.aspose.com/temporary-license/)**.

### هل يدعم Aspose.BarCode مجموعة واسعة من أنواع الباركود؟
بالطبع – يدعم EAN‑13، QR Code، Code 128، DataMatrix، PDF‑417، والعديد غيرها.

### هل يمكنني تخصيص مظهر الباركود المُولد؟
نعم، يمكنك تعديل الألوان، الخطوط، الهوامش، وحتى إضافة صور خلفية باستخدام واجهة برمجة التطبيقات الواسعة `Parameters`.

## الخلاصة

أنت الآن تعرف كيف **تنشئ باركود EAN-13** مع بيانات إضافية EAN‑2 أو EAN‑5 و**تولّد ملفات PNG للباركود** باستخدام Aspose.BarCode for .NET. يمنحك هذا النهج تحكمًا كاملاً في أبعاد الباركود، مسافة الملحق، وتنسيق الإخراج، مما يجعله مثاليًا للتجزئة، اللوجستيات، وأي سيناريو يتطلب معلومات رقمية إضافية.

للتعمق أكثر، اطلع على دليل المرجع الكامل: **[توثيق Aspose.BarCode for .NET](https://reference.aspose.com/barcode/net/)**.

---

**آخر تحديث:** 2026-03-07  
**تم الاختبار مع:** Aspose.BarCode 24.11 for .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}