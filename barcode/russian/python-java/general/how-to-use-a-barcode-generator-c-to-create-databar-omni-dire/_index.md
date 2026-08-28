---
category: general
date: 2026-08-22
description: Учебник по генератору штрихкодов на C# показывает, как создавать PNG‑файлы
  штрихкодов, генерировать штрихкоды DataBar и регулировать высоту штрихкода за несколько
  шагов.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- generate barcode PNG
- create DataBar barcode
- adjust barcode height
language: ru
lastmod: 2026-08-22
og_description: Руководство по генератору штрихкодов на C# покажет, как создавать
  PNG‑штрихкоды, генерировать DataBar и эффективно регулировать высоту штрихкода.
og_image_alt: Screenshot of two DataBar Omni‑directional barcodes with different heights
  saved as PNG files
og_title: Генератор штрихкодов C# – создание штрихкодов DataBar и настройка высоты
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to generate barcode PNG files,
    create DataBar barcodes, and adjust barcode height in just a few steps.
  headline: How to use a barcode generator C# to create DataBar Omni‑directional barcodes
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Как использовать генератор штрихкодов C# для создания штрихкодов DataBar Omni‑directional
url: /ru/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как использовать генератор штрихкодов C# для создания DataBar Omni‑directional штрихкодов

Если вам нужен **barcode generator C#**, способный создавать PNG‑изображения высокого качества, это руководство вам поможет. Вы узнаете, как генерировать PNG‑файлы штрихкодов, создавать DataBar Omni‑directional штрихкод и регулировать высоту штрихкода, не выходя из IDE.

Генерация штрихкодов программно устраняет необходимость ручного использования графического редактора. К концу этого руководства у вас будет два PNG‑файла — один с высотой штриха 30 пикселей, другой с высотой 60 пикселей — готовые к включению в счета, этикетки или системы учёта запасов.

**Требования**

- .NET 6.0 или новее (код также работает с .NET Framework 4.7+)
- Ссылка на пакет NuGet `Aspose.BarCode` (или любую библиотеку, предоставляющую аналогичный API)
- Базовые знания C# и Visual Studio или вашей предпочтительной IDE

---

## Шаг 1: Настройка проекта генератора штрихкодов C#  

Создание экземпляра **barcode generator C#** — первая вещь, которую вы делаете. Конструктор принимает два аргумента: тип штрихкода (`EncodeTypes.DatabarOmniDirectional`) и данные. В этом примере данные соответствуют формату идентификатора приложения GS1 для 14‑значного GTIN.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the barcode generator for a DataBar Omni‑directional code
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

**Почему это важно:** Перечисление `EncodeTypes.DatabarOmniDirectional` указывает библиотеке отрисовывать DataBar, который можно считывать из любого направления, что идеально для небольших розничных этикеток.

---

## Шаг 2: Определение размера модуля (X‑dimension)  

X‑dimension контролирует ширину отдельного модуля штрихкода. Установка значения в 2 пикселя даёт чёткое, читаемое изображение при небольшом размере файла.

```csharp
        // Set the module (X) dimension to 2 pixels per module
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Подсказка:** Если нужен более плотный штрихкод для ограниченного пространства, уменьшите значение до 1 пикселя, но проверьте читаемость сканером.

---

## Шаг 3: Генерация первого PNG с высотой штриха 30 пикселей  

Высота штриха определяет, насколько высокими будут полосы. Высота 30 пикселей — распространённый стандарт для обычных этикеток.

```csharp
        // Set bar height to 30 pixels
        generator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image as PNG
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png",
                       BarCodeImageFormat.Png);
```

Файл `DatabarBarHeight30Pixels.png` теперь содержит **generate barcode PNG**, который можно использовать напрямую в веб‑страницах или печатать по требованию.

---

## Шаг 4: Регулировка высоты штрихкода до 60 пикселей и сохранение второго PNG  

Изменить высоту штриха так же просто, как присвоить новое значение тому же свойству. Это демонстрирует возможность **adjust barcode height** генератора.

```csharp
        // Change bar height to 60 pixels for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png",
                       BarCodeImageFormat.Png);
    }
}
```

Теперь у вас есть `DatabarBarHeight60Pixels.png`, который идеален для крупной упаковки, где штрихкод должен считываться с расстояния.

**Ожидаемый результат**

- `DatabarBarHeight30Pixels.png` – компактный DataBar Omni‑directional штрихкод, высотой 30 px.  
- `DatabarBarHeight60Pixels.png` – тот же штрихкод, удвоенный по высоте для лучшей видимости.

Оба изображения — файлы PNG, сохраняющие без потерь качество и поддерживающие прозрачность при необходимости.

---

## Как генерировать файлы штрихкодов PNG в разных форматах  

Хотя в этом руководстве акцент делается на PNG, метод `Save` принимает и другие форматы, такие как `Jpeg`, `Bmp` и `Svg`. Чтобы **how to generate barcode** файлы в другом формате, просто замените `BarCodeImageFormat.Png` на нужное значение перечисления:

```csharp
generator.Save(@"path\barcode.svg", BarCodeImageFormat.Svg);
```

Выбор SVG удобен, когда требуется векторное изображение, которое масштабируется без пикселизации.

---

## Распространённые подводные камни при **создании DataBar barcode** изображений  

| Проблема | Причина | Решение |
|----------|---------|---------|
| Штрихкод выглядит размытым | X‑dimension слишком низок для целевого разрешения | Увеличьте `XDimension.Pixels` до 3 или 4 |
| Сканер не может прочитать код | Высота штриха слишком мала для оптики сканера | Используйте минимум 30 пикселей или следуйте спецификациям сканера |
| Строка данных отклоняется | Неправильное форматирование GS1 | Убедитесь, что строка начинается с правильного идентификатора приложения, например `(01)` для GTIN‑14 |

Решение этих вопросов на ранних этапах экономит время при интеграции штрихкодов в производственные конвейеры.

---

## Продвинутый совет: Повторное использование одного генератора для нескольких штрихкодов  

Если вам нужно **generate barcode PNG** файлы для партии продуктов, переиспользуйте тот же экземпляр `BarcodeGenerator` и обновляйте только свойство `CodeText`:

```csharp
string[] gtins = { "(01)12345678901231", "(01)98765432109876" };
int[] heights = { 30, 60 };

foreach (var gtin in gtins)
{
    generator.CodeText = gtin;          // Change data payload
    foreach (var h in heights)
    {
        generator.Parameters.Barcode.BarHeight.Pixels = h;
        string fileName = $"Databar_{gtin.Substring(4)}_{h}Px.png";
        generator.Save($@"YOUR_DIRECTORY\{fileName}", BarCodeImageFormat.Png);
    }
}
```

Такой подход минимизирует накладные расходы на создание объектов и делает ваш код лаконичнее.

---

## Заключение  

Теперь у вас есть полный рабочий процесс **barcode generator C#**, который **creates DataBar barcodes**, **generates barcode PNG** файлы и позволяет **adjust barcode height** одной заменой свойства. Пример охватывает всё — от настройки проекта до обработки крайних случаев, так что вы можете уверенно интегрировать создание штрихкодов в любое .NET‑приложение.

**Следующие шаги**

- Исследуйте другие символьные наборы штрихкодов (`EncodeTypes.QR`, `EncodeTypes.Code128`), чтобы расширить решение.  
- Скомбинируйте генератор с ASP.NET Core для динамической выдачи штрихкодов через API‑конечную точку.  
- Поэкспериментируйте с цветовыми опциями (`generator.Parameters.Barcode.ForeColor`) для брендинга.

Счастливого кодинга, и пусть ваши сканирования всегда проходят быстро!

## Что вам следует изучить дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Как генерировать и регулировать высоту штрихкода для одностороннего Databar с использованием Aspose.BarCode для .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Создание 2D штрихкодов One-Dimensional Databar с помощью Aspose.BarCode .NET API](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [Как генерировать DataMatrix штрихкоды с использованием Aspose.BarCode для .NET – пошаговое руководство](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}