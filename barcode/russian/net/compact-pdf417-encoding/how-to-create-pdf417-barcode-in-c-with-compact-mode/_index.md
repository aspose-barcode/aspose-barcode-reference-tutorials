---
category: general
date: 2026-09-10
description: Создайте штрих‑код PDF417 на C# быстро. Узнайте, как включить компактный
  режим, задать количество столбцов и сгенерировать PNG с помощью BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- enable compact mode
- barcode generator C#
- how to generate barcode
- how to set columns
language: ru
lastmod: 2026-09-10
og_description: Создайте штрих‑код PDF417 на C#, включив компактный режим, задав количество
  столбцов и сохранив его в формате PNG. Следуйте полному пошаговому руководству.
og_image_alt: Screenshot of a compact PDF417 barcode generated with C#
og_title: Создание штрихкода PDF417 в C# – руководство по компактному режиму
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create PDF417 barcode in C# quickly. Learn how to enable compact mode,
    set columns, and generate a PNG with BarcodeGenerator.
  headline: How to create PDF417 barcode in C# with compact mode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Как создать штрих‑код PDF417 в C# в компактном режиме
url: /ru/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать штрих‑код PDF417 в C# с компактным режимом

Если вам нужно **создать штрих‑код PDF417** в приложении .NET, это руководство покажет, как это сделать. Вы увидите, как **включить компактный режим**, задать количество столбцов и сохранить результат в виде PNG‑изображения с помощью библиотеки BarcodeGenerator для C#.

Создание штрих‑кода — распространённая задача для учёта запасов, систем билетов и мобильных сканирующих приложений. К концу этого руководства у вас будет автономный, готовый к запуску пример, генерирующий компактный штрих‑код PDF417, готовый к использованию в продакшене.

## Prerequisites

Перед тем как начать, убедитесь, что у вас есть:

* .NET 6.0 или более поздняя версия (код также работает с .NET Framework 4.7+)
* Последняя версия библиотеки **BarcodeGenerator** (например, Aspose.BarCode for .NET)
* IDE или редактор, такой как Visual Studio 2022 или VS Code
* Права записи в папку, куда будет сохраняться PNG

Дополнительные пакеты NuGet не требуются, кроме самой библиотеки штрих‑кодов.

## Step 1: Create a PDF417 barcode generator

Первый шаг — создать объект `BarcodeGenerator` с перечислением `EncodeTypes.Pdf417` и текстом, который нужно закодировать. Этот объект управляет всем процессом генерации.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

*Почему это важно*: Значение `EncodeTypes.Pdf417` указывает библиотеке использовать символьную систему PDF417, а второй аргумент передаёт полезную нагрузку. Вы можете заменить `"Compact mode"` любой другой алфавитно‑цифровой строкой, которую нужно закодировать.

## Step 2: Set the X dimension (module width)

Размер X определяет ширину каждого маленького квадратика (модуля) в штрих‑коде. Меньшие значения дают более плотное изображение, что полезно при ограниченном пространстве.

```csharp
// Step 2: Set the X dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Значение `2` пикселя — хороший компромисс между читаемостью и компактностью для большинства сканеров, работающих с экранами.

## Step 3: Define the number of columns

PDF417 может размещать данные в сетке строк и столбцов. Изменение количества столбцов меняет соотношение сторон штрих‑кода.

```csharp
// Step 3: Define the number of columns for the PDF417 barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

Установка **how to set columns** в `3` даёт короткий, широкий штрих‑код, который удобно размещать на этикетке. Вы можете экспериментировать со значениями от `1` до `30` в зависимости от объёма данных и целевого сканера.

## Step 4: Enable compact mode

Компактный режим удаляет лишние строки‑заполнители, делая штрих‑код меньше без потери целостности данных. Это ключевой шаг для **компактного PDF417**.

```csharp
// Step 4: Enable compact mode by truncating the barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

Когда `Truncate` установлен в `true`, библиотека автоматически рассчитывает минимальное количество строк, необходимых для хранения данных, поэтому итоговое изображение выглядит «плотным».

## Step 5: Save the generated barcode as a PNG image

Наконец, сохраняем штрих‑код в файл. PNG сохраняет чёткие края, необходимые для надёжного сканирования.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Замените `YOUR_DIRECTORY` на абсолютный или относительный путь, в который ваше приложение может записывать файлы. После выполнения вы найдёте файл `CompactPdf417.png`, содержащий штрих‑код.

### Full source code

Объединив все шаги, получаем готовую к запуску программу:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

        // Set the X dimension (module width) in pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the number of columns for the PDF417 barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;

        // Enable compact mode by truncating the barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("CompactPdf417.png", BarCodeImageFormat.Png);

        Console.WriteLine("PDF417 barcode created successfully.");
    }
}
```

Запуск этой программы создаёт `CompactPdf417.png` в той же папке, где находится исполняемый файл. Откройте изображение в любом просмотрщике — вы увидите плотный, контрастный штрих‑код PDF417, готовый к сканированию.

## How to enable compact mode in other scenarios

* **Batch generation** – При создании большого количества штрих‑кодов установите `Truncate` один раз у генератора и переиспользуйте его для каждой новой полезной нагрузки.
* **Different image formats** – Тот же метод `Save` работает с `BarCodeImageFormat.Jpeg` или `BarCodeImageFormat.Bmp`, если нужен другой тип файла.
* **Dynamic column count** – Если длина кодируемой строки меняется, рассчитывайте оптимальное количество столбцов исходя из её длины и разрешения сканера.

## How to set columns for specific use‑cases

* **Label printing** – Используйте небольшое количество столбцов (например, `2`‑`5`), чтобы штрих‑код помещался на узких этикетках.
* **Mobile scanning** – Большие количества столбцов (`10`‑`15`) дают более высокие штрих‑коды, которые легче фокусировать камере телефона.
* **Error‑correction trade‑off** – Большее число столбцов уменьшает количество строк, что может влиять на встроенную коррекцию ошибок. Тестируйте с вашим сканером, чтобы найти оптимальный баланс.

## Common pitfalls and pro tips

| Issue | Why it happens | Fix |
|-------|----------------|-----|
| Штрих‑код нечитаем | Слишком маленький X‑размер (например, `1` пиксель) | Увеличьте `XDimension.Pixels` минимум до `2` |
| Изображение слишком велико | Слишком много столбцов для короткой полезной нагрузки | Уменьшите `Pdf417.Columns` или включите `Truncate` |
| PNG‑файл пустой | Папка назначения не существует или нет прав записи | Убедитесь, что директория существует и процесс имеет права записи |
| Сканер сообщает «данные повреждены» | `Truncate` отключён при большом количестве столбцов | Включите `Truncate` или уменьшите количество столбцов |

## Verifying the result

Проверьте штрих‑код с помощью любого приложения‑сканера PDF417 (существует множество бесплатных Android/iOS‑приложений). Откройте `CompactPdf417.png` в приложении и убедитесь, что декодированный текст совпадает с исходной полезной нагрузкой («Compact mode»). Если текст отличается, проверьте флаг `Truncate` и настройки столбцов.

## Next steps

* **Integrate with ASP.NET Core** – Возвращайте PNG напрямую из действия контроллера вместо сохранения на диск.
* **Add human‑readable text** – Используйте `barcodeGenerator.Parameters.Barcode.CodeTextParameters` для отображения закодированной строки под штрих‑кодом.
* **Explore other symbologies** – Класс `BarcodeGenerator` также поддерживает QR, Code128, DataMatrix и другие. Поменяйте `EncodeTypes`, чтобы попробовать их.

---

### Conclusion

Теперь вы знаете, как **создать штрих‑код PDF417** в C# с **включённым компактным режимом**, управлять **количеством столбцов** и использовать **API генератора штрих‑кодов C#** для **генерации штрих‑кода**, отвечающего реальным ограничениям по размеру. Применяйте эти шаги в любом .NET‑проекте, где нужны компактные, высокоплотные штрих‑коды, и расширяйте шаблон на другие форматы штрих‑кодов по мере необходимости. Happy coding!

## What Should You Learn Next?

Следующие руководства охватывают тесно связанные темы, развивая техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}