---
date: 2026-03-07
description: تعلم كيفية إنشاء باركودات Databar أحادية البعد المشفرة وفق معيار GS1
  في .NET باستخدام Aspose.BarCode. يوضح هذا الدليل كيفية ضبط GS1، وتكوين مولد الباركود،
  وإنشاء الباركودات بسرعة.
linktitle: One-Dimensional Databar GS1 Encoding
second_title: Aspose.BarCode .NET API
title: إنشاء ترميز GS1 أحادي الأبعاد لباركود Databar باستخدام Aspose.BarCode
url: /ar/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء شيفرة Databar أحادية البُعد مع ترميز GS1 باستخدام Aspose.BarCode

في هذا الدرس ستقوم **بإنشاء شيفرات Databar أحادية البُعد** التي تتوافق مع معيار GS1، باستخدام مكتبة Aspose.BarCode لـ .NET. سواء كنت تحتاج إلى تحقق صارم من GS1 أو شيفرة أكثر مرونة، سنستعرض كل خطوة — من تثبيت المكتبة إلى معالجة استثناءات الترميز — حتى تتمكن من توليد شيفرات موثوقة في تطبيقاتك الخاصة.

## إجابات سريعة
- **ماذا يعني “إنشاء شيفرة Databar أحادية البُعد”؟** يعني ذلك توليد شيفرة خطية (1‑D) من عائلة Databar، تُستخدم غالبًا في التجزئة واللوجستيات.  
- **كيف أُفعِّل تحقق GS1؟** عيّن `IsAllowOnlyGS1Encoding` إلى `true` في معلمات `DataBar`.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج.  
- **ما هي إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.  
- **أين يمكنني تنزيل المكتبة؟** من صفحة الإصدار الرسمية لـ Aspose (انظر المتطلبات المسبقة).

## ما هو “إنشاء شيفرة Databar أحادية البُعد”؟
Databar أحادية البُعد (المعروفة أيضًا باسم RSS) هي شيفرة خطية مدمجة يمكنها ترميز بيانات رقمية أو تواريخ أو سلاسل AI (معرف التطبيق). عند دمجها مع ترميز GS1، تتبع الشيفرة بنية بيانات معترف بها عالميًا، مما يجعلها مثالية لسيناريوهات التجزئة، الرعاية الصحية، وسلسلة الإمداد.

## لماذا نستخدم Aspose.BarCode لـ .NET؟
توفر Aspose.BarCode واجهة برمجة تطبيقات سلسة، دعم كامل لـ GS1، وإمكانية ضبط كل جانب بصري من الشيفرة. فهي تزيل التخمين في الترميز منخفض المستوى وتسمح لك بالتركيز على منطق الأعمال.

## المتطلبات المسبقة

1. **Aspose.BarCode for .NET** – قم بتنزيله وتثبيته من [هنا](https://releases.aspose.com/barcode/net/).  
2. **مسار الدليل الخاص بك** – استبدل `"Your Directory Path"` في الأمثلة بمجلد تملك صلاحية الكتابة فيه.

## استيراد المساحات الاسمية

أضف عبارات `using` المطلوبة في أعلى ملف C# الخاص بك:

```csharp
using Aspose.BarCode;
using System;
```

## الخطوة 1: تهيئة مولد الشيفرة

أنشئ كائن `BarcodeGenerator` وحدد نوع رموز Databar Expanded:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## الخطوة 2: كيفية ضبط GS1 – توليد شيفرة مع تحقق صارم من GS1

فعّل الترميز المقتصر على GS1، عيّن نصًا متوافقًا مع GS1، واحفظ الصورة:

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## الخطوة 3: توليد شيفرة مع Aspose – ترميز متغيّر (بدون فحص GS1)

إذا كنت تحتاج شيفرة لا تفرض قواعد GS1، قم بإيقاف الفحص:

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## الخطوة 4: فحص مولد الشيفرة GS1 – معالجة استثناء

عند ضبط `IsAllowOnlyGS1Encoding` إلى `true` ولكن النص غير متوافق مع GS1، تقوم Aspose برمي استثناء. يوضح النمط التالي كيفية التقاطه وتسجيله:

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

### الأخطاء الشائعة والنصائح
- **خطأ شائع:** توفير سلسلة غير GS1 بينما فحص GS1 مفعَّل سيؤدي إلى إلغاء توليد الشيفرة.  
- **نصيحة احترافية:** تحقق من سلاسل AI قبل تعيينها إلى `CodeText` لتجنب الأخطاء وقت التشغيل.  
- **نصيحة:** استخدم مسارات مطلقة أو `Path.Combine` لإنشاء أسماء الملفات بأمان عبر الأنظمة.

## الخلاصة

الآن تعرف كيف **تنشئ شيفرات Databar أحادية البُعد** مع ترميز GS1، وكيفية تشغيل/إيقاف فحص GS1، وكيفية التعامل مع الاستثناءات المرتبطة — كل ذلك باستخدام Aspose.BarCode لـ .NET. يمكنك استكشاف خيارات تنسيق إضافية مثل حجم الشيفرة، اللون، والهوامش عبر كائن `Parameters.Barcode`.

إذا واجهت أي مشاكل، فإن الوثائق الرسمية ومنتدى المجتمع مصادر ممتازة:

- [توثيق Aspose.BarCode](https://reference.aspose.com/barcode/net/)  
- [منتدى دعم Aspose.BarCode](https://forum.aspose.com/c/barcode/13)

## الأسئلة المتكررة

### 1. ما هو ترميز GS1 في الشيفرات؟
ترميز GS1 هو طريقة موحدة لبنية البيانات (مثل معرفات المنتجات) داخل الشيفرة، مما يضمن التوافق بين التجار، المصنعين، ومزودي الخدمات اللوجستية.

### 2. هل يمكنني تخصيص مظهر الشيفرات المولدة؟
نعم. تتيح لك Aspose.BarCode تعديل الحجم، الألوان، الهوامش، وحتى إضافة نص قابل للقراءة البشرية عبر إعدادات `Parameters.Barcode`.

### 3. أين يمكنني العثور على موارد إضافية ووثائق Aspose.BarCode؟
يمكنك العثور على وثائق شاملة وأمثلة في [توثيق Aspose.BarCode](https://reference.aspose.com/barcode/net/). إنها مصدر قيم للتعلم وحل المشكلات.

### 4. هل تتوفر نسخة تجريبية من Aspose.BarCode؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.BarCode لـ .NET من [هنا](https://releases.aspose.com/).

### 5. كيف يمكنني شراء ترخيص لـ Aspose.BarCode لـ .NET؟
لشراء ترخيص لـ Aspose.BarCode لـ .NET، زر صفحة [الشراء](https://purchase.aspose.com/buy) على موقع Aspose.

---

**آخر تحديث:** 2026-03-07  
**تم الاختبار مع:** Aspose.BarCode 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}