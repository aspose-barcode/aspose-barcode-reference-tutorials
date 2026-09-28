---
category: general
date: 2026-07-15
description: Учебник по созданию многослойного всенаправленного штрихкода Databar
  в C#. Узнайте, как генерировать Databar, задавать соотношение сторон и использовать
  генератор штрихкодов C# для идеальных результатов.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar stacked omnidirectional
- barcode generator c#
- how to set aspect ratio
- how to generate databar
- create databar barcode
language: ru
lastmod: 2026-07-15
og_description: Объяснение штрихкода Databar Stacked Omnidirectional на C#. Следуйте
  этому пошаговому руководству, чтобы создать Databar, настроить соотношение сторон
  и освоить генератор штрихкодов на C#.
og_image_alt: Two PNG images showing a databar stacked omnidirectional barcode with
  aspect ratios 15 and 30
og_title: Databar stacked omnidirectional barcode – руководство по C#
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: databar stacked omnidirectional barcode in C# tutorial. Learn how to
    generate databar, set aspect ratio, and use a barcode generator c# for perfect
    results.
  headline: databar stacked omnidirectional barcode in C# – Complete Guide
  type: TechArticle
- description: databar stacked omnidirectional barcode in C# tutorial. Learn how to
    generate databar, set aspect ratio, and use a barcode generator c# for perfect
    results.
  name: databar stacked omnidirectional barcode in C# – Complete Guide
  steps:
  - name: The **X‑Dimension** isn’t too low (below 1 pixel is impossible).
    text: The **X‑Dimension** isn’t too low (below 1 pixel is impossible).
  - name: The **AspectRatio** matches what your scanning hardware expects.
    text: The **AspectRatio** matches what your scanning hardware expects.
  - name: The **output path** is writable—sometimes `UnauthorizedAccessException`
      hides behind a silent failure.
    text: The **output path** is writable—sometimes `UnauthorizedAccessException`
      hides behind a silent failure.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Databar Stacked Omnidirectional штрих‑код в C# – Полное руководство
url: /ru/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# databar stacked omnidirectional barcode в C# – Полное руководство

Задумывались ли вы когда‑нибудь, как задать соотношение сторон при работе с **databar stacked omnidirectional barcode** в C#? Вы не одиноки. Многие разработчики сталкиваются с трудностями, пытаясь точно настроить эти штрих‑коды для розничных или логистических этикеток, а документация часто оставляет желать лучшего.  

В этом руководстве мы пройдемся по **how to generate databar**, настроим X‑Dimension и — самое главное — **how to set aspect ratio**, чтобы сканер считывал его без ошибок. К концу вы получите готовый к запуску пример кода, который создаст два изображения штрих‑кода рядом: одно с соотношением сторон 15, другое — 30. Никаких загадок, только четкие шаги.

## Что покрывает это руководство

- Настройка **barcode generator c#** с использованием популярной библиотеки Aspose.BarCode.  
- Понимание структуры символа **databar stacked omnidirectional**.  
- Настройка **aspect ratio** в соответствии со спецификациями GS1.  
- Сохранение результата в виде PNG‑файлов, которые можно добавить в любой проект .NET.  

Требования? Просто актуальный .NET SDK (4.6+ или .NET Core 3.1+) и ссылка NuGet на `Aspose.BarCode`. Если они у вас есть, можно начинать.

---

## Понимание databar stacked omnidirectional barcode

Формат **databar stacked omnidirectional** упаковывает 14‑значный GTIN и несколько дополнительных цифр в компактный двухстрочный символ. Это предпочтительный выбор для небольших товаров, где пространство ограничено — например, косметика, фармацевтика или крошечные упаковки снеков.

Почему важен aspect ratio? Спецификация штрих‑кода определяет соотношение ширины к высоте, которое влияет на надежность сканирования. Слишком сжатый код может не быть прочитан сканером; слишком растянутый может выйти за пределы этикетки. Свойство `AspectRatio` объекта `DataBar` позволяет точно отрегулировать этот баланс.

---

## Шаг 1: Создать генератор штрих‑кода **databar stacked omnidirectional**

Сначала запустим генератор с правильным типом кодирования и данными, которые нужно внедрить. Здесь мы используем пример GTIN‑14, заключённый в скобки, как того требует спецификация.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Initialize the generator for a DataBar Stacked Omnidirectional barcode
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

> **Pro tip:** Строка должна начинаться с “(01)”, чтобы сообщить библиотеке, что последующие 14 цифр являются GTIN. Пропуск скобок приводит к `ArgumentException`.

---

## Шаг 2: Define the basic size of the bars (X‑Dimension)

X‑Dimension контролирует, сколько пикселей занимает каждый модуль (самый маленький бар). Обычной отправной точкой является 2 пикселя на модуль, что обеспечивает хороший компромисс между читаемостью и размером файла.

```csharp
// Set 2 pixels per module – a safe default for most printers
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Если вы печатаете на высоко‑разрешающем лазерном принтере, можно увеличить значение до 3 или 4 пикселей. Просто помните: больший X‑Dimension → большие общие размеры штрих‑кода.

---

## Шаг 3: **How to set aspect ratio** – первая версия (15)

Теперь часть, которая ставит многих в тупик: `AspectRatio`. Это простое целое число, но оно напрямую влияет на высоту стековых строк относительно ширины.

```csharp
// Aspect ratio of 15 – the default for many retail scenarios
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;

// Save the first image
barcodeGenerator.Save(@"YOUR_DIRECTORY\DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Полученный PNG будет выглядеть примерно так (заполнитель изображения):

![databar stacked omnidirectional barcode с соотношением сторон 15](databar_aspect_ratio_15.png)

*Текст alt изображения (для SEO):* **databar stacked omnidirectional barcode с соотношением сторон 15**.

---

## Шаг 4: **How to set aspect ratio** – вторая версия (30)

Иногда требуется более высокое соотношение, особенно когда высота этикетки достаточна или сканер ожидает более высокий символ. Переключаемся на 30 и сохраняем второй файл.

```csharp
// Change the aspect ratio to 30 for a taller barcode
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;

// Save the second image
barcodeGenerator.Save(@"YOUR_DIRECTORY\DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

И результат:

![databar stacked omnidirectional barcode с соотношением сторон 30](databar_aspect_ratio_30.png)

*Текст alt изображения:* **databar stacked omnidirectional barcode с соотношением сторон 30**.

Вы заметите, что бары стали выше, но ширина осталась той же, поскольку X‑Dimension не менялся.

---

## Шаг 5: Проверка вывода – быстрая проверка

Откройте оба PNG‑файла в любом просмотрщике изображений. Оба должны показывать чистый двухстрочный штрих‑код с одинаковыми числовыми данными. Если под рукой есть ручной сканер, попробуйте отсканировать каждый файл. Сканер должен вернуть исходную строку GTIN `(01)12345678901231`.  

Если сканирование не удалось, проверьте:

1. **X‑Dimension** не слишком низок (меньше 1 пикселя невозможно).  
2. **AspectRatio** соответствует ожиданиям вашего сканирующего оборудования.  
3. **output path** доступен для записи — иногда `UnauthorizedAccessException` скрывается за молчаливой ошибкой.

---

## Распространённые подводные камни при **create databar barcode**

| Симптом | Вероятная причина | Исправление |
|---------|-------------------|-------------|
| Сохранено пустое изображение | `EncodeTypes` не совпадает (например, используется `DatabarExpanded` вместо `DatabarStackedOmniDirectional`) | Проверьте `EncodeTypes.DatabarStackedOmniDirectional` |
| Штрих‑код слишком широкий | X‑Dimension установлен слишком высоким | Уменьшите `XDimension.Pixels` |
| Сканер сообщает «недопустимый формат» | Aspect ratio не поддерживается моделью сканера | Отрегулируйте `AspectRatio` до 15 или 30 согласно спецификациям устройства |
| Исключение при `Save` | Папка вывода отсутствует или нет прав на запись | Создайте папку или запустите с повышенными правами |

---

## Продвинуто: Динамический выбор соотношения сторон

В реальных приложениях может потребоваться выбирать соотношение сторон в зависимости от размера этикетки. Ниже небольшая вспомогательная функция, которая выбирает 15 для узких этикеток и 30 для высоких.

```csharp
private static int ChooseAspectRatio(int labelWidthPx, int labelHeightPx)
{
    // Simple heuristic: if height > 2× width, use a taller ratio
    return (labelHeightPx > 2 * labelWidthPx) ? 30 : 15;
}

// Usage
int chosenRatio = ChooseAspectRatio(200, 500);
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = chosenRatio;
barcodeGenerator.Save(@"YOUR_DIRECTORY\DatabarDynamic.png", BarCodeImageFormat.Png);
```

Теперь ваш **barcode generator c#** адаптируется «на лету» — нет необходимости хард‑кодировать два отдельных сохранения.

---

## Итоги – чего мы достигли

- **Создан** генератор штрих‑кода **databar stacked omnidirectional** в C#.  
- **Задано** X‑Dimension = 2 пикселя на модуль для чёткого отображения.  
- **Продемонстрировано**, как **set aspect ratio** до 15 и 30, сохраняя каждый в PNG.  
- **Исследованы** распространённые ошибки и предложен небольшой помощник для динамического выбора соотношения.

Всё это помещено в один самостоятельный файл, который можно добавить в любой проект .NET. Никаких внешних скриптов, никаких загадочных файлов конфигурации.

---

## Что дальше? Расширьте свой набор инструментов для штрих‑кодов

Теперь, когда вы освоили основы **create databar barcode**, рассмотрите следующие возможности:

- **Добавление читаемого человеком текста** под символом (`barcodeGenerator.Parameters.Barcode.CodeTextParameters.ShowCodeText = true`).  
- **Встраивание штрих‑кода** напрямую в PDF с помощью `Aspose.Pdf` для генерации счетов.  
- **Пакетная обработка** списка GTIN‑ов с помощью цикла `foreach` и именования каждого файла по коду продукта.  

Каждая из этих тем опирается на те же базовые концепции, которые вы только что изучили, и сделает ваши проекты **barcode generator c#** ещё более мощными.

---

### Финальные мысли

Генерация **databar stacked omnidirectional** штрих‑кода в C# — это не магия, а лишь несколько настроек свойств в надёжной библиотеке. Управляя X‑Dimension и **aspect ratio**, вы полностью контролируете форму штрих‑кода и его надёжность сканирования.  

Запустите код, поиграйте с числами и наблюдайте, как сканер «танцует». Если возникнут проблемы, вернитесь к таблице «Распространённые подводные камни» — обычно всё решается быстрой правкой свойства.  

Счастливого кодинга, и пусть ваши этикетки всегда сканируются с первой попытки!

## Что вы можете изучить дальше?

- [Настроить соотношение сторон databar stacked omnidirectional в .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)
- [Регулировка высоты одностороннего Databar штрих‑кода](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Создать изображение штрих‑кода – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}