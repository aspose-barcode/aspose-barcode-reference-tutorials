---
date: 2026-09-28
description: Узнайте, как создать пользовательское пространство штрих‑кода для купонов
  GS1 с помощью Aspose.BarCode for .NET и повысить читаемость штрих‑кода. Следуйте
  нашему пошаговому руководству.
keywords:
- create barcode custom space
- GS1 coupon supplement
- Aspose.BarCode .NET
- increase barcode readability
lastmod: 2026-09-28
linktitle: Конфигурация пространства дополнения купона GS1
og_description: Узнайте, как создать пользовательское пространство штрих‑кода для
  купонов GS1 с помощью Aspose.BarCode for .NET и повысить читаемость штрих‑кода.
  Включены пошаговый код и советы.
og_image_alt: Screenshot of a GS1 coupon barcode generated with custom supplement
  space using Aspose.BarCode for .NET
og_title: Создание пользовательского пространства штрих‑кода для дополнения купона
  GS1 – Aspose.BarCode .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  headline: How to create barcode custom space for GS1 coupon supplement
  type: TechArticle
- description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  name: How to create barcode custom space for GS1 coupon supplement
  steps:
  - name: '**Visual Studio** – The primary IDE for .NET development.'
    text: '**Visual Studio** – The primary IDE for .NET development.'
  - name: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
  - name: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
    text: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
  - name: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
    text: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
  - name: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
    text: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
  - name: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
    text: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
  type: HowTo
