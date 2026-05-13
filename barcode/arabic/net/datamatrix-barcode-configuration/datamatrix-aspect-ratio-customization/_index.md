---
date: 2026-01-12
description: تعلم كيفية إنشاء صورة PNG للباركود بنسبة أبعاد مخصصة لـ DataMatrix باستخدام
  Aspose.BarCode لـ .NET. دليل خطوة بخطوة لإنشاء الباركود وتخصيص الحجم.
linktitle: DataMatrix Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
title: إنشاء باركود PNG – نسبة أبعاد DataMatrix – Aspose.BarCode
url: /ar/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء صورة باركود PNG – نسبة أبعاد DataMatrix – Aspose.BarCode

إنشاء **صورة باركود PNG** بنسبة أبعاد DataMatrix مخصصة هو طلب شائع عندما تحتاج إلى أن يتناسب الباركود مع قيود تخطيطية محددة. في هذا الدرس سنستعرض الخطوات الدقيقة **لإنشاء ملفات باركود PNG** باستخدام Aspose.BarCode لـ .NET، نشرح لماذا قد ترغب في تعديل نسبة الأبعاد، ونظهر لك كيفية ضبط الناتج بدقة لتطبيقك.

## إجابات سريعة
- **ماذا يتحكم فيه “نسبة الأبعاد”؟** يحدد نسبة العرض إلى الارتفاع لوحدات DataMatrix.  
- **هل يمكنني إخراج PNG أو JPEG أو SVG؟** نعم – تدعم طريقة `Save` PNG و JPEG و BMP و GIF وغيرها.  
- **هل أحتاج إلى ترخيص لهذه الميزة؟** النسخة التجريبية المجانية تكفي للتطوير؛ الترخيص الكامل مطلوب للإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.x، .NET Core 3.1+، .NET 5/6/7.  
- **كم عدد قيم نسبة الأبعاد الصالحة؟** أي عدد عشري موجب؛ القيم الشائعة تتراوح بين 0.5 – 2.0.

## ما هو باركود DataMatrix ولماذا نضبط نسبة أبعاده؟
DataMatrix هو باركود مصفوفة ثنائية الأبعاد يخزن كميات كبيرة من البيانات في مساحة صغيرة. ضبط **نسبة الأبعاد** يسمح لك بتمديد أو ضغط الوحدات أفقياً، وهو ما يمكن أن يكون مفيداً لتناسب الباركود في أعمدة ضيقة أو ملصقات عريضة دون التضحية بقراءة الباركود.

## المتطلبات المسبقة

قبل أن نبدأ بتخصيص نسب أبعاد DataMatrix، تأكد من توفر المتطلبات التالية:

1. **Visual Studio** – أي نسخة حديثة ستفي بالغرض.  
2. **Aspose.BarCode لـ .NET** – حمّله من [هنا](https://releases.aspose.com/barcode/net/).  
3. **.NET Framework / .NET Core** – يجب أن يستهدف مشروعك نسخة مدعومة.

## استيراد مساحات الأسماء

أولاً، تحتاج إلى استيراد مساحة الأسماء الضرورية في مشروع C# الخاص بك:

```csharp
using Aspose.BarCode.Generation;
```

> **نصيحة احترافية:** احتفظ بعبارة `using` هذه في أعلى ملفك لتكون فئة `BarcodeGenerator` متاحة دائماً.

## دليل خطوة بخطوة

### الخطوة 1: إعداد المشروع
أنشئ مشروع وحدة تحكم (Console) أو Windows Forms جديد في Visual Studio وأضف مرجعاً إلى مكتبة Aspose.BarCode DLL.

### الخطوة 2: تهيئة مولّد الباركود
قم بإنشاء كائن `BarcodeGenerator` من نوع DataMatrix والبيانات التي تريد ترميزها:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> هذا السطر ينشئ مولّداً جاهزاً لإنتاج باركود DataMatrix يحتوي على النص التجريبي.

### الخطوة 3: تخصيص نسبة الأبعاد وحفظ ملفات PNG
الآن يمكنك تعديل **نسبة الأبعاد** وحفظ كل نسخة كصورة PNG:

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- الاستدعاء الأول ينتج باركود بنسبة أبعاد مربعة (`AspectRatio = 1`).  
- الاستدعاء الثاني يضغط الباركود أفقياً (`AspectRatio = 0.5`)، مما يعطي مظهرًا أوسع.

الآن لديك ملفا **باركود PNG** بنسب أبعاد مختلفة جاهزين للاستخدام في التقارير أو الملصقات أو عناصر واجهة المستخدم.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **الصورة الناتجة غير واضحة** | زد قيمة معامل `Resolution` قبل الحفظ (`gen.Parameters.ImageResolution = 300`). |
| **الباركود لا يُمسح** | تأكد من أن نسبة الأبعاد تبقى بين 0.5 – 2.0 واحرص على وجود مساحة هادئة كافية (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **أخطاء في مسار الملف** | استخدم `Path.Combine` لتكوين مسار الإخراج وتأكد من وجود المجلد. |

## الأسئلة المتكررة

**س: هل يمكنني تخصيص نسبة أبعاد أنواع باركود أخرى باستخدام Aspose.BarCode لـ .NET؟**  
ج: نعم، العديد من الباركودات ثنائية الأبعاد (مثل QR، PDF417) تدعم تعديل نسبة الأبعاد عبر كائنات المعاملات الخاصة بها.

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.BarCode لـ .NET؟**  
ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.BarCode لـ .NET [هنا](https://releases.aspose.com/).

**س: أين يمكنني شراء ترخيص لـ Aspose.BarCode لـ .NET؟**  
ج: يمكنك شراء الترخيص من موقع Aspose [هنا](https://purchase.aspose.com/buy).

**س: هل Aspose.BarCode لـ .NET متوافق مع إصدارات .NET Framework المختلفة؟**  
ج: نعم، يعمل مع .NET Framework 4.x، .NET Core 3.1+، وأحدث إصدارات .NET.

**س: هل يمكنني توليد باركود بصيغ مختلفة باستخدام Aspose.BarCode لـ .NET؟**  
ج: بالتأكيد – PNG، JPEG، BMP، GIF، TIFF، SVG، و PDF كلها مدعومة مباشرة.

## الخلاصة

تخصيص **نسبة أبعاد** باركود DataMatrix و**إنشاء ملفات باركود PNG** أمر سهل مع Aspose.BarCode لـ .NET. باتباع الخطوات أعلاه، يمكنك توليد باركود بأحجام مثالية تلبي متطلبات التخطيط الدقيقة لمشروعك. استكشف معلمات أخرى مثل `Resolution` و `Margin` و `Color` لتخصيص الناتج أكثر.

لمزيد من الاستكشاف، راجع [التوثيق الرسمي](https://reference.aspose.com/barcode/net/) أو انضم إلى المجتمع في [منتدى Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**آخر تحديث:** 2026-01-12  
**تم الاختبار مع:** Aspose.BarCode 24.12 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}