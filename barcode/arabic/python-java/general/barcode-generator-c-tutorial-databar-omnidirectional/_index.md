---
category: general
date: 2026-11-14
description: دليل توليد الباركود بلغة C# يوضح كيفية إنشاء باركود DataBar Omnidirectional،
  وتعيين البُعد X، وضبط ارتفاع الخطوط بالبكسل.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c# tutorial
- DataBar Omnidirectional
- set bar height
- XDimension pixels
- BarCodeImageFormat PNG
language: ar
lastmod: 2026-11-14
og_description: يشرح درس توليد الباركود بلغة C# خطوة بخطوة كيفية إنشاء باركود DataBar
  Omnidirectional، وتحديد XDimension بالبكسل، وتغيير ارتفاع الخطوط لإخراج PNG.
og_image_alt: Screenshot of barcode generator C# tutorial output showing a DataBar
  barcode
og_title: دليل مولد الباركود C# – إنشاء باركود DataBar
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Barcode generator C# tutorial that shows how to create DataBar Omnidirectional
    barcodes, set X‑dimension, and adjust bar height in pixels.
  headline: 'Barcode generator C# tutorial: DataBar Omnidirectional'
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- tutorial
title: 'دليل توليد الباركود بلغة C#: DataBar Omnidirectional'
url: /ar/python-java/general/barcode-generator-c-tutorial-databar-omnidirectional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# دليل توليد الباركود C# – إنشاء باركود DataBar Omnidirectional

إذا كنت تبحث عن **دليل توليد الباركود C#**، فقد وصلت إلى المكان الصحيح. يشرح هذا الدليل كيفية إنشاء باركود DataBar Omnidirectional، وضبط XDimension بالبكسل، وتعديل ارتفاع الخطوط لإنتاج صور PNG.

سترى مثالًا كاملاً قابلاً للتنفيذ يغطي كل شيء من تهيئة المولد إلى حفظ صور متعددة بارتفاعات خطوط مختلفة. لا حاجة لأي وثائق خارجية—فقط انسخ الشيفرة، شغّلها، وستحصل على ملفي باركود جاهزين للاستخدام.

## المتطلبات المسبقة

* .NET 6.0 أو أحدث مثبت  
* مرجع إلى مكتبة الباركود التي توفر `BarcodeGenerator` و `EncodeTypes` و `BarCodeImageFormat` (مثال: Aspose.BarCode for .NET)  
* إلمام أساسي بصياغة C# و Visual Studio أو بيئة التطوير المتكاملة التي تفضلها  

> **نصيحة احترافية:** إذا كنت تستخدم Aspose.BarCode، أضف حزمة NuGet `Aspose.BarCode` إلى مشروعك.

## دليل توليد الباركود C# – الخطوة 1: إنشاء المولد

الخطوة الأولى هي إنشاء كائن `BarcodeGenerator` باستخدام نوع الترميز `DatabarOmniDirectional` والبيانات التي تريد ترميزها.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Omnidirectional barcode generator with the desired data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*لماذا هذا مهم:* `EncodeTypes.DatabarOmniDirectional` يخبر المكتبة بإنتاج باركود يمكن قراءته من أي اتجاه، وهو مثالي لتغليف التجزئة واللوجستيات.

## ضبط بكسلات XDimension للباركود

يحدد X‑dimension عرض أصغر وحدة (الـ “بكسل”) في الباركود. ضبطه بالبكسل يمنحك تحكمًا دقيقًا في كثافة الباركود البصرية.

```csharp
        // Step 2: Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*شرح:* قيمة `2` بكسل تنتج باركودًا حادًا بما يكفي لمعظم الماسحات الضوئية مع الحفاظ على حجم ملف الصورة معتدلًا.

## تعديل ارتفاع الخطوط وحفظ الصور

ارتفاع الخطوط يحدد مدى طول الخطوط الظاهرة. يمكنك إنشاء صور متعددة بارتفاعات مختلفة عن طريق تغيير خاصية `BarHeight.Pixels` واستدعاء `Save` مرة أخرى.

```csharp
        // Step 3: Set the bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        string outputPath = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
```

قيمة التعداد `BarCodeImageFormat.Png` تضمن أن يكون الناتج ملف PNG غير مضغوط، وهو الصيغة الموصى بها لرسومات الباركود لأنها تحافظ على الأبعاد الدقيقة.

## تغيير ارتفاع الخطوط لإنشاء صور متعددة

غالبًا ما تحتاج إلى نفس الباركود بأحجام مختلفة—مثلاً، واحد لملصق صغير وآخر لملصق كبير. غيّر ارتفاع الخطوط وأعد استخدام نفس كائن المولد:

```csharp
        // Step 4: Change the bar height to 60 px and save a second image
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        outputPath = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

*حالة حدية:* إذا تم ضبط ارتفاع الخطوط منخفضًا جدًا (مثلاً أقل من 10 px)، قد تواجه بعض الماسحات صعوبة في قراءة الكود. اختبر دائمًا الصور المولدة مع جهاز الماسح المستهدف.

## الشيفرة المصدرية الكاملة

فيما يلي البرنامج الكامل الذي يمكنك نسخه ولصقه في مشروع وحدة تحكم جديد. يتضمن جميع توجيهات `using` المطلوبة ويظهر كلا من اختلافات ارتفاع الخطوط.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a DataBar Omnidirectional barcode generator
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Set XDimension to 2 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image – 30 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
            generator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 30 px barcode to {path30}");

            // Second image – 60 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
            generator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 60 px barcode to {path60}");
        }
    }
}
```

شغّل البرنامج، استبدل `YOUR_DIRECTORY` بمسار مجلد صالح، وستجد ملفي PNG:

* `DatabarBarHeight30Pixels.png` – خطوط بارتفاع 30 px  
* `DatabarBarHeight60Pixels.png` – خطوط بارتفاع 60 px  

![نتيجة دليل توليد الباركود C#](images/databar-example.png "دليل توليد الباركود C# يظهر صورتين لباركود DataBar")

## أسئلة شائعة

| السؤال | الإجابة |
|----------|--------|
| **هل يمكنني تغيير صيغة الصورة؟** | نعم. استبدل `BarCodeImageFormat.Png` بـ `Jpeg` أو `Bmp` أو `Gif` حسب الحاجة. يُفضَّل PNG للجودة غير المضغوطة. |
| **ماذا لو احتجت إلى XDimension مختلف؟** | قم بضبط `generator.Parameters.Barcode.XDimension.Pixels` إلى أي عدد صحيح. القيم الأكبر تزيد من عرض الباركود الكلي. |
| **هل الباركود DataBar Omnidirectional مناسب للمسح الضوئي عبر الهاتف المحمول؟** | نعم، بشرط أن يكون الحجم المطبوع يفي بأقل حجم وحدة للماسح (عادةً 0.33 مم). يساعدك XDimension القائم على البكسل في تحقيق هذا المتطلب. |
| **كيف يمكنني تضمين الباركود في ملف PDF؟** | بعد حفظ PNG، استخدم مكتبة PDF (مثل iTextSharp) لإدراج الصورة في صفحة PDF. |

## الخلاصة

هذا **دليل توليد الباركود C#** أظهر لك كيفية إنشاء باركود DataBar Omnidirectional، وضبط XDimension بالبكسل، وتوليد ملفات PNG بارتفاعات خطوط مختلفة. لديك الآن مقطع شيفرة قابل لإعادة الاستخدام يمكنك تعديله لأي مشروع C# يتطلب إنشاء باركود.

### ما التالي؟

* استكشف `EncodeTypes` أخرى مثل `Code128` أو `QR` لتوسيع مجموعة الباركود الخاصة بك.  
* اجمع PNG المولد مع مكتبة إنشاء PDF لإنتاج فواتير قابلة للطباعة.  
* جرب `generator.Parameters.Barcode.Color` لإضافة ألوان مخصصة مع الالتزام بمواصفات الماسحات.

لا تتردد في تعديل المثال، تجربة ارتفاعات خطوط إضافية، أو تغيير صيغة الإخراج. برمجة سعيدة!

## ما الذي يجب أن تتعلمه بعد ذلك؟

الدروس التالية تغطي مواضيع ذات صلة وثيقة تبني على التقنيات الموضحة في هذا الدليل. كل مورد يتضمن أمثلة شيفرة كاملة مع شروحات خطوة بخطوة لمساعدتك على إتقان ميزات API إضافية واستكشاف أساليب تنفيذ بديلة في مشاريعك.

- [كيفية ضبط العرض وتعديل الارتفاع لباركود GS1 DataBar Omni‑Directional](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [كيفية ضبط ارتفاع الباركود، إنشاء باركود DataBar في C#](/barcode/english/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/)
- [كيفية إنشاء باركود Databar Omnidirectional في C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}