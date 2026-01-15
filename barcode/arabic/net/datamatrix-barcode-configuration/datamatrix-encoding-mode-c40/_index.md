---
date: 2026-01-15
description: تعلم كيفية حفظ ملفات PNG أثناء استخدام وضع ترميز DataMatrix (C40) مع
  Aspose.BarCode لـ .NET – دليل خطوة بخطوة للباركود.
linktitle: DataMatrix Encoding Mode (C40)
second_title: Aspose.BarCode .NET API
title: كيفية حفظ PNG باستخدام DataMatrix C40 مع Aspose.BarCode
url: /ar/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# الوضع الرئيسي لتشفير DataMatrix (C40) باستخدام Aspose.BarCode لـ .NET

## مقدمة

## إجابات سريعة
- **ماذا يعني “how to save png”؟** حفظ الباركود المُولد كملف صورة PNG.  
- **أي وضع تشفير يتم تغطيته؟** تشفير DataMatrix C40.  
- **هل أحتاج إلى ترخيص؟** الإصدار التجريبي المجاني يكفي للاختبار؛ الترخيص مطلوب للإنتاج.  
- **هل يمكن تشغيله على .NET Core؟** نعم، Aspose.BarCode يدعم .NET Framework و .NET Core.  
- **ما هو تنسيق الملف الناتج؟** صورة PNG (Portable Network Graphics).

## كيفية حفظ PNG مع تشفير DataMatrix C40
حفظ الباركود كملف PNG هو الخطوة الأخيرة بعد تكوين المولد. طريقة `Save` تأخذ مسار الملف، اسم الملف المطلوب، وتنسيق الصورة (`BarCodeImageFormat.Png`). هذا يضمن تخزين الباركود بتنسيق غير فقدان للبيانات يعمل عبر المتصفحات، الطابعات، والأجهزة المحمولة.

## ما هو وضع تشفير DataMatrix (C40)؟
C40 هو مجموعة أحرف فعّالة للبيانات الحرفية الرقمية، تسمح لك بضغط المزيد من المعلومات في رمز DataMatrix أصغر. وهو مفيد بشكل خاص عندما تحتاج إلى تشفير نص يحتوي على أحرف، أرقام، ومجموعة محدودة من الأحرف الخاصة.

## لماذا تستخدم Aspose.BarCode لـ .NET؟
- **تحكم كامل** في أبعاد الباركود، تصحيح الأخطاء، ووضعيات التشفير.  
- **توليد بدون تبعيات** – لا حاجة لخدمات خارجية.  
- **دعم متعدد المنصات** لـ .NET Framework، .NET Core، و .NET 5/6+.  

## المتطلبات المسبقة
قبل الغوص في الكود، تأكد من أن لديك ما يلي:

1. بيئة تطوير .NET – Visual Studio، Rider، أو أي بيئة تطوير تدعم C#.  
2. Aspose.BarCode لـ .NET – مثبت عبر NuGet أو المثبت الرسمي. راجع [التوثيق](https://reference.aspose.com/barcode/net/) للتفاصيل.  
3. معرفة أساسية بـ C# – يجب أن تكون مرتاحًا مع المساحات الاسمية، الفئات، وتعليمات using.  
4. مجلد بصلاحية كتابة – دليل على جهازك حيث سيتم حفظ ملف PNG.  

## استيراد المساحات الاسمية الضرورية
أضف المساحة الاسمية المطلوبة في أعلى ملف C# الخاص بك لتتمكن من الوصول إلى فئات توليد الباركود:

```csharp
using Aspose.BarCode.Generation;
```

## توليد الباركود خطوة بخطوة
فيما يلي دليل **الباركود خطوة بخطوة**. يتم شرح كل خطوة بلغة بسيطة، وتُحافظ على كتل الكود الأصلية دون تعديل لتسهيل النسخ واللصق.

### الخطوة 1: تعريف مسار الدليل
حدد المجلد الذي سيُحفظ فيه صورة PNG. استبدل العنصر النائب بمسار فعلي على جهازك.

```csharp
string path = "Your Directory Path";
```

### الخطوة 2: إعداد توليد الباركود
أنشئ كائن `BarcodeGenerator`، حدد `EncodeTypes.DataMatrix`، وقدم البيانات التي تريد تشفيرها.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### الخطوة 3: تخصيص الباركود
قم بتكوين البُعد X (عرض البكسل للوحدات) وقم بتبديل وضع التشفير إلى C40.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### الخطوة 4: حفظ صورة الباركود
أخيرًا، احفظ الباركود المُولد كملف PNG. هذا هو الجواب المحدد على **كيفية حفظ png** باستخدام Aspose.BarCode.

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

عند تشغيل البرنامج، ستجد `DataMatrixEncodeModeC40.png` في المجلد الذي حددته، جاهز للاستخدام في التقارير، الملصقات، أو صفحات الويب.

## المشكلات الشائعة والنصائح
- **مسار غير صالح** – تأكد من وجود الدليل ولديك صلاحيات كتابة؛ وإلا ستطلق `gen.Save` استثناء.  
- **وضع تشفير غير صحيح** – إذا كنت بحاجة لتشفير أحرف خارج مجموعة C40، فبدّل إلى `DataMatrixEncodeMode.Auto` أو وضع مناسب آخر.  
- **حجم الصورة** – اضبط `XDimension.Pixels` لزيادة أو تقليل حجم الباركود العام دون التأثير على قابلية القراءة.  

## الأسئلة المتكررة
**س: ما هو وضع تشفير DataMatrix (C40)؟**  
ج: C40 هو نظام تشفير حروف وأرقام مدمج لرموز DataMatrix، مثالي للنص الذي يتضمن أحرفًا، أرقامًا، ومجموعة محدودة من الأحرف الخاصة.

**س: أين يمكنني العثور على توثيق Aspose.BarCode لـ .NET؟**  
ج: يمكنك العثور على التوثيق [هنا](https://reference.aspose.com/barcode/net/). يقدم إرشادات مفصلة حول جميع أنواع الباركود وخيارات التشفير.

**س: هل Aspose.BarCode لـ .NET متوافق مع جميع إصدارات .NET؟**  
ج: نعم، المكتبة تدعم مجموعة واسعة من إصدارات .NET، من .NET Framework 4.5+ إلى .NET 6 وما بعده.

**س: هل يمكنني تجربة Aspose.BarCode لـ .NET قبل الشراء؟**  
ج: نعم، يمكنك استكشاف نسخة تجريبية مجانية من Aspose.BarCode لـ .NET بزيارة [هذا الرابط](https://releases.aspose.com/). يتيح لك اختبار ميزات المكتبة وقدراتها.

**س: أين يمكنني الحصول على الدعم لـ Aspose.BarCode لـ .NET؟**  
ج: يمكنك العثور على مجتمع داعم والوصول إلى الدعم لـ Aspose.BarCode لـ .NET على [منتدى Aspose](https://forum.aspose.com/c/barcode/13).

## الخلاصة
باتباعك لهذا الدليل **الباركود خطوة بخطوة**، أنت الآن تعرف بالضبط **كيفية حفظ PNG** للملفات المُولدة بتشفير DataMatrix C40 باستخدام Aspose.BarCode لـ .NET. يمنحك هذا النهج تحكمًا كاملًا في مظهر الباركود، حجمه، وتمثيل البيانات، مما يجعل من السهل دمج باركود عالي الجودة في أي تطبيق .NET.

---

**آخر تحديث:** 2026-01-15  
**تم الاختبار مع:** Aspose.BarCode 24.11 for .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}