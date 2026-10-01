---
category: general
date: 2026-08-19
description: Узнайте, как генерировать PNG‑файл штрих‑кода на C# и регулировать его
  высоту, включая создание изображений штрих‑кода и простое изменение высоты штрих‑кода.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode png file
- how to generate barcode
- adjust barcode height
- change barcode height
language: ru
lastmod: 2026-08-19
og_description: Создайте PNG‑файл штрих‑кода на C# и узнайте, как генерировать изображения
  штрих‑кодов, регулировать высоту штрих‑кода и изменять её для оптимального сканирования.
og_image_alt: barcode PNG file showing Databar OmniDirectional barcode at two heights
og_title: Создайте PNG‑файл штрих‑кода в C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Learn how to generate a barcode PNG file in C# and adjust its height,
    covering how to generate barcode images and change barcode height easily.
  headline: How to create a barcode PNG file with adjustable height in C#
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`,
      `BarCodeImageFormat.Bmp`, etc.
    question: Can I generate other image formats (JPEG, BMP)?
  - answer: Serve the generated PNG via an HTTP endpoint or convert it to a Base64
      string and place it in an `<img>` tag’s `src` attribute.
    question: How do I embed the PNG in a web page?
  - answer: 'Use `generator.Parameters.Image.BackgroundColor = Color.White;` (or any
      `System.Drawing.Color`). ## Conclusion You now know how to **generate a barcode
      PNG file** in C# and precisely **adjust barcode height** to meet scanning or
      design requirements. By changing the `BarHeight.Pixels` property you ca'
    question: Is there a way to set the background color?
  type: FAQPage
tags:
- barcode
- C#
- image generation
title: Как создать PNG‑файл штрих‑кода с регулируемой высотой в C#
url: /ru/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать PNG‑файл штрих‑кода с регулируемой высотой в C#

Если вам нужно создать **PNG‑файл штрих‑кода** в C#, это руководство покажет, как это сделать. Вы увидите полностью готовый, исполняемый пример, демонстрирующий **генерацию изображений штрих‑кода** и **регулировку высоты штрих‑кода** для разных сценариев.

Создание PNG‑файла штрих‑кода — распространённая задача для систем учёта, POS‑терминалов и любых приложений, которым требуется печатать или отображать машинно‑читаемые данные. К концу этого урока вы сможете изменять высоту штрих‑кода, сохранять несколько PNG‑файлов и понимать, как высота влияет на надёжность сканирования.

## Предварительные требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 SDK или более новая версия  
* Visual Studio 2022 (или любая IDE, поддерживающая .NET)  
* NuGet‑пакет **Aspose.BarCode for .NET** (в примере используется эта библиотека)  

Пакет можно добавить из командной строки:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Бесплатная оценочная версия Aspose.BarCode подходит для разработки и тестирования. Для продакшна получите лицензионный ключ.

## Установите библиотеку штрих‑кода

Первый шаг — добавить ссылку на библиотеку в ваш проект. Добавьте следующие директивы `using` в начало вашего C#‑файла:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Эти пространства имён дают доступ к `BarcodeGenerator`, `EncodeTypes` и `BarCodeImageFormat`.

## Создайте PNG‑файл штрих‑кода

Теперь создаём экземпляр `BarcodeGenerator`, который будет выводить **PNG‑файл штрих‑кода**. В примере используется символьная система Databar OmniDirectional, но вы можете заменить `EncodeTypes.DatabarOmniDirectional` на любой поддерживаемый тип.

```csharp
// Step 1: Create a DataBar Omnidirectional generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Строка `"(01)12345678901231"` соответствует формату GS1 Application Identifier для 14‑значного GTIN. Подкорректируйте данные под свои идентификаторы продуктов.

## Установите X‑размер (необязательно)

X‑размер определяет ширину отдельного модуля штрих‑кода. Значение в пикселях даёт точный контроль над размером изображения.

```csharp
// Optional: Set the pixel size of the X‑dimension (module width)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Значение `2` пикселя хорошо подходит для большинства экранов. Увеличьте его, если нужен более крупный штрих‑код при печати.

## Регулируйте высоту штрих‑кода и сохраняйте PNG‑файл

Свойство **BarHeight** управляет вертикальным размером полос. Изменяя это значение, вы **регулируете высоту штрих‑кода** без изменения закодированных данных.

```csharp
// Step 2: Generate a 30‑pixel‑high barcode and save it as PNG
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Файл `DatabarBarHeight30Pixels.png` теперь представляет собой **PNG‑файл штрих‑кода** высотой 30 пикселей.  

Чтобы **изменить высоту штрих‑кода** и создать второе изображение, просто задайте новое значение и снова вызовите `Save`:

```csharp
// Step 3: Change the height to 60 pixels and save the new image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
barcodeGenerator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Теперь у вас есть два PNG‑файла — один высотой 30 px, другой 60 px — демонстрирующие, как **регулировать высоту штрих‑кода** «на лету».

### Почему высота полос важна

* **Читаемость:** Сканеры ожидают минимальную высоту для надёжного обнаружения. Слишком короткий штрих‑код может не считаться, особенно на камерах низкого разрешения.  
* **Эстетика:** Согласование высоты штрих‑кода с окружающими элементами дизайна делает интерфейс чище.  
* **Ограничения печати:** У некоторых принтеров этикеток фиксированные высотные слоты; регулировка высоты штрих‑кода гарантирует его размещение.

**Best practice:** Делайте высоту кратной X‑размеру (например, 30 px при X‑размере 2 px), чтобы сохранить пропорции и избежать искажений.

## Полный пример

Ниже приведена полностью автономная программа, которую можно вставить в консольное приложение и сразу запустить.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator with Databar OmniDirectional data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set a reasonable X‑dimension (module width)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First height: 30 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Second height: 60 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

**Ожидаемый результат**

Запуск программы создаёт два файла в рабочем каталоге исполняемого файла:

* `DatabarBarHeight30Pixels.png` — PNG‑файл штрих‑кода высотой 30 пикселей  
* `DatabarBarHeight60Pixels.png` — PNG‑файл штрих‑кода высотой 60 пикселей  

Откройте любой из PNG‑файлов в просмотрщике изображений — вы увидите чёткий штрих‑код Databar OmniDirectional, готовый к сканированию.

## Пограничные случаи и устранение неполадок

| Ситуация | Что проверить | Рекомендуемое решение |
|-----------|---------------|-----------------|
| Штрих‑код выглядит размытым | X‑размер слишком мал для выбранной высоты | Увеличьте `XDimension.Pixels` (например, с 2 до 3) |
| Сканер не читает штрих‑код низкой высоты | Высота ниже минимального порога сканера | Установите `BarHeight.Pixels` минимум 30 px (или согласно спецификации сканера) |
| PNG‑файл пустой или повреждён | Неправильный путь вывода или отсутствие прав записи | Используйте абсолютный путь или убедитесь, что приложение имеет права на запись |
| Требуется другая символьная система | Текущий `EncodeTypes` не подходит | Замените `EncodeTypes.DatabarOmniDirectional` на другое значение enum (например, `EncodeTypes.Code128`) |

## Часто задаваемые вопросы

**В: Можно ли генерировать другие форматы изображений (JPEG, BMP)?**  
О: Да. Замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp` и т.д.

**В: Как встроить PNG в веб‑страницу?**  
О: Отдайте сгенерированный PNG через HTTP‑endpoint или преобразуйте его в строку Base64 и поместите в атрибут `src` тега `<img>`.

**В: Можно ли задать цвет фона?**  
О: Используйте `generator.Parameters.Image.BackgroundColor = Color.White;` (или любой `System.Drawing.Color`).

## Заключение

Теперь вы знаете, как **генерировать PNG‑файл штрих‑кода** в C# и точно **регулировать высоту штрих‑кода** под требования сканирования или дизайна. Изменяя свойство `BarHeight.Pixels`, вы можете **изменять высоту штрих‑кода** «на лету» и создавать несколько PNG‑ресурсов из одного кода.

Далее изучайте другие варианты настройки, такие как цвет штрихов, отступы и добавление человекочитаемого текста. Вы также можете экспериментировать с различными символьными системами (`EncodeTypes.Code128`, `EncodeTypes.QR`), расширяя диапазон кодируемых данных.

Удачной разработки, и пусть ваши штрих‑коды всегда сканируются с первой попытки!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}