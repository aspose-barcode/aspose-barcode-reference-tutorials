---
date: 2026-01-20
description: تعلم كيفية إنشاء صورة الباركود برمجيًا في وضع ASCII باستخدام Aspose.BarCode
  لـ .NET. دليل خطوة بخطوة مع عينات من الشيفرة.
linktitle: DataMatrix Encoding Mode (ASCII)
second_title: Aspose.BarCode .NET API
title: كيفية إنشاء صورة الباركود برمجياً – ترميز DataMatrix ASCII باستخدام Aspose.BarCode
  لـ .NET
url: /ar/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# الترميز الرئيسي لـ Data بحاجة باركود برمجيًا**، فإن الفواتير، أو أي مستند آخر. سواء كنت مطورًا متمرسًا أو مبتدئًا في تولفيذ
- **ما المكتبة التي أحتاجها؟** Aspose.BarCode لـ .NET
- **هل يمكنني توليد الصورة بسطر واحد من الكود؟** نعم، بعد ضبط بعض المعلمات
- **ما هو تنسيق الصورة المستخدم في المثال؟** PNG
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تكفي للاختبار؛ الترخيص مطلوب للإنتاج
- **هل الكود متوافق مع .NET Core / .NET 5+؟** بالتأكيد

## ما هو ترميز DataMatrix ASCII؟
DataMatrix هوستخدم AspNET؟
توفر Aspose.Barود. تتيح لك **إنشاء صورة باركود برمجيًا** عبر تعيين عدد قليل من الخصائص فقط، وتدعم مجموعة واسعة من التنسيقات، وتوفر خيارات تخصيص واسعة (الحجم، الألوان، الهوامش، إلخ).

## المتطلبات المسبقة

1. **بيئة التطوير** – Visual Studio أو Visual Studio Code أوقة مع .NET.  
2. **Aspose.BarCode لـ .NET** – حمّل المكتبة من [هنا](https://releases.aspose.com/barcode/net/).  
3. **معرفة أساسية بـ C#** – الكود بسيط، لكن الإلمام بصياغة C# سيساعدك.

الآن بعد أن أعددنا كل شيء، لنبدأ التنفيذ.

## كيفية إنشاء صورة باركود برمجيضف المساحةئات المولد.

```csharp
using Aspose.BarCode.Generation;
```

### الخطوة 1: إنشاء مجلد

اختر مجلدًا سيُحفظ فيه الباركود المُولد. استبدل `"Your Directory Path"` بمسار مطلق أو نسبي على جهازك.

```csharp
string path = "Your Directory Path";
```

### الخطوة 2: ترميز البيانات في وضع ASCII

جوهر الدرس – نقوم بإنشاء كائن `BarcodeGenerator`، ضبط إعدادات DataMatrix، تعيين وضع الترميز إلى ASCII، وأخيرًا حفظ الصورة. يوضح هذا المقتطف بالضبط كيفية **إنشاء صورة باركود برمجيًا**.

```csharp
System.Console.WriteLine("DataMatrixEncodeModeASCII:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    // Set the X-dimension (size) of the barcode in pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set the encoding mode to ASCII
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;
    
    // Save the barcode as a PNG image
    gen.Save($"{path}DataMatrixEncodeModeASCII.png", BarCodeImageFormat.Png);
}
```

عند تشغيل البرنامج، سيظهر ملف باسم `DataMatrixEncodeModeASCII.png` في المجلد الذي حددته. افتحه بأي عارض صور لتشاهد الباركود المُولد.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|--------|-----|
| **الملف غير محفوظ** | `path` يشير إلى مجلد غير موجود أو لا تملك صلاحيات الكتابة. | تأكد من وجود المجلد ومن أن تطبيقك يملك صلاحية الكتابة. |
| **الباركود غير واضح** | أبعاد X منخفضة بالنسبة لحجم البيانات. | زد قيمة `gen.Parameters.Barcode.XDimension.Pixels` (مثلاً إلى 6 أو 8). |
| **حروف غير مدعومة** | وضع ASCII يدعم فقط الحروف من 0‑127. | انتقل إلى وضع ترميز آخر (مثل Base256) إذا كنت تحتاج بيانات ثنائية. |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.BarCode لـ .NET مع لغات برمجة أخرى غير C#؟**  
ج: تدعم Aspose.BarCode عدة لغات (Java، Python، إلخ)، لكن هذا الدرس يركز على C#.

**س: ما هي أوضاع الترميز المختلفة المتاحة في باركود DataMatrix؟**  
ج: تشمل الأوضاع ASCII، C40، Text، وBase256، كل منها مُحسّن لنوع معين من البيانات.

**س: هل يمكنني تخصيص مظهر الباركود المُولد، مثل حجمه ولونه؟**  
ج: نعم، يمكنك تعديل الحجم، الألوان، الهوامش، والمزيد عبر خصائص `Parameters.Barcode`.

**س: هل توجد نسخة تجريبية مجانية من Aspose.BarCode لـ .NET؟**  
ج: نعم، يمكنك تجربة Aspose.BarCode لـ .NET بنسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).

**س: أين يمكنني شراء ترخيص لـ Aspose.BarCode لـ .NET؟**  
ج: يمكنك شراء الترخيص من موقع Aspose عبر [هنا](https://purchase.aspose.com/buy).

## الخلاصة

في هذا الدليل أظهرنا كيفية **إنشاء صورة باركود برمجيًا** باستخدام ترميز DataMatrix ASCII في Aspose.BarCode لـ .NET. ببضع أسطر من الكود يمكنك توليد باركود عالي الجودة يناسب أنظمة المخزون، ملصقات الشحن، أو أي تطبيق يتطلب بيانات مضغوطة قابلة للقراءة آليًا. لا تتردد في تجربة أوضاع ترميز أخرى، ألوان، وأحجام لتتناسب مع سيناريوك الخاص.

لمزيد من التفاصيل، راجع الوثائق الرسمية على [توثيق Aspose.BarCode لـ .NET](https://reference.aspose.com/barcode/net/) أو انضم إلى المجتمع عبر [منتدى Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**آخر تحديث:** 2026-01-20  
**تم الاختبار مع:** Aspose.BarCode 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}