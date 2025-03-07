---
title: إنشاء بيانات باركود تكميلية باستخدام Aspose.BarCode لـ .NET
linktitle: تكوين بيانات الباركود التكميلي
second_title: Aspose.BarCode .NET API
description: قم بإنشاء بيانات باركود تكميلية باستخدام Aspose.BarCode لـ .NET. قم بتخصيص الرموز الشريطية EAN-2 وEAN-5 بسهولة. دليل خطوة بخطوة لمطوري .NET.
weight: 10
url: /ar/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء بيانات باركود تكميلية باستخدام Aspose.BarCode لـ .NET


في عالم إنشاء الباركود وتخصيصه، يبرز Aspose.BarCode for .NET كأداة قوية ومتعددة الاستخدامات. سواء كنت مطورًا ذا خبرة أو بدأت للتو، سيرشدك هذا الدليل خطوة بخطوة خلال عملية تكوين بيانات الرمز الشريطي الإضافية باستخدام Aspose.BarCode for .NET. 

## المتطلبات الأساسية

قبل أن نتعمق في عالم بيانات الباركود الإضافية، تأكد من توفر المتطلبات الأساسية التالية:

- بيئة تطوير تم إعدادها باستخدام Visual Studio أو أي أداة تطوير .NET أخرى.
-  نسخة من Aspose.BarCode لـ .NET. إذا لم تكن قد قمت بذلك بالفعل، يمكنك تنزيله[هنا](https://releases.aspose.com/barcode/net/).
- المعرفة الأساسية ببرمجة C#.
- دليل حيث يمكنك حفظ صور الباركود التي تم إنشاؤها.

## استيراد مساحات الأسماء

أولاً، تأكد من أن لديك مساحات الأسماء الضرورية المضمنة في كود C# الخاص بك للعمل مع Aspose.BarCode لـ .NET. قم باستيراد مساحات الأسماء المطلوبة في بداية ملف C# الخاص بك:

```csharp
using Aspose.BarCode.Generation;
```

الآن، دعونا نقسم عملية تكوين بيانات الباركود الإضافية إلى خطوات متعددة.

## الخطوة 1: إعداد مسار الدليل

 في كود C# الخاص بك، حدد المسار إلى الدليل الذي تريد حفظ صور الباركود التي تم إنشاؤه فيه. يستبدل`"Your Directory Path"` مع مسار الدليل الفعلي الخاص بك.

```csharp
string path = "Your Directory Path";
```

## الخطوة 2: إنشاء مولد الباركود

 إنشاء مثيل ل`BarcodeGenerator` من خلال تحديد نوع الباركود والبيانات التي تريد تشفيرها. في هذا المثال، نستخدم الرمز الشريطي EAN-13 مع البيانات "1234567890128".

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

## الخطوة 3: تخصيص أبعاد الباركود

قم بتعيين أبعاد الباركود، مثل البعد X (عرض أصغر عنصر في الباركود) والمساحة الإضافية. في هذا المثال، قمنا بتعيين البعد X على 2 بكسل والمساحة الإضافية على 20 بكسل.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

## الخطوة 4: تكوين ملحق EAN-2

لتكوين رمز شريطي إضافي EAN-2، اضبط البيانات الإضافية على القيمة المطلوبة. في هذه الحالة، قمنا بتعيينه على "12". 

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

## الخطوة 5: حفظ صورة الباركود

احفظ صورة الباركود التي تم إنشاؤها في الدليل المحدد الخاص بك باسم ذي معنى. في هذا المثال، نقوم بحفظ الرمز الشريطي الإضافي EAN-2 باسم "SupplementEAN2.png".

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

## الخطوة 6: تكوين ملحق EAN-5

 لتكوين رمز شريطي إضافي EAN-5، ما عليك سوى تغيير`SupplementData` إلى القيمة التي تريدها. هنا، قمنا بضبطه على "12345".

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

## الخطوة 7: حفظ صورة الرمز الشريطي (EAN-5)

وأخيرًا، احفظ صورة الرمز الشريطي التكميلي EAN-5 في الدليل المحدد لديك. في هذه الحالة، نقوم بحفظه باسم "SuplementEAN5.png".

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

لقد نجحت الآن في تكوين وإنشاء بيانات باركود تكميلية باستخدام Aspose.BarCode لـ .NET. يمكنك استخدام هذا الأسلوب لإنشاء مجموعة واسعة من أنواع الباركود مع بيانات تكميلية مختلفة.

## خاتمة

يعد Aspose.BarCode for .NET أداة قوية لإنشاء الباركود وتخصيصه. في هذا الدليل، تناولنا عملية تكوين وإنشاء بيانات الباركود الإضافية خطوة بخطوة. مع المتطلبات الأساسية الصحيحة والقليل من الترميز، يمكنك العمل بكفاءة مع بيانات الباركود وتلبية احتياجاتك الخاصة.

 لمزيد من المعلومات والاستخدام المتقدم، راجع[Aspose.BarCode لوثائق .NET](https://reference.aspose.com/barcode/net/).

## أسئلة مكررة

### هل يمكنني استخدام Aspose.BarCode لـ .NET في مشروع .NET Core الخاص بي؟
نعم، Aspose.BarCode for .NET متوافق مع .NET Core.

### هل تتوفر نسخة تجريبية مجانية من Aspose.BarCode لـ .NET؟
 نعم يمكنك تجربتها مجاناً من خلال زيارتنا[هذا الرابط](https://releases.aspose.com/).

### أين يمكنني الحصول على ترخيص مؤقت لـ Aspose.BarCode لـ .NET؟
 يمكنك الحصول على ترخيص مؤقت من[هذا الرابط](https://purchase.aspose.com/temporary-license/).

### هل يدعم Aspose.BarCode مجموعة واسعة من أنواع الباركود؟
نعم، فهو يدعم أنواع مختلفة من الباركود، بما في ذلك EAN-13، وQR Code، وCode 128، والمزيد.

### هل يمكنني تخصيص مظهر الباركود الذي تم إنشاؤه؟
بالتأكيد، يمكنك تخصيص الأبعاد والألوان والجوانب الأخرى للرموز الشريطية لتلبية متطلباتك.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
