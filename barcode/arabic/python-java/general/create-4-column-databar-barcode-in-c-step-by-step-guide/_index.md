---
category: general
date: 2026-08-09
description: أنشئ باركود داتابار بأربعة أعمدة في C# بسرعة باستخدام Aspose.BarCode.
  تعلّم كيفية ضبط الأعمدة والصفوف وحفظ صور PNG في هذا الدليل المختصر.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create 4‑column databar barcode
- databar expanded stacked
- barcode generator c#
- set barcode rows
- barcode image format
language: ar
lastmod: 2026-08-09
og_description: إنشاء باركود داتابار بأربعة أعمدة في C# باستخدام Aspose.BarCode، ثم
  تخصيص الصفوف وتصدير صور PNG لتطبيقك.
og_image_alt: Screenshot of a 4‑column DataBar Expanded Stacked barcode generated
  in C#
og_title: إنشاء باركود داتابار بأربعة أعمدة في C# – دليل سريع
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create 4‑column databar barcode in C# quickly with Aspose.BarCode.
    Learn how to configure columns, rows, and save PNG images in this concise guide.
  headline: Create 4‑column databar barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create 4‑column databar barcode in C# quickly with Aspose.BarCode.
    Learn how to configure columns, rows, and save PNG images in this concise guide.
  name: Create 4‑column databar barcode in C# – step‑by‑step guide
  steps:
  - name: Configure DataBar Expanded Stacked columns
    text: If you need a different column count, simply change the integer assigned
      to `Columns`. The property accepts values from 1 to 4 for the expanded stacked
      variant.
  - name: Save the barcode image
    text: The `BarCodeImageFormat` enumeration provides several options (`Png`, `Jpeg`,
      `Bmp`, `Gif`, `Tiff`). PNG is loss‑less and works well for most web and desktop
      scenarios.
  - name: Set barcode rows dynamically
    text: 'You can compute the row count at runtime based on input data:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- DataBar
title: إنشاء باركود داتابار بأربع أعمدة في C# – دليل خطوة بخطوة
url: /ar/python-java/general/create-4-column-databar-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء باركود DataBar بأربعة أعمدة في C# – دليل خطوة بخطوة

إذا كنت بحاجة إلى **إنشاء باركود DataBar بأربعة أعمدة** في C#، فإن هذا الدليل يوضح لك بالضبط كيفية ذلك. سنستعرض عملية إنشاء باركود DataBar Expanded Stacked، وضبط أربعة أعمدة، وحفظ النتيجة كصورة PNG.

في هذا الدليل ستتعلم كيف:

* تهيئة `BarcodeGenerator` لرمز **DataBar Expanded Stacked**.  
* ضبط عدد الأعمدة إلى 4 (المتطلب الأساسي).  
* تعديل عدد الصفوف عندما تحتاج إلى تخطيط مكدس مع ثلاثة صفوف.  
* تصدير الباركود كملف PNG باستخدام **تنسيق صورة الباركود** المناسب.

كل ما تحتاجه هو مكتبة Aspose.BarCode for .NET (الإصدار 23.10 أو أحدث) وبيئة تطوير .NET 6+ مثل Visual Studio 2022. لا توجد تبعيات إضافية مطلوبة.

---

## كيفية إنشاء باركود DataBar بأربعة أعمدة

الخطوة الأولى هي إنشاء كائن `BarcodeGenerator` يستهدف رموز **DataBar Expanded Stacked**. هذه الفئة تغلف جميع خيارات العرض، مما يجعل من السهل التبديل بين التخطيطات القائمة على الأعمدة أو الصفوف.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise a generator for DataBar Expanded Stacked
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        
        // 2️⃣ Set the barcode to use a 4‑column layout
        generator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image as PNG
        generator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**لماذا هذا يعمل:**  
`EncodeTypes.DatabarExpandedStacked` يخبر Aspose.BarCode بإنتاج النسخة المكدسة من عائلة DataBar. خاصية `DataBar.Columns` تتحكم في عدد الوحدات العمودية التي يشغلها الباركود. ضبطها على 4 يطابق المتطلب لإنشاء **باركود DataBar بأربعة أعمدة**. أخيرًا، `Save` يكتب التمثيل البصري على القرص باستخدام **تنسيق صورة الباركود** `Png`.

### تكوين أعمدة DataBar Expanded Stacked

إذا كنت بحاجة إلى عدد أعمدة مختلف، ما عليك سوى تغيير القيمة الصحيحة المخصصة لـ `Columns`. الخاصية تقبل قيمًا من 1 إلى 4 للنسخة المكدسة الموسعة.

```csharp
// Example: switch to a 2‑column layout
generator.Parameters.Barcode.DataBar.Columns = 2;
```

*نصيحة احترافية:* اختبر دائمًا الباركود المُولد باستخدام ماسح يدعم عائلة DataBar، لأن المظهر البصري وحده لا يضمن القابلية للقراءة.

### حفظ صورة الباركود

