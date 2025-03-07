---
title: تكوين ذو نسبة واسعة وضيقة أحادية البعد
linktitle: تكوين ذو نسبة واسعة وضيقة أحادية البعد
second_title: Aspose.BarCode .NET API
description: قم بإنشاء رموز شريطية مخصصة بسهولة باستخدام Aspose.BarCode لـ .NET. دليل خطوة بخطوة لتكوين نسبة واسعة وضيقة أحادية البعد.
weight: 22
url: /ar/net/one-dimensional-barcode-types/one-dimensional-wide-narrow-ratio-configuration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تكوين ذو نسبة واسعة وضيقة أحادية البعد


هل تتطلع إلى إنشاء رموز شريطية وتخصيصها بسهولة في تطبيقات .NET الخاصة بك؟ لا مزيد من البحث! Aspose.BarCode for .NET هي مكتبة قوية تجعل إنشاء الباركود وتخصيصه أمرًا سهلاً. في هذا الدليل التفصيلي، سنتعمق في كيفية تسخير قوة Aspose.BarCode لـ .NET لإنشاء رموز شريطية بتكوين نسبة واسعة وضيقة.

## المتطلبات الأساسية

قبل أن نتعمق في عالم الرموز الشريطية باستخدام Aspose.BarCode for .NET، يجب أن تتوفر لديك المتطلبات الأساسية التالية:

### 1. بيئة الاستوديو المرئي
   - تأكد من تثبيت Visual Studio على نظامك للعمل مع تطبيقات .NET.
   
### 2. Aspose.BarCode لمكتبة .NET
   -  يجب أن يكون لديك Aspose.BarCode لمكتبة .NET مثبتة. يمكنك تنزيله من[موقع إلكتروني](https://releases.aspose.com/barcode/net/).

### 3. مفتاح الترخيص (اختياري)
   -  إذا كان لديك مفتاح ترخيص، فيمكن استخدامه لفتح ميزات إضافية للمكتبة. يمكنك الحصول على ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/).

الآن بعد أن اكتملت المتطلبات الأساسية، دعنا ننتقل إلى إنشاء رموز شريطية أحادية البعد بتكوين نسبة عريضة وضيقة باستخدام Aspose.BarCode لـ .NET.

## استيراد مساحات الأسماء

أولاً، تحتاج إلى تضمين مساحات الأسماء الضرورية في مشروعك للوصول إلى ميزات Aspose.BarCode لـ .NET. يمكنك القيام بذلك عن طريق إضافة ما يلي باستخدام العبارات الموجودة أعلى الكود الخاص بك:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## الخطوة 1: تحديد مسار الدليل الخاص بك

ابدأ بتحديد المسار الذي تريد حفظ صور الباركود التي تم إنشاؤه فيه. يمكنك القيام بذلك باستخدام الكود التالي:

```csharp
string path = "Your Directory Path";
```

 يستبدل`"Your Directory Path"` باستخدام مسار الدليل الفعلي الذي تريد حفظ صور الباركود فيه.

## الخطوة 2: إنشاء باركود أحادي البعد ذو نسبة واسعة وضيقة

الآن، لنقم بإنشاء رمز شريطي أحادي البعد بتكوين نسبة عريضة وضيقة باستخدام Aspose.BarCode لـ .NET. في هذا المثال، سنستخدم نوع التشفير Code39Extending ونضبط البيانات على "ASPOSE".

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code39Extended, "ASPOSE");
```

يقوم سطر التعليمات البرمجية هذا بتهيئة مولد الباركود بنوع التشفير والبيانات المحددة.

## الخطوة 3: تعيين نسبة واسعة / ضيقة

تحدد النسبة الواسعة والضيقة النسبة بين العناصر العريضة والضيقة في الباركود. في هذه الخطوة، سنقوم بتعيين النسبة الواسعة والضيقة إلى 2:

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 2;
```

وبعد ذلك، سنقوم بحفظ صورة الباركود التي تم إنشاؤها في المسار المحدد:

```csharp
gen.Save($"{path}WideNarrow2Code39.png", BarCodeImageFormat.Png);
```

## الخطوة 4: ضبط النسبة الواسعة والضيقة

يمكنك تجربة نسب مختلفة واسعة وضيقة لتحقيق مظهر الباركود المطلوب. على سبيل المثال، إذا كنت تريد رمزًا شريطيًا أوسع، فاضبط نسبة العرض والضيق إلى 5:

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 5;
```

وحفظ صورة الباركود:

```csharp
gen.Save($"{path}WideNarrow5Code39.png", BarCodeImageFormat.Png);
```

لقد نجحت الآن في إنشاء رموز شريطية أحادية البعد بنسب مختلفة واسعة وضيقة باستخدام Aspose.BarCode لـ .NET. توفر لك هذه المكتبة المرونة اللازمة لإنشاء رموز شريطية مخصصة وفقًا لمتطلباتك المحددة.

## خاتمة

Aspose.BarCode for .NET هي مكتبة متعددة الاستخدامات تعمل على تبسيط عملية إنشاء الباركود وتخصيصه في تطبيقات .NET الخاصة بك. في هذا البرنامج التعليمي، قمنا بتغطية أساسيات إنشاء باركود أحادي البعد بتكوين نسبة واسعة وضيقة. من خلال القدرة على ضبط المعلمات المختلفة، يمكنك إنشاء رموز شريطية تناسب احتياجاتك تمامًا.

## أسئلة مكررة

### 1. كيف يمكنني الحصول على ترخيص Aspose.BarCode لـ .NET؟
 يمكنك شراء ترخيص من[موقع أسبوز](https://purchase.aspose.com/buy).

### 2. هل يمكنني استخدام Aspose.BarCode لـ .NET بدون ترخيص؟
نعم، يمكنك استخدامه بترخيص مؤقت يوفر وظائف محدودة.

### 3. هل يتوافق Aspose.BarCode for .NET مع .NET Core؟
نعم، Aspose.BarCode for .NET متوافق مع .NET Core و.NET Framework.

### 4. هل هناك أي قيود على أنواع الرموز الشريطية التي يمكنني إنشاؤها؟
يدعم Aspose.BarCode for .NET نطاقًا واسعًا من رموز الباركود، بما في ذلك QR Code وCode 39 وغير ذلك الكثير.

### 5. كيف يمكنني الحصول على الدعم أو طرح الأسئلة حول Aspose.BarCode for .NET؟
 يمكنك زيارة[منتدى Aspose.BarCode](https://forum.aspose.com/c/barcode/13) للدعم والمناقشات.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
