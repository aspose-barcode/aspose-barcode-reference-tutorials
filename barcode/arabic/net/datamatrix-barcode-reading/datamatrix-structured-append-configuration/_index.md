---
date: 2026-01-20
description: تعلم كيفية إنشاء باركود DataMatrix وفك تشفير باركود DataMatrix باستخدام
  تكوين الإلحاق الهيكلي في .NET باستخدام Aspose.BarCode لتنظيم البيانات بكفاءة عالية.
linktitle: DataMatrix Structured Append Configuration
second_title: Aspose.BarCode .NET API
title: كيفية إنشاء باركود DataMatrix مع Structured Append باستخدام Aspose.BarCode
  لـ .NET
url: /ar/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تكوين الإلحاق الهيكلي لـ DataMatrix باستخدام Aspose.BarCode لـ .NET

إذا كنت مطورًا يتطلع إلى **إنشاء رمز شريطي DataMatrix** مع تكوين الإلحاق الهيكلي في تطبيقات .NET الخاصة بك، فإن Aspose.BarCode لـ .NET هو الحل المثالي لك. في هذا الدليل خطوة بخطوة، سنستعرض إنشاء وقراءة هذه الرموز الشريطية، مقسمين كل مثال إلى أجزاء سهلة المتابعة حتى تتمكن من إتقان سير العمل بسرعة.

## إجابات سريعة
- **ما المكتبة التي يجب أن أستخدمها؟** Aspose.BarCode for .NET  
- **كم عدد أسطر الكود؟** حوالي 30 سطرًا لإنشاء وقراءة رمز شريطي DataMatrix هيكلي  
- **هل أحتاج إلى ترخيص؟** نسخة تجريبية مجانية تكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج  
- **المنصات المدعومة؟** .NET Framework, .NET Core, .NET 5/6/7  
- **هل يمكنني أيضًا فك تشفير الرمز الشريطي؟** نعم – راجع قسم “How to decode DataMatrix barcode”

## المتطلبات المسبرس، تأكد من أن لديك:

1. **مكتبة Aspose.BarCode لـ .NET** – قم بتنزيلها من [هنا](https://releases.aspose.com/barcode/net/).  
2. **بيئة التطالآن، دعنا نبدأ للعمل مع الإلحاق الهيكلي لـ DataMatrix باستخدام Aspose.BarCode لـ .NET.

## استيراد مساحات الأسماء

أولاً، استورد مساحات الأسماء التي تمنحك الوصول إلى فئات إنشاء الرموز الشريطية والتعرف عليها.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

الآن أنت جاهز لإنشاء وقراءة **رمز شريطي DataMatrix**.

## كيفية إنشاء رمز شريطي DataMatrix مع الإلحاق الهيكلي

لإنشاء رمز شريطي DataMatrix مع الإلحاق الهيكلي، تحتاج إلى ضبط عدة معلمات مثل معرف الرمز الشريطي، العدد الإجمالي للرموز الشريطية في السلسلة، ومعرف الملف الذي يربطها معًا.

```csharp
string path = "Your Directory Path";

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;

    // Set DataMatrix structured append mode
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodeId = 3;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodesCount = 5;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendFileId = 150;

    // Generate the barcode image
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

في هذا المقتطف، قمنا بتعيين الخصائص الأساسية التي تُفعِّل ميزة الإلحاق الهيكلي.

## كيفية فك تشفير رمز شريطي DataMatrix باستخدام Aspose.BarCode

بعد إنشاء الرمز الشريطي، غالبًا ما تحتاج إلى قراءة المعلومات المضمنة فيه. يستخدم الكود التالي `BarCodeReader` لاستخراج تفاصيل الإلحاق الهيكلي من الصورة التي أنشأناها للتو.

```csharp
    using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
    {
        reader.ReadBarCodes();

        Console.WriteLine("Barcode ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodeId);
        Console.WriteLine("Barcodes count: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodesCount);
        Console.WriteLine("File ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendFileId);
    }
}
```

هذا الجزء **يفك تشفير معلومات رمز شريطي DataMatrix** مثل معرف الرمز الشريطي، العدد الإجمالي، ومعرف الملف، مؤكدًا أن بيانات الإلحاق الهيكلي تم تضمينها بشكل صحيح.

## المشكلات الشائعة والنصائح

- **الأبعاد غير الصحيحة:** تأكد من أن `XDimension.Pixels` يتطابق مع دقة الطابعة أو الشاشة؛ وإلا قد يصبح الرمز الشريطي غير قابل للقراءة.  
- **عدد غير متطابق:** يجب أن يكون `StructuredAppendBarcodesCount` نفسه عبر جميع أجزاء السلسلة.  
- **أخطاء الترخيص:** إذا ظهرت تحذيرات ترخيص، تحقق من أن ملف الترخيص التجريبي أو التجاري مُشار إليه بشكل صحيح في مشروعك.

## الخلاصة

يُسهل Aspose.BarCode لـ .NET **إنشاء رمز شريطي DataMatrix** و**فك تشفير رمز شريطي DataMatrix** مع تكوينات الإلحاق الهيكلي. باتباع الخطوات أعلاه، يمكنك دمج هذه الرموز الشريطية في أنظمة الجرد، تتبع المستندات، أو أي سيناريو يستفيد من تقسيم حمولات البيانات الكبيرة عبر عدة رموز شريطية.

## الأسئلة المتكررة

### س1: ما هو الإلحاق الهيكلي لـ DataMatrix، ولماذا يُستخدم؟

ج1: الإلحاق الهيكلي لـ DataMatrix هو ميزة تسمح لك بتقسيم كمية كبيرة من البيانات إلى عدة رموز شريطية أصغر. هذا مفيد بشكل خاص عندما تكون مساحة الرمز الشريطي الواحد محدودة أو تحتاج إلى تنظيم البيانات بكفاءة. يُستخدم عادةً في صناعات مثل اللوجستيات، الرعاية الصحية، والتصنيع.

### س2: هل يمكنني استخدام Aspose.BarCode لـ .NET في مشروعي المفتوح المصدر؟

ج2: نعم، يوفر Aspose.BarCode لـ .NET نسخة تجريبية مجانية يمكنك استخدامها في المشاريع المفتوحة المصدر. يمكنك العثور على النسخة التجريبية [هنا](https://releases.aspose.com/).

### س3: هل هناك دعم مجتمع متاح لـ Aspose.BarCode لـ .NET؟

ج3: نعم، يمكنك طلب دعم المجتمع والتفاعل مع المستخدمين الآخرين على منتدى Aspose.BarCode [هنا](https://forum.aspose.com/c/barcode/13).

### س4: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.BarCode لـ .NET؟

ج4: إذا كنت بحاجة إلى ترخيص مؤقت للتقييم أو الاختبار، يمكنك الحصول عليه من [هنا](https://purchase.aspose.com/temporary-license/).

### س5: هل يدعم Aspose.BarCode لـ .NET أنواعًا أخرى من الرموز الشريطية؟

ج5: نعم، يدعم Aspose.BarCode لـ .NET مجموعة واسعة من أنواع الرموز الشريطية، بما في ذلك رموز QR، Code 128، EAN-13، والعديد غيرها. يمكنك استكشاف الوثائق الكاملة [هنا](https://reference.aspose.com/barcode/net/) لرؤية القائمة الكاملة لأنواع الرموز الشريطية المدعومة.

---

**آخر تحديث:** 2026-01-20  
**تم الاختبار مع:** Aspose.BarCode 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}