---
date: 2026-06-09
description: تعلم كيفية إنشاء باركود datamatrix باستخدام Aspose.BarCode لـ .NET، وتخصيص
  نسب الأبعاد، وأنماط ECC، وترميز datamatrix c40 لإنشاء باركود فعال.
keywords:
- generate datamatrix barcode
- datamatrix c40 encoding
- aspose barcode .net
- datamatrix ecc modes
- barcode aspect ratio
linktitle: تكوين باركود DataMatrix
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  headline: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  name: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  steps:
  - name: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
    text: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
  - name: '**Adjust** `AspectRatio` to your desired value.'
    text: '**Adjust** `AspectRatio` to your desired value.'
  - name: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
    text: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
  type: HowTo
- questions:
  - answer: Choose ECC 000‑140 for small data sets with limited error correction,
      or ECC 200 for larger data and higher reliability. Macro mode adds an extra
      data layer for linking.
    question: How do I decide which ECC mode to use?
  - answer: Yes, set the `CodeText` property to your custom string, then select the
      appropriate encoding mode (ASCII, C40, etc.) to control size.
    question: Can I embed custom text in a DataMatrix barcode?
  - answer: Set `EncodeMode` to `Auto`; Aspose.BarCode evaluates the payload and picks
      the most space‑efficient mode automatically.
    question: Is there a way to automatically select the best encoding mode?
  - answer: Reuse a single `BarCodeGenerator` instance, enable multi‑threading, and
      generate PNG images for lossless quality or JPEG for smaller file size. Processing
      10 000 symbols typically completes in under 30 seconds on a standard 8‑core
      server.
    question: What are the performance considerations for large barcode batches?
  - answer: Absolutely – the library is fully compatible with .NET Framework, .NET
      Core, and the latest .NET releases, offering the same feature set across all
      platforms.
    question: Does Aspose.BarCode support .NET Core and .NET 5/6?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: إنشاء باركود DataMatrix – دليل احترافي مع Aspose.BarCode
url: /ar/net/datamatrix-barcode-configuration/
weight: 30
---

{{< blocks/products/pf/main-container >}}
{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء باركود DataMatrix – دليل محترف مع Aspose.BarCode

مرحبًا بكم في سلسلة الدروس الشاملة حول **إنشاء باركود DataMatrix** باستخدام Aspose.BarCode لـ .NET. سواء كنت مطورًا متمرسًا يقوم بضبط مخرجات الباركود أو مبتدئًا حريصًا على فهم الأساسيات، فإن هذا الدليل يرافقك في كل خطوة — من الإعداد الأساسي إلى تقنيات الترميز المتقدمة — لتتمكن من تقديم باركود موثوق وجاهز للمسح في أي تطبيق .NET.

## إجابات سريعة
- **ما هو الهدف الأساسي؟** لإنشاء وتخصيص باركودات DataMatrix برمجيًا.  
- **ما المكتبة المستخدمة؟** Aspose.BarCode لـ .NET.  
- **هل أحتاج إلى ترخيص؟** يتوفر نسخة تجريبية مجانية؛ يتطلب الترخيص التجاري للاستخدام في الإنتاج.  
- **الإصدارات المدعومة من .NET؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.  
- **هل يمكنني تخصيص نسبة الأبعاد؟** نعم — راجع قسم “How to customize DataMatrix aspect ratio”.

## ما هو باركود DataMatrix؟
باركود DataMatrix هو مصفوفة ثنائية الأبعاد من الخلايا السوداء والبيضاء يمكنها تخزين ما يصل إلى 2 300 حرف أبجدي رقمي. باستخدام Aspose.BarCode، يمكنك **إنشاء باركود DataMatrix** كصور، ملفات PDF أو SVG مباشرةً من كود .NET الخاص بك، مع التحكم في الحجم، مستوى تصحيح الأخطاء، ووضع الترميز لتلبية أي معيار صناعي.

## لماذا نستخدم Aspose.BarCode لـ DataMatrix؟
يقوم Aspose.BarCode بعرض رموز DataMatrix بدقة تصل إلى **600 dpi** دون بكسلة، مما يضمن مسحًا واضحًا على الطابعات عالية الدقة. يدعم **جميع أوضاع ECC والماكرو التي تزيد عن 50** — بما في ذلك ECC 000‑140، ECC 200، وMacro 05/06 — بحيث يمكنك اختيار مستوى تصحيح الأخطاء الأمثل لحجم بياناتك. توفر الـ API خيارات ترميز **ASCII، C40، Text، X12، وBytes**، مما يتيح لك ضغط البيانات بكفاءة. يتطلب التكامل حزمة NuGet واحدة فقط ولا يحتاج إلى مكتبات أصلية خارجية.

## كيفية تخصيص نسبة أبعاد DataMatrix
خاصية `AspectRatio` في `BarCodeGenerator` تتحكم في نسبة العرض إلى الارتفاع لرمز DataMatrix المُولد. `BarCodeGenerator` هي الفئة الرئيسية في Aspose.BarCode المستخدمة لإنشاء صور الباركود.  

**الإجابة المباشرة:** اضبط `generator.Parameters.Barcode.DataMatrix.AspectRatio = 1.2` (أو أي قيمة بين 0.5 و 2.0) قبل استدعاء `GenerateBarCodeImage()`. تقوم المكتبة تلقائيًا بإعادة حساب حجم الوحدة للحفاظ على موثوقية المسح مع الالتزام بالنسبة المطلوبة.

### خطوة بخطوة
1. **إنشاء** `BarCodeGenerator` باستخدام `EncodeTypes.DataMatrix`.  
2. **ضبط** `AspectRatio` إلى القيمة المطلوبة.  
3. **إنشاء** الصورة والتحقق منها باستخدام ماسح ضوئي أو القارئ المدمج في Aspose.

## كيفية إنشاء باركود DataMatrix ECC 000‑140
ECC 000‑140 مثالي لسلاسل البيانات القصيرة التي تتطلب رمزًا مدمجًا، حيث يقدم ما يصل إلى 140 كلمة تصحيح خطأ. `DataMatrixEccMode.Ecc000140` يختار نظام تصحيح الأخطاء ECC 000‑140 لباركود DataMatrix.  

**الإجابة المباشرة:** استخدم `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc000140` قبل التصيير. هذا يبدل المشفر إلى خوارزمية ECC 000‑140، منتجًا أصغر مصفوفة ممكنة للبيانات المعطاة مع الحفاظ على تصحيح أخطاء قوي.

### نصيحة عملية
عند ترميز بيانات رقمية أقل من 20 حرفًا، غالبًا ما ينتج ECC 000‑140 مصفوفة 10 × 10، مما يوفر مساحة قيمة على الملصق.

## كيفية إنشاء باركود DataMatrix ECC 200
ECC 200 هو الوضع الأكثر انتشارًا لباركود DataMatrix، يدعم ما يصل إلى 2 335 حرفًا أبجديًا رقميًا ويقدم تصحيح أخطاء متفوق. `DataMatrixEccMode.Ecc200` يختار نظام تصحيح الأخطاء ECC 200 لباركود DataMatrix.  

**الإجابة المباشرة:** اضبط `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc200` وقدم البيانات عبر `CodeText`. تقوم المكتبة بعد ذلك باختيار حجم المصفوفة الأمثل تلقائيًا.

### متى يُفضَّل ECC 200
استخدم ECC 200 للسلاسل الطويلة، البيانات المختلطة، أو عندما تحتاج إلى أعلى مستوى من المقاومة للضرر — يمكن استعادة ما يصل إلى **30 %** من الرمز.

## كيفية إتقان ترميز DataMatrix في ASCII
وضع ASCII يرمز الأحرف باستخدام بايت واحد لكل حرف، مما يجعله الأكثر كفاءة في استهلاك المساحة للنص العادي. `DataMatrixEncodeMode.Ascii` يوجه المولد لاستخدام ترميز ASCII لرمز DataMatrix.  

**الإجابة المباشرة:** عيّن `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Ascii` وضع `CodeText` إلى السلسلة ASCII الخاصة بك. يقوم المحرك بتجميع البيانات دون أي عبء إضافي، منتجًا أصغر مصفوفة ممكنة للمحتوى ASCII النقي.

### سيناريو مثال
رمز SKU في المستودع المكوّن من أحرف كبيرة وأرقام (مثال: “AB1234”) يناسب وضع ASCII تمامًا، وغالبًا ما ينتج مصفوفة 12 × 12.

## كيفية إنشاء وضع DataMatrix (Auto)
وضع Auto يسمح لـ Aspose.BarCode بتحليل المدخلات واختيار الترميز الأكثر كفاءة تلقائيًا (ASCII، C40، Text، X12، أو Bytes). `DataMatrixEncodeMode.Auto` يفعّل ميزة الاختيار التلقائي هذه.  

**الإجابة المباشرة:** اضبط `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Auto`. تقوم المكتبة بتقييم البيانات، تختار الوضع الأمثل، وتُنشئ الباركود في خطوة واحدة.

### الفوائد
وضع Auto يقلل من جهد التطوير ويضمن أصغر رمز ممكن للبيانات المختلطة، مما يحسن سرعة المسح.

## كيفية استخدام وضع ترميز DataMatrix (Bytes)
وضع Bytes مصمم للبيانات الثنائية، مثل الحمولات المشفرة أو الملفات المضغوطة. `DataMatrixEncodeMode.Bytes` يوجه المولد لمعالجة كل بايت كبيانات خام.  

**الإجابة المباشرة:** استخدم `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Bytes` وقدم سلسلة مشفرة Base64 كـ `CodeText`. يتعامل المشفر مع كل بايت كبيانات خام، محافظًا على التمثيل الثنائي الدقيق.

### حالة استخدام
إدراج GUID بطول 128 بت أو رمز مشفر صغير مباشرةً داخل رمز DataMatrix.

## كيفية إتقان وضع ترميز DataMatrix (C40)
وضع C40 يضغط البيانات الأبجدية الرقمية الكبيرة، محققًا تقليلًا في الحجم يصل إلى **40 %** مقارنةً بـ ASCII. `DataMatrixEncodeMode.C40` يفعّل هذا الخوارزمية الضاغطة.  

**الإجابة المباشرة:** اضبط `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.C40` وقدم سلسلة بأحرف كبيرة (مثال: “HELLO WORLD”). يقوم المحرك بتجميع ثلاثة أحرف في كلمتين رمزيتين، مما يقلص المصفوفة النهائية.

### نصيحة احترافية
يعمل C40 بأفضل شكل عندما يتكون الحمولة أساسًا من أحرف كبيرة، أرقام، ومسافات. بالنسبة للبيانات المختلطة، يُنصح باستخدام وضع Auto.

## كيفية تكوين نص رمز DataMatrix
خاصية `CodeText` تحدد البيانات الدقيقة المخزنة في الباركود. يمكن أن تشمل نصًا عاديًا، سلاسل رقمية، أو حتى حمولة XML. `CodeText` هي الخاصية النصية الأساسية في `BarCodeGenerator` التي تحتفظ بحمولة الباركود.  

**الإجابة المباشرة:** عيّن `generator.Parameters.Barcode.CodeText = "YourDataHere"` قبل التصيير. تقبل الخاصية أي سلسلة UTF‑8 حتى الحد الأقصى للطول المدعوم من وضع ECC المختار.

### نصيحة متقدمة
اجمع `CodeText` مع `ExtendedDataMatrix` لإدراج بيانات تعريفية إضافية دون زيادة حجم المصفوفة الظاهرة.

## كيفية إتقان تكوين ماكرو DataMatrix
أوضاع الماكرو (Macro 05 و Macro 06) تسمح لك بإدراج رمز DataMatrix ثانوي داخل الرمز الأساسي، وهو مفيد للربط بمصادر بيانات خارجية. `DataMatrixMacroMode.Macro05` و `DataMatrixMacroMode.Macro06` تفعّلان هذه الميزات.  

**الإجابة المباشرة:** فعّل وضع الماكرو باستخدام `generator.Parameters.Barcode.DataMatrix.MacroMode = DataMatrixMacroMode.Macro05` (أو `Macro06`) واضبط خصائص `MacroPdf417` للحمولة الثانوية. ينشئ المولد رمزًا مركبًا يمكن للماسحات قراءته كرمزين مرتبطين.

### مثال واقعي
إدراج عنوان URL في الجزء الماكرو مع الحفاظ على معرفات المنتج في المصفوفة الأساسية، مما يتيح تكاملًا سلسًا بين الويب والباركود.

*قائمة دروس Aspose.BarCode لـ .NET*

## دروس تكوين باركود DataMatrix
### [تخصيص نسبة أبعاد DataMatrix](./datamatrix-aspect-ratio-customization/)
تعرف على كيفية تخصيص نسب أبعاد باركود DataMatrix باستخدام Aspose.BarCode لـ .NET. دليل خطوة بخطوة لإنشاء الباركود.
### [إنشاء باركود DataMatrix ECC 000-140](./datamatrix-ecc-000-140-configuration/)
أنشئ باركود DataMatrix ECC 000-140 بسهولة باستخدام Aspose.BarCode لـ .NET. عزّز الكفاءة في إدارة المخزون وأكثر.
### [إنشاء باركود DataMatrix ECC 200](./datamatrix-ecc-200-configuration/)
تعرف على كيفية إنشاء باركود DataMatrix ECC 200 في .NET باستخدام Aspose.BarCode. سهل العمليات من خلال إنشاء باركود فعال.
### [إتقان ترميز DataMatrix في ASCII](./datamatrix-encoding-mode-ascii/)
تعلم إنشاء باركود DataMatrix في وضع ASCII باستخدام Aspose.BarCode لـ .NET. دليل خطوة بخطوة للمطورين.
### [إنشاء وضع DataMatrix (Auto)](./datamatrix-encoding-mode-auto/)
تعرف على كيفية إنشاء وضع DataMatrix (Auto) باستخدام Aspose.BarCode لـ .NET. يغطي هذا الدليل خطوة بخطوة كل شيء من المتطلبات المسبقة إلى قراءة الباركود.
### [وضع ترميز DataMatrix (Bytes)](./datamatrix-encoding-mode-bytes/)
تعرف على كيفية ترميز البيانات بصيغة DataMatrix باستخدام وضع Bytes مع Aspose.BarCode لـ .NET. اتبع دليلنا خطوة بخطوة لإنشاء الباركود والتعرف عليه.
### [إتقان وضع ترميز DataMatrix (C40)](./datamatrix-encoding-mode-c40/)
تعلم وضع ترميز DataMatrix (C40) باستخدام Aspose.BarCode لـ .NET. أنشئ باركودات مخصصة بفعالية. استكشف دليل خطوة بخطوة.
### [تكوين نص رمز DataMatrix](./datamatrix-extended-code-text-configuration/)
تعلم تكوين نص رمز DataMatrix الموسع باستخدام Aspose.BarCode لـ .NET. أنشئ، تعرف، ودمج الباركودات في تطبيقات .NET الخاصة بك.
### [إتقان تكوين ماكرو DataMatrix](./datamatrix-macro-configuration/)
تعرف على كيفية تكوين باركودات DataMatrix Macro باستخدام Aspose.BarCode لـ .NET. أنشئ، خصص، وتعرف على باركودات DataMatrix في تطبيقات .NET الخاصة بك.

## الأسئلة المتكررة

**س: كيف أقرر أي وضع ECC أستخدم؟**  
ج: اختر ECC 000‑140 لمجموعات البيانات الصغيرة مع تصحيح أخطاء محدود، أو ECC 200 للبيانات الأكبر وموثوقية أعلى. يضيف وضع الماكرو طبقة بيانات إضافية للربط.

**س: هل يمكنني تضمين نص مخصص في باركود DataMatrix؟**  
ج: نعم، اضبط خاصية `CodeText` إلى السلسلة المخصصة الخاصة بك، ثم اختر وضع الترميز المناسب (ASCII، C40، إلخ) للتحكم في الحجم.

**س: هل هناك طريقة لاختيار وضع الترميز الأنسب تلقائيًا؟**  
ج: اضبط `EncodeMode` إلى `Auto`؛ يقوم Aspose.BarCode بتقييم الحمولة واختيار الوضع الأكثر كفاءة في استهلاك المساحة تلقائيًا.

**س: ما هي اعتبارات الأداء عند إنشاء دفعات كبيرة من الباركود؟**  
ج: أعد استخدام نسخة واحدة من `BarCodeGenerator`، فعّل المعالجة المتعددة الخيوط، وأنشئ صور PNG لجودة غير مضيفة أو JPEG لحجم ملف أصغر. عادةً ما يكتمل معالجة 10 000 رمز في أقل من 30 ثانية على خادم قياسي بثمانية أنوية.

**س: هل يدعم Aspose.BarCode .NET Core و .NET 5/6؟**  
ج: بالتأكيد — المكتبة متوافقة تمامًا مع .NET Framework، .NET Core، وأحدث إصدارات .NET، وتقدم نفس مجموعة الميزات عبر جميع المنصات.

**آخر تحديث:** 2026-06-09  
**تم الاختبار باستخدام:** Aspose.BarCode 24.12 for .NET  
**المؤلف:** Aspose

## دروس ذات صلة
- [كيفية إنشاء باركود DataMatrix (ECC 200) باستخدام Aspose.BarCode لـ .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [إتقان ترميز DataMatrix في ASCII باستخدام Aspose.BarCode لـ .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [إنشاء PNG للباركود – نسبة أبعاد DataMatrix – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)

{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/pf/main-wrap-class >}}