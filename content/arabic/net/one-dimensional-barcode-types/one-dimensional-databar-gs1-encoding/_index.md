---
title: ترميز شريط البيانات أحادي البعد GS1
linktitle: ترميز شريط البيانات أحادي البعد GS1
second_title: Aspose.BarCode .NET API
description: تعلم كيفية إنشاء رموز شريطية مشفرة لـ Databar GS1 في .NET باستخدام Aspose.BarCode. إنشاء الباركود بكل سهولة. اتبع دليلنا خطوة بخطوة.
type: docs
weight: 18
url: /ar/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
---

في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء رموز شريطية مشفرة أحادية البعد لـ Databar GS1 باستخدام مكتبة Aspose.BarCode for .NET. سواء كنت تتطلع إلى إنشاء رموز شريطية باستخدام تشفير GS1 أو بدونه، فلدينا كل ما تحتاجه. سيساعدك هذا الدليل التفصيلي خطوة بخطوة على فهم المتطلبات الأساسية واستيراد مساحات الأسماء وتوضيح كل مثال لإنشاء رموز شريطية مشفرة لـ Databar GS1 بسهولة.

## المتطلبات الأساسية

قبل أن نتعمق في الكود، تأكد من توفر المتطلبات الأساسية التالية:

1.  Aspose.BarCode لـ .NET: يجب أن يكون Aspose.BarCode لـ .NET مثبتًا لديك. إذا لم تكن قد قمت بذلك بالفعل، يمكنك تنزيله من[هنا](https://releases.aspose.com/barcode/net/).

2.  مسار الدليل الخاص بك: استبدال`"Your Directory Path"` في أمثلة التعليمات البرمجية مع المسار الفعلي حيث تريد حفظ صور الباركود التي تم إنشاؤها.

الآن بعد أن أصبحت المتطلبات الأساسية جاهزة، دعنا ننتقل إلى جزء البرمجة.

## استيراد مساحات الأسماء

للبدء، تحتاج إلى استيراد مساحات الأسماء ذات الصلة لـ Aspose.BarCode. أضف أسطر التعليمات البرمجية التالية في بداية مشروع .NET الخاص بك:

```csharp
using Aspose.BarCode;
using System;
```

## الخطوة 1: تهيئة مولد الباركود

الخطوة الأولى هي تهيئة كائن BarcodeGenerator بنوع الترميز المطلوب. في هذه الحالة، نستخدم ترميز Databar Expanded. 

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## الخطوة 2: إنشاء رمز شريطي بتشفير GS1

الآن، سوف نقوم بتعيين نص الكود مع فحص GS1Encoding وحفظ صورة الباركود التي تم إنشاؤها. 

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## الخطوة 3: إنشاء باركود ترميز متغير

في هذه الخطوة، سنقوم بإنشاء رمز شريطي يحتوي على نص رمزي متغير دون التحقق من GS1Encoding.

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## الخطوة 4: التعامل مع الاستثناء الخاص بفحص ترميز GS1

إذا حاولت إنشاء رمز شريطي يحتوي على نص رمزي متغير مع تمكين التحقق من GS1Encoding، فسيؤدي ذلك إلى حدوث استثناء. وإليك كيف يمكنك التعامل معها:

```csharp
try
{
    gen.CodeText = "ASPOSE";
    gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

لقد نجحت الآن في إنشاء رموز شريطية مشفرة أحادية البعد لـ Databar GS1 باستخدام Aspose.BarCode لـ .NET. يمكنك أيضًا استكشاف وتخصيص إنشاء الباركود الخاص بك بناءً على متطلباتك المحددة.

## خاتمة

في هذا البرنامج التعليمي، قمنا بتغطية عملية إنشاء رموز شريطية مشفرة أحادية البعد لـ Databar GS1 باستخدام Aspose.BarCode لـ .NET. لقد ناقشنا المتطلبات الأساسية، وقمنا باستيراد مساحات الأسماء الضرورية، وقدمنا إرشادات خطوة بخطوة لإنشاء كل من الرموز الشريطية المشفرة والمتغيرة GS1.

 مع Aspose.BarCode for .NET، يصبح إنشاء الرمز الشريطي مهمة سلسة، مما يوفر المرونة والتحكم في احتياجات إنشاء الرمز الشريطي لديك. إذا واجهت أي مشاكل أو لديك أسئلة، فلا تتردد في زيارة[وثائق Aspose.BarCode](https://reference.aspose.com/barcode/net/) أو طلب المساعدة على[منتدى دعم Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

## أسئلة مكررة

### 1. ما هو ترميز GS1 في الباركود؟
يعد ترميز GS1 معيارًا يستخدم في التشفير الشريطي لضمان بنية البيانات وتحديد هويتها بشكل صحيح. يتم استخدامه بشكل شائع للعناصر الموجودة في البيع بالتجزئة والرعاية الصحية والخدمات اللوجستية لتسهيل التتبع الدقيق وتبادل المعلومات.

### 2. هل يمكنني تخصيص مظهر الباركود الذي تم إنشاؤه؟
نعم، يمكنك تخصيص مظهر الرموز الشريطية التي تم إنشاؤها باستخدام Aspose.BarCode لـ .NET. يمكنك التحكم في العديد من المعلمات مثل الحجم واللون والنمط.

### 3. أين يمكنني العثور على موارد ووثائق إضافية خاصة بـ Aspose.BarCode؟
 يمكنك العثور على وثائق وأمثلة شاملة على[وثائق Aspose.BarCode](https://reference.aspose.com/barcode/net/). إنه مورد قيم للتعلم واستكشاف الأخطاء وإصلاحها.

### 4. هل هناك نسخة تجريبية متاحة لـ Aspose.BarCode؟
 نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.BarCode لـ .NET من[هنا](https://releases.aspose.com/).

### 5. كيف يمكنني شراء ترخيص Aspose.BarCode لـ .NET؟
 لشراء ترخيص Aspose.BarCode لـ .NET، قم بزيارة[صفحة الشراء](https://purchase.aspose.com/buy) على موقع Aspose.