تُوفر تعداد `BarCodeImageFormat` عدة خيارات (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`). PNG غير مضغوط ويعمل جيدًا لمعظم سيناريوهات الويب وسطح المكتب.

```csharp
generator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
```

إذا كنت بحاجة إلى تنسيق مختلف، استبدل `Png` بالقيمة المطلوبة من التعداد. يمكن تضمين الملف المحفوظ مباشرةً في HTML أو PDFs أو طباعته على الملصقات.

## إنشاء باركود بصفوف مخصصة

أحيانًا يكون التخطيط المكدس مطلوبًا بعدد محدد من الصفوف بدلاً من الأعمدة. نفس الفئة `BarcodeGenerator` تُظهر خاصية `Rows` لهذا الغرض.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class RowExample
{
    static void Main()
    {
        // 1️⃣ Initialise a generator for the same symbology
        BarcodeGenerator rowGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the barcode to use a 3‑row layout
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 3️⃣ Save the image as PNG
        rowGenerator.Save("DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**لماذا الصفوف مهمة:**  
عندما يكون الباركود المكدس أطول من عرضه، تحدد خاصية `Rows` عدد الشرائح الأفقية التي يُقسم إليها الرمز. ضبط `Rows = 3` يُنشئ باركودًا مكدسًا بثلاثة صفوف، وهو مفيد لعروض الملصقات الضيقة.

### ضبط صفوف الباركود ديناميكيًا

يمكنك حساب عدد الصفوف في وقت التشغيل بناءً على بيانات الإدخال:

```csharp
int desiredRows = GetRowsFromUser(); // your custom logic
rowGenerator.Parameters.Barcode.DataBar.Rows = desiredRows;
```

هذه المرونة تتيح لك **ضبط صفوف الباركود** دون الحاجة إلى إعادة تجميع التطبيق.

## مثال كامل من البداية إلى النهاية

فيما يلي برنامج واحد يُنشئ كلًا من باركود بأربعة أعمدة وباركود بثلاثة صفوف، موضحًا كيفية ت coexistence التكوينين.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class FullExample
{
    static void Main()
    {
        // ---------- 4‑column barcode ----------
        BarcodeGenerator colGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        colGen.Parameters.Barcode.DataBar.Columns = 4; // create 4‑column databar barcode
        colGen.Save("DatabarCols4.png", BarCodeImageFormat.Png);

        // ---------- 3‑row barcode ----------
        BarcodeGenerator rowGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        rowGen.Parameters.Barcode.DataBar.Rows = 3; // set barcode rows to 3
        rowGen.Save("DatabarRows3.png", BarCodeImageFormat.Png);

        // Output confirmation
        System.Console.WriteLine("Barcodes generated:");
        System.Console.WriteLine(" - DatabarCols4.png (4 columns)");
        System.Console.WriteLine(" - DatabarRows3.png (3 rows)");
    }
}
```

**الناتج المتوقع:**  
ظهر ملفان PNG في دليل العمل الخاص بالتطبيق:

* `DatabarCols4.png` – باركود DataBar Expanded Stacked بأربعة أعمدة عمودية.  
* `DatabarRows3.png` – نفس الرمز مُرتب في ثلاثة صفوف أفقية.

يمكن فتح الصورتين في أي عارض صور أو تضمينهما في عنصر واجهة مستخدم.

---

## أسئلة شائعة وحالات خاصة

| السؤال | الجواب |
|----------|--------|
| *هل يمكنني استخدام رموز باركود مختلفة؟* | نعم. استبدل `EncodeTypes.DatabarExpandedStacked` بقيمة `EncodeTypes` أخرى (مثل `EncodeTypes.QR`)، لكن خاصيتي `Columns` و `Rows` خاصة بعائلات DataBar. |
| *ماذا لو تجاوز نص البيانات الحد الأقصى للطول؟* | تدعم رموز DataBar Expanded Stacked ما يصل إلى 61 حرفًا رقميًا. تجاوز هذا الحد يُطلق استثناء `ArgumentException`. تحقق من صحة الإدخال قبل تمريره إلى المُولد. |
| *هل يجب إغلاق `BarcodeGenerator`؟* | `BarcodeGenerator` يُطبق الواجهة `IDisposable`. في خدمة طويلة التشغيل، غلفه بكتلة `using` أو استدعِ `Dispose()` يدويًا لتحرير الموارد الأصلية. |
| *هل يمكنني إنشاء SVG بدلاً من PNG؟* | بالتأكيد. استخدم `BarCodeImageFormat.Svg` في طريقة `Save`. |
| *هل المكتبة متوافقة مع .NET Core؟* | Aspose.BarCode for .NET يدعم .NET Core 3.1، .NET 5، .NET 6 وما بعده. لا تحتاج إلى تعديل الكود. |

---

## الخلاصة

أنت الآن تعرف كيف **تنشئ باركود DataBar بأربعة أعمدة** في C# باستخدام Aspose.BarCode، وكيفية تعديل التخطيط بالصفوف، وكيفية تصدير النتيجة بتنسيق **صورة باركود** ملائم. يُظهر المثال الكامل كلًا من التكوينات القائمة على الأعمدة والصفوف، مما يمنحك أساسًا قويًا لأي سيناريو طباعة ملصقات أو مسح ضوئي عبر الهاتف المحمول.

**الخطوات التالية**

* جرّب أحمال بيانات مختلفة وتحقق من توافقها مع الماسحات.  
* استكشف خيارات تنسيق إضافية مثل ألوان المقدمة/الخلفية (`generator.Parameters.Barcode.Color`).  
* دمج الباركود مع رسومات أخرى باستخدام واجهة `Graphics` لتصميم ملصقات مخصص.

لا تتردد في تعديل الكود لمشاريع ASP.NET Core أو Windows Forms أو Xamarin—Aspose.BarCode يعمل عبر جميع منصات .NET. برمجة سعيدة!

## ما الذي ينبغي أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تُبنى على التقنيات الموضحة في هذا الدليل. كل مورد يتضمن أمثلة شاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [إنشاء صورة باركود DotCode – الصفوف والأعمدة (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [إنشاء صورة باركود c# – تكوين صفوف وأعمدة Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [كيفية إنشاء نص رمزي موسع لـ dotcode باستخدام Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}