---
category: general
date: 2026-08-22
description: Как изменить размер штрихкода в C# с помощью генератора DataBar Stacked
  Omni‑Directional. Узнайте, как установить X‑размер и соотношение сторон для вывода
  в PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to change barcode size
- DataBar Stacked Omni‑Directional barcode
- C# barcode generator
- barcode aspect ratio
- X‑dimension pixels
- BarCodeImageFormat PNG
language: ru
lastmod: 2026-08-22
og_description: Как изменить размер штрихкода в C# с помощью генератора DataBar Stacked
  Omni‑Directional. Следуйте пошаговому руководству, чтобы настроить X‑размер и соотношение
  сторон.
og_image_alt: Screenshot showing how to change barcode size in C#
og_title: Как изменить размер штрихкода в C# — полное руководство
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  headline: How to change barcode size in C# with DataBar Stacked
  type: TechArticle
- description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  name: How to change barcode size in C# with DataBar Stacked
  steps:
  - name: Create a DataBar Stacked Omni‑Directional barcode generator
    text: The generator object holds all barcode settings. By passing `EncodeTypes.DatabarStackedOmniDirectional`
      and sample data, you create a valid barcode ready for further customization.
  - name: Set the basic module size (X‑dimension) in pixels
    text: The X‑dimension defines the width of a single barcode module. Adjusting
      it changes the overall width and height proportionally.
  - name: Change the barcode aspect ratio to 15 and save the image
    text: The **barcode aspect ratio** controls the height‑to‑width relationship.
      An aspect ratio of 15 yields a relatively tall barcode.
  - name: Change the barcode aspect ratio to 30 and save the new image
    text: Increasing the aspect ratio to 30 makes the barcode even taller, illustrating
      the flexibility of size adjustments.
  - name: Verify the generated images
    text: Open the PNG files in any image viewer. You should see two barcodes with
      identical width (controlled by the X‑dimension) but different heights (controlled
      by the aspect ratio). If the images appear blurry, increase the X‑dimension
      pixels; if they are too tall, lower the aspect ratio.
  - name: What to explore next
    text: '* **Custom colors** – experiment with `barcodeGenerator.Parameters.Barcode.ForeColor`
      and `BackColor` to match brand guidelines. * **Different barcode types** – replace
      `EncodeTypes.DatabarStackedOmniDirectional` with `EncodeTypes.QR` or `EncodeTypes.Code128`
      to see how size parameters differ across'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Как изменить размер штрихкода в C# с помощью DataBar Stacked
url: /ru/python-java/general/how-to-change-barcode-size-in-c-with-databar-stacked/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как изменить размер штрих‑кода в C# с помощью DataBar Stacked

Если вам нужно **изменить размер штрих‑кода** в приложении .NET, это руководство покажет точные шаги с использованием генератора штрих‑кода DataBar Stacked Omni‑Directional. Вы увидите, как управлять X‑размером в пикселях, регулировать соотношение сторон штрих‑кода и сохранять результат в файл PNG.

Изменение размера штрих‑кода часто требуется, когда пространство этикетки ограничено или когда необходимо изображение более высокого разрешения для цифровых каналов. В этом учебнике рассматривается всё, что вам нужно, от инициализации генератора до создания двух изображений разного размера.

## Предварительные требования

Перед началом убедитесь, что у вас есть:

* .NET 6.0 SDK или более поздняя версия  
* Ссылка на пакет **Aspose.BarCode for .NET** в NuGet  
* Базовое знакомство с синтаксисом C#  

Дополнительная конфигурация не требуется; код работает на Windows, Linux и macOS.

## Как изменить размер штрих‑кода в C# – пошагово

Следующие разделы разбивают процесс на отдельные, переиспользуемые шаги. Каждый шаг объясняет **почему** нужен код, а не только **что** он делает.

### Шаг 1: Создать генератор штрих‑кода DataBar Stacked Omni‑Directional

Объект‑генератор хранит все настройки штрих‑кода. Передав `EncodeTypes.DatabarStackedOmniDirectional` и пример данных, вы создаёте валидный штрих‑код, готовый к дальнейшей настройке.

```csharp
// Step 1: Create a DataBar Stacked Omni‑Directional barcode generator with sample data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

*Почему это важно* – Класс **C# barcode generator** инкапсулирует алгоритм кодирования. Начало с корректного генератора гарантирует, что последующие изменения размера будут применяться к правильному типу штрих‑кода.

### Шаг 2: Установить базовый размер модуля (X‑размер) в пикселях

X‑размер определяет ширину отдельного модуля штрих‑кода. Его изменение пропорционально меняет общую ширину и высоту.

```csharp
// Step 2: Define the basic module size (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Почему это важно* – Большой X‑размер даёт более крупный штрих‑код, что полезно для принтеров с низким разрешением. Маленькое значение создаёт компактный штрих‑код, подходящий для небольших этикеток.

### Шаг 3: Изменить соотношение сторон штрих‑кода на 15 и сохранить изображение

**Соотношение сторон штрих‑кода** контролирует отношение высоты к ширине. Значение 15 даёт относительно высокий штрих‑код.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

*Почему это важно* – Разные сканирующие устройства имеют оптимальные требования к соотношению сторон. Установка значения 15 демонстрирует, как **изменить размер штрих‑кода**, изменяя высоту при фиксированном X‑размере.

#### Ожидаемый результат

Файл `DatabarAspectRatio15.png` показывает DataBar Stacked Omni‑Directional штрих‑код, который выше стандартного. Ширина штрих‑кода соответствует X‑размеру 2 пикселя, а высота следует соотношению 15.

### Шаг 4: Изменить соотношение сторон штрих‑кода на 30 и сохранить новое изображение

Увеличение соотношения сторон до 30 делает штрих‑код ещё выше, демонстрируя гибкость регулировки размеров.

```csharp
// Step 4: Change the DataBar aspect ratio to 30 and save the new image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

*Почему это важно* – Поменяв значение **barcode aspect ratio**, вы мгновенно видите, как **изменить размер штрих‑кода** без создания нового генератора. Это экономит время при пакетной обработке.

#### Ожидаемый результат

Файл `DatabarAspectRatio30.png` заметно выше предыдущего изображения, подтверждая, что соотношение сторон напрямую влияет на высоту штрих‑кода.

### Шаг 5: Проверить сгенерированные изображения

Откройте PNG‑файлы в любом просмотрщике изображений. Вы должны увидеть два штрих‑кода одинаковой ширины (контролируемой X‑размером), но разной высоты (контролируемой соотношением сторон). Если изображения выглядят размытыми, увеличьте X‑размер в пикселях; если они слишком высокие, уменьшите соотношение сторон.

```csharp
// Optional verification code – load images and print dimensions
using (var img15 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio15.png"))
using (var img30 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio30.png"))
{
    Console.WriteLine($"15‑ratio size: {img15.Width}×{img15.Height}");
    Console.WriteLine($"30‑ratio size: {img30.Width}×{img30.Height}");
}
```

*Почему это важно* – Программная проверка гарантирует, что изменения размеров применены корректно, что критично для автоматизированных конвейеров сборки.

## Распространённые варианты и граничные случаи

| Ситуация | Настройка | Причина |
|-----------|------------|--------|
| **Очень маленькие этикетки** | `XDimension.Pixels = 1` и `AspectRatio = 10` | Уменьшает общий размер, сохраняя читаемость |
| **Печать высокого разрешения** | `XDimension.Pixels = 4` и `AspectRatio = 20` | Повышает плотность пикселей для чёткого вывода |
| **Другой формат изображения** | Заменить `BarCodeImageFormat.Png` на `BarCodeImageFormat.Jpeg` | Полезно, когда поддержка PNG ограничена |
| **Динамические данные** | Передать переменную строку в конструктор `BarcodeGenerator` | Автоматически генерирует штрих‑коды для каждого продукта |

Когда нужно генерировать множество штрих‑кодов разных размеров, оберните шаги в метод:

```csharp
void GenerateDatabar(string data, int xDim, int aspectRatio, string filePath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
    generator.Parameters.Barcode.XDimension.Pixels = xDim;
    generator.Parameters.Barcode.DataBar.AspectRatio = aspectRatio;
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

Вызов `GenerateDatabar("(01)98765432109876", 3, 25, "output.png")` создаёт штрих‑код с пользовательским размером одной строкой кода.

## Профессиональные советы для надёжного изменения размеров

* **Всегда задавайте X‑размер перед соотношением сторон.** Сначала изменение соотношения может привести к неожиданному масштабированию, если X‑размер остаётся по умолчанию.  
* **Используйте единый каталог вывода.** Жёстко прописывая `"YOUR_DIRECTORY"` удобно для демонстраций, но в продакшене предпочтительнее `Path.Combine(Environment.CurrentDirectory, "Barcodes")`.  
* **Проверяйте размер сгенерированного изображения.** Небольшие изменения X‑размера могут быть незаметны на экране; проверка пиксельных размеров гарантирует, что изменение вступило в силу.  

## Заключение

Теперь вы знаете **как изменить размер штрих‑кода** в C# с помощью генератора DataBar Stacked Omni‑Directional. Регулируя **X‑dimension pixels** и **barcode aspect ratio**, можно получать PNG‑изображения, подходящие под любой размер этикетки или требование к разрешению. Полный, готовый к запуску пример выше демонстрирует весь рабочий процесс от создания генератора до проверки размеров.

### Что изучать дальше

* **Пользовательские цвета** – поэкспериментируйте с `barcodeGenerator.Parameters.Barcode.ForeColor` и `BackColor`, чтобы соответствовать фирменному стилю.  
* **Другие типы штрих‑кодов** – замените `EncodeTypes.DatabarStackedOmniDirectional` на `EncodeTypes.QR` или `EncodeTypes.Code128`, чтобы увидеть, как параметры размера различаются у разных символогий.  
* **Пакетная обработка** – комбинируйте метод `GenerateDatabar` с импортом CSV для автоматического создания тысяч штрих‑кодов.

Не стесняйтесь адаптировать фрагменты кода под архитектуру вашего проекта, и позвольте настройкам размеров штрих‑кода улучшить надёжность сканирования и визуальный дизайн. Приятного кодинга!

## Что стоит изучить дальше?

Следующие учебники охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [Как настроить размер штрих‑кода – соотношение сторон Codablock F с Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Как сгенерировать Aztec‑штрих‑код с пользовательским соотношением сторон, используя Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Как генерировать и регулировать высоту штрих‑кода One‑Dimensional Databar с Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}