---
title: قم بإنشاء باركود DataMatrix باستخدام Aspose.BarCode لـ .NET
linktitle: إصدارات داتا ماتريكس
second_title: Aspose.BarCode .NET API
description: تعرف على كيفية إنشاء رموز شريطية DataMatrix في .NET باستخدام Aspose.BarCode لـ .NET. الأبعاد المخصصة ودعم ECC والمزيد.
weight: 12
url: /ar/net/datamatrix-barcode-reading/datamatrix-versions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قم بإنشاء باركود DataMatrix باستخدام Aspose.BarCode لـ .NET

إذا كنت تبحث عن حل موثوق لإنشاء رموز شريطية DataMatrix في تطبيقات .NET الخاصة بك، فإن Aspose.BarCode for .NET هو الحل الأمثل. في هذا الدليل المفصّل خطوة بخطوة، سنرشدك خلال عملية استخدام Aspose.BarCode لـ .NET لإنشاء رموز DataMatrix الشريطية. سنقوم بتقسيم كل مثال إلى خطوات متعددة، مما يضمن أنه يمكنك المتابعة بسهولة.

## المتطلبات الأساسية

قبل أن نتعمق في الكود، تأكد من توفر المتطلبات الأساسية التالية:
- بيئة تطوير بدعم .NET.
-  نسخة من Aspose.BarCode for .NET، والتي يمكنك تنزيلها من[هذا الرابط](https://releases.aspose.com/barcode/net/).
- المعرفة الأساسية بـ C# وإطار عمل .NET.

الآن، دعنا نستكشف إصدارات DataMatrix وكيفية إنشائها باستخدام Aspose.BarCode لـ .NET.

## استيراد مساحات الأسماء

في أي مشروع C#، من الضروري استيراد مساحات الأسماء الضرورية. في حالة Aspose.BarCode، ستحتاج إلى تضمين ما يلي:

```csharp
using Aspose.BarCode.Generation;
```

 توفر مساحة الاسم هذه الوصول إلى`BarcodeGenerator` فئة، وهو أمر بالغ الأهمية لتوليد الباركود.

الآن، دعونا نقسم المثال إلى خطوات متعددة.

## الخطوة 1: إعداد مسار الدليل الخاص بك

ابدأ بتحديد مسار الدليل حيث تريد حفظ الرموز الشريطية DataMatrix التي تم إنشاؤها.

```csharp
string path = "Your Directory Path";
```

 يستبدل`"Your Directory Path"` بالمسار الفعلي الذي تريد حفظ صور الباركود فيه.

## الخطوة 2: تهيئة مولد الباركود

 إنشاء مثيل لـ`BarcodeGenerator` فئة وتحديد نوع الباركود كما`DataMatrix`. يمكنك أيضًا تقديم البيانات التي تريد تشفيرها داخل الباركود.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // رمز إنشاء الباركود موجود هنا
}
```

## الخطوة 3: تكوين خصائص الرمز الشريطي

يمكنك تخصيص خصائص مختلفة للرمز الشريطي DataMatrix، مثل أبعاده ونوع ECC (رمز تصحيح الخطأ). فيما يلي مثال على ضبط البعد X على 4 بكسل واختيار ECC200:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4;
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

## الخطوة 4: قم بتعيين إصدار DataMatrix وحفظه

يمكنك تحديد إصدار DataMatrix عن طريق تحديد عدد الصفوف والأعمدة. بعد تكوين الإصدار، قم بحفظ صورة الباركود.

على سبيل المثال، لإنشاء رمز شريطي DataMatrix يحتوي على 22 صفًا و22 عمودًا باستخدام ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC200_22x22;
generator.Save($"{path}DataMatrixRows22Columns22Ecc200.png", BarCodeImageFormat.Png);
```

وبالمثل، يمكنك إنشاء رمز شريطي بمعلمات مختلفة عن طريق تغيير الإصدار ونوع تصحيح الأخطاء (ECC) حسب الحاجة.

## الخطوة 5: كرر للإصدارات الأخرى

يمكنك تكرار الخطوة 4 لإصدارات DataMatrix الأخرى. على سبيل المثال، لإنشاء باركود مكون من 12 صفًا و64 عمودًا باستخدام ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.DMRE_12x64;
generator.Save($"{path}DataMatrixRows12Columns64Ecc200.png", BarCodeImageFormat.Png);
```

## الخطوة 6: تبديل أنواع ECC

إذا كنت تريد تغيير نوع ECC إلى Ecc140، فيمكنك القيام بذلك عن طريق تحديث خاصية ECC:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;
```

## الخطوة 7: إنشاء رموز شريطية بإصدارات مختلفة ورمز تصحيح الأخطاء (ECC).

كرر الخطوة 4 لإصدارات DataMatrix وأنواع ECC الأخرى، مع حفظ كل رمز شريطي باسم ملف فريد.

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC000_140_29x29;
generator.Save($"{path}DataMatrixRows29Columns29Ecc140.png", BarCodeImageFormat.Png);
```

الآن بعد أن تعلمت كيفية إنشاء رموز شريطية DataMatrix باستخدام Aspose.BarCode لـ .NET، يمكنك بسهولة دمج هذه الوظيفة في تطبيقات .NET الخاصة بك.

## خاتمة

يعمل Aspose.BarCode for .NET على تبسيط عملية إنشاء رموز شريطية DataMatrix في تطبيقات .NET الخاصة بك. باستخدام هذا الدليل التفصيلي، يمكنك إنشاء رموز شريطية بإصدارات مختلفة وأنواع ECC، مما يوفر المرونة والتخصيص لتلبية احتياجاتك الخاصة.

 إذا كان لديك أي أسئلة أو كنت بحاجة إلى المساعدة، فلا تتردد في زيارة[Aspose.BarCode لوثائق .NET](https://reference.aspose.com/barcode/net/) أو تحقق من[منتدى Aspose.BarCode](https://forum.aspose.com/c/barcode/13) للدعم.

## الأسئلة الشائعة

### س1: ما هو ECC في باركود DataMatrix؟

A1: يعد ECC (رمز تصحيح الخطأ) مكونًا حيويًا للرموز الشريطية DataMatrix التي تساعد على ضمان تكامل البيانات. توفر مستويات ECC المختلفة درجات متفاوتة من تصحيح الأخطاء.

### س2: هل يمكنني إنشاء رموز شريطية لـ DataMatrix بأبعاد مخصصة باستخدام Aspose.BarCode لـ .NET؟

ج2: نعم، يمكنك تخصيص أبعاد باركود DataMatrix عن طريق تعيين عدد الصفوف والأعمدة كما هو موضح في البرنامج التعليمي.

### س3: أين يمكنني تنزيل Aspose.BarCode لـ .NET؟

 ج3: يمكنك تنزيل Aspose.BarCode لـ .NET من[هذا الرابط](https://releases.aspose.com/barcode/net/).

### س4: هل تتوفر نسخة تجريبية مجانية من Aspose.BarCode لـ .NET؟

 ج4: نعم، يمكنك الوصول إلى الإصدار التجريبي المجاني من Aspose.BarCode لـ .NET[هنا](https://releases.aspose.com/).

### س5: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.BarCode لـ .NET؟

 ج5: للحصول على ترخيص مؤقت لـ Aspose.BarCode لـ .NET، قم بزيارة[هذا الرابط](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