- questions:
  - answer: It adds a mandatory blank margin around the supplemental data, improving
      scanner reliability and meeting retailer‑specified minimum widths.
    question: What is the purpose of the GS1 Coupon Supplement Space in barcodes?
  - answer: Yes, set `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` to any
      integer value; the library instantly applies the change to the generated image.
    question: Can I customize the width of the GS1 Coupon Supplement Space with Aspose.BarCode
      for .NET?
  - answer: Refer to the [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)
      and visit the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)
      for community assistance.
    question: Where can I find additional documentation and support for Aspose.BarCode
      for .NET?
  - answer: Absolutely. The API offers straightforward methods for quick tasks and
      advanced options for fine‑tuned barcode generation.
    question: Is Aspose.BarCode for .NET suitable for both beginners and experienced
      developers?
  - answer: Yes, request a trial license from the [Aspose temporary license website](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for Aspose.BarCode for .NET to evaluate
      its features?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- barcode configuration
- GS1 standards
- Aspose.BarCode
- .NET barcode generation
title: Как создать пользовательское пространство штрих‑кода для дополнения купона
  GS1
url: /ru/net/gs1-barcode-encoding/gs1-coupon-supplement-space-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Конфигурация пространства дополнения купона GS1

В этом руководстве вы **создадите пользовательское пространство штрих‑кода** для пространства дополнения купона GS1, используя Aspose.BarCode for .NET. Регулировка пространства дополнения необходима, когда нужно **повысить читаемость штрих‑кода** на сканерах низкого разрешения или соответствовать требованиям розничных маржей. К концу этого руководства вы поймёте, почему пространство дополнения важно, как задать его программно и как генерировать изображения с разными значениями пикселей.

## Быстрые ответы
- **Что контролирует пространство дополнения?** Оно определяет пустую область (в пикселях) между данными купона и остальной частью штрих‑кода.  
- **Какой тип штрих‑кода используется?** `EncodeTypes.UpcaGs1DatabarCoupon`.  
- **Могу ли я изменить размер пространства?** Да — установите `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` в любое целое значение.  
- **Нужна ли лицензия для этой функции?** Временная лицензия подходит для оценки; полная лицензия требуется для продакшн.  
- **Какие форматы вывода поддерживаются?** PNG, JPEG, BMP, GIF, TIFF и другие через `BarCodeImageFormat`.

## Что такое пространство дополнения купона GS1?
Пространство дополнения купона GS1 — это определённый пустой регион, который появляется в штрих‑кодах GS1‑Databar купонов. Розничные системы используют это пространство для повышения надёжности сканирования и соответствия отраслевым спецификациям, требующим минимального отступа вокруг дополнительных данных.

## Зачем настраивать пространство дополнения?
Пространство дополнения напрямую **повышает читаемость штрих‑кода** и помогает вам соответствовать строгим требованиям розничных продавцов. Добавляя дополнительные пиксели, вы снижаете вероятность ошибок чтения на сканерах низкого разрешения, обеспечиваете стабильное сканирование на этикетках разных размеров и получаете визуальную гибкость для балансировки штрих‑кода в печатном макете.

## Предварительные требования

Перед тем как приступить к настройке пространства дополнения купона GS1 с Aspose.BarCode for .NET, убедитесь, что у вас есть следующее:

1. **Visual Studio** — основной IDE для разработки на .NET.  
2. **Aspose.BarCode for .NET** — загрузите библиотеку из [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).  
3. **.NET Framework или .NET 5+** — требуется знание C# и среды выполнения .NET.

Теперь, когда среда готова, перейдём к реализации.

## Импорт пространств имён

Пространство имён `Aspose.BarCode.Generation` содержит класс `BarcodeGenerator` и связанные настройки.

```csharp
using Aspose.BarCode;
```

## Шаг 1: определить путь

Выберите папку, куда будут сохраняться сгенерированные изображения. Путь должен заканчиваться соответствующим разделителем каталогов для вашей операционной системы.

```csharp
string path = "Your Directory Path";
```

## Шаг 2: создать конфигурацию пространства дополнения купона GS1

Следующий фрагмент кода создаёт штрих‑код, задаёт X‑размер и регулирует пространство дополнения.

```csharp
System.Console.WriteLine("Gs1CouponSupplementSpace:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.UpcaGs1DatabarCoupon, "123456789012(8110)ASPOSE");
gen.Parameters.Barcode.XDimension.Pixels = 2;

// Set coupon supplement space to 30 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 30;
gen.Save($"{path}Gs1CouponSpace30Pixels.png", BarCodeImageFormat.Png);

// Set coupon supplement space to 50 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 50;
gen.Save($"{path}Gs1CouponSpace50Pixels.png", BarCodeImageFormat.Png);
```

В этом примере мы:

1. **Создаём** экземпляр `BarcodeGenerator` для типа `UpcaGs1DatabarCoupon`.  
2. **Устанавливаем** X‑размер в 2 пикселя, что определяет минимальную ширину полосы.  
3. **Регулируем** свойство `SupplementSpace.Pixels` до 30 px, генерируем изображение, затем повторяем с 50 px.  

Не стесняйтесь экспериментировать с другими значениями пикселей, чтобы подобрать их под ваш процесс печати.

## Распространённые проблемы и советы

- **Неверный путь** — убедитесь, что переменная `path` заканчивается обратным слешем (`\`) или прямым слешем (`/`), соответствующим вашей ОС.  
- **Недостаточные права** — запустите Visual Studio от имени администратора или выберите папку, где приложение имеет права записи.  
- **Неправильный формат данных** — строка данных должна соответствовать синтаксису GS1 (`(8110)` обозначает идентификатор дополнения).  

## Почему это важно для вашего бизнеса

Aspose.BarCode поддерживает **более 60 символогий штрих‑кодов** и может рендерить изображения размером до **10 000 × 10 000 пикселей** без исчерпания памяти. Для крупномасштабных розничных внедрений это означает возможность пакетной генерации высокоразрешённых купонов GS1, удерживая время обработки менее секунды на изображение на типичном серверном оборудовании.

## Часто задаваемые вопросы

**Q: Какова цель пространства дополнения купона GS1 в штрих‑кодах?**  
A: Оно добавляет обязательный пустой отступ вокруг дополнительных данных, повышая надёжность сканера и соответствуя минимальным ширинам, указанным розничными продавцами.

**Q: Могу ли я изменить ширину пространства дополнения купона GS1 с помощью Aspose.BarCode for .NET?**  
A: Да, установите `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` в любое целое значение; библиотека мгновенно применит изменение к сгенерированному изображению.

**Q: Где я могу найти дополнительную документацию и поддержку для Aspose.BarCode for .NET?**  
A: Обратитесь к [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) и посетите [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) для получения помощи от сообщества.

**Q: Подходит ли Aspose.BarCode for .NET как для начинающих, так и для опытных разработчиков?**  
A: Абсолютно. API предлагает простые методы для быстрых задач и расширенные опции для тонкой настройки генерации штрих‑кодов.

**Q: Могу ли я получить временную лицензию для Aspose.BarCode for .NET, чтобы оценить его возможности?**  
A: Да, запросите пробную лицензию на сайте [Aspose temporary license website](https://purchase.aspose.com/temporary-license/).

## Заключение

Следуя приведённым выше шагам, вы теперь знаете, как **создать пользовательское пространство штрих‑кода** для пространства дополнения купона GS1 — ключевой приём для **повышения читаемости штрих‑кода** и соответствия розничным стандартам. Интегрируйте код в существующие решения сканирования, экспериментируйте с различными значениями пикселей и изучайте другие типы штрих‑кодов, предлагаемые Aspose.BarCode for .NET.

---

**Last Updated:** 2026-09-28  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose

## Связанные руководства

- [Создание штрих‑кода Databar Aspose.BarCode с помощью .NET API – конфигурация строк и столбцов](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Как генерировать DataMatrix штрих‑коды с помощью Aspose.BarCode for .NET – пошаговое руководство](/barcode/net/datamatrix-barcode-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}