---
category: general
date: 2026-07-30
description: Быстро создавайте планетарный штрих‑код с помощью C#. Узнайте, как генерировать
  штрих‑код планеты, задавать пользовательскую высоту штрих‑кода и экспортировать
  изображение штрих‑кода.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planetary barcode
- generate planet barcode
- custom barcode height
- export barcode image
- customize postal barcode
language: ru
lastmod: 2026-07-30
og_description: Создайте планетарный штрих‑код на C# и мгновенно генерируйте штрих‑код
  планеты с пользовательской высотой, затем экспортируйте изображение штрих‑кода для
  любой почтовой системы.
og_image_alt: Screenshot showing a generated planetary barcode saved as a PNG file
og_title: Создайте планетарный штрих‑код на C# – Полное пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Create planetary barcode quickly with C#. Learn how to generate planet
    barcode, set custom barcode height, and export barcode image.
  headline: Create planetary barcode in C# – Complete Programming Guide
  type: TechArticle
- description: Create planetary barcode quickly with C#. Learn how to generate planet
    barcode, set custom barcode height, and export barcode image.
  name: Create planetary barcode in C# – Complete Programming Guide
  steps:
  - name: 'Example 1: Default planetary barcode (auto height)'
    text: '```csharp using Aspose.Barcode; using Aspose.Barcode.Generation;'
  - name: 'Example 2: Planet barcode with a custom 100‑pixel bar height'
    text: 'Sometimes you need a taller barcode for a specific label printer. Here’s
      how to set a **custom barcode height**:'
  - name: 'Example 3: RM4SCC barcode with a custom 100‑pixel bar height'
    text: 'The Planet format isn’t the only postal symbology you might encounter.
      Let’s **customize postal barcode** for RM4SCC, which is popular in the UK and
      parts of Europe:'
  type: HowTo
tags:
- barcode
- C#
- planetary barcode
title: Создание планетарного штрихкода на C# – Полное руководство по программированию
url: /ru/python-java/general/create-planetary-barcode-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание планетарного штрихкода в C# – Полное руководство по программированию

Когда‑то вам нужно **создать планетарный штрихкод**, но вы не знали, какие свойства менять? Вы не одиноки; символьная система Planet может казаться загадочной, пока не увидеть её в действии. В этом руководстве мы **сгенерируем объекты штрихкода планеты**, настроим **пользовательскую высоту штрихкода**, а затем **экспортируем файлы изображения штрихкода**, которые работают в любой почтовой системе.

Подумайте о планетарном штрихкоде как о версии QR‑кода для почтовой службы — компактный, машинно‑читаемый и удивительно гибкий. К концу этого урока вы сможете **настроить параметры почтового штрихкода** без бесконечного изучения API‑документов, и у вас будет три готовых к запуску фрагмента кода, которые можно вставить в свой проект.

---

## Предварительные требования – Что нужно перед началом

| Требование | Почему это важно |
|-------------|----------------|
| .NET 6.0 или новее | Современная среда выполнения, полная поддержка Aspose.Barcode |
| Visual Studio 2022 (или любой IDE для C#) | Удобная отладка и IntelliSense |
| **Aspose.Barcode for .NET** NuGet‑пакет | Предоставляет `BarcodeGenerator`, `EncodeTypes` и форматы изображений |
| Права записи в папку на диске | Необходимо для вызова `Save`, который **экспортирует изображение штрихкода** |

Библиотеку можно добавить через консоль диспетчера пакетов:

```powershell
Install-Package Aspose.Barcode
```

Вот и всё — никаких дополнительных DLL, никаких внешних сервисов. Готовы? Приступаем.

---

## Создание планетарного штрихкода – Пошагово

Ниже мы пройдем три практических примера:

1. **Планетарный штрихкод со стандартной высотой** (автоматический размер)
2. **Планетарный штрихкод с пользовательской высотой 100 пикселей**
3. **Штрихкод RM4SCC с пользовательской высотой** (показывает, как **настроить почтовый штрихкод** помимо Planet)

Каждый пример опирается на предыдущий, поэтому смело копируйте‑вставляйте весь блок в новое консольное приложение и запускайте его.

### Пример 1: Планетарный штрихкод со стандартной высотой (авто)

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a generator for the Planet symbology and supply the data to encode
        BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Step 2: Define the module (X) size – 4 pixels per bar
        gen.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 3: Render the barcode to a PNG file (this will **export barcode image**)
        gen.Save(@"C:\Barcodes\PostalPlanetAuto.png", BarCodeImageFormat.Png);
    }
}
```

**Что только что произошло?**  
`BarcodeGenerator` — ваша точка входа; вы указываете *что* (Planet) и *какие данные* (`"123456"`). Параметр X‑dimension задаёт ширину каждой полосы, а поскольку мы не меняли высоту, библиотека автоматически выбирает разумный размер согласно почтовым стандартам. При запуске программы вы найдёте PNG‑файл с именем **PostalPlanetAuto.png** в `C:\Barcodes`.

> **Совет:** При отладке откройте PNG в любом просмотрщике изображений — обратите внимание, как полосы чёткие и равномерно распределены. Это фундамент надёжной операции **generate planet barcode**.

### Пример 2: Планетарный штрихкод с пользовательской высотой 100 пикселей

Иногда требуется более высокий штрихкод для конкретного принтера этикеток. Вот как задать **пользовательскую высоту штрихкода**:

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

class Program
{
    static void Main()
    {
        // Initialise the generator with the same data
        BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Set the X dimension (module width)
        gen.Parameters.Barcode.XDimension.Pixels = 4;

        // Override the default bar height to 100 pixels
        gen.Parameters.Barcode.BarHeight.Pixels = 100;

        // Save the customised barcode image
        gen.Save(@"C:\Barcodes\PostalPlanetHeight100.png", BarCodeImageFormat.Png);
    }
}
```

**Зачем менять высоту?**  
Более высокая полоса может улучшить надёжность сканирования на принтерах с низким разрешением, а некоторые почтовые службы явно требуют минимальную высоту. Изменяя `BarHeight.Pixels`, мы сохраняем полный контроль над визуальным весом символа, одновременно **generate planet barcode** «под капотом».

### Пример 3: Штрихкод RM4SCC с пользовательской высотой 100 пикселей

Формат Planet — не единственная почтовая символьная система, с которой вы можете столкнуться. Давайте **настроим почтовый штрихкод** для RM4SCC, популярного в Великобритании и части Европы:

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

class Program
{
    static void Main()
    {
        // Create a generator for the RM4SCC symbology
        BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

        // Set the X dimension (module width)
        gen.Parameters.Barcode.XDimension.Pixels = 4;

        // Specify a 100‑pixel bar height
        gen.Parameters.Barcode.BarHeight.Pixels = 100;

        // Export the barcode to a PNG file
        gen.Save(@"C:\Barcodes\PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);
    }
}
```

Обратите внимание, что код почти идентичен примеру 2 — меняется только перечисление `EncodeTypes`. В этом и прелесть Aspose.Barcode: вы **настраиваете почтовый штрихкод** без изучения новой API‑поверхности.

---

## Понимание ключевых свойств

| Свойство | Значение | Типичные значения |
|----------|----------|-------------------|
| `XDimension.Pixels` | Ширина одного модуля (самой маленькой полосы) | 2‑6 px для большинства принтеров |
| `BarHeight.Pixels` | Высота самой высокой полосы (в пикселях) | 50‑150 px, в зависимости от размера этикетки |
| `EncodeTypes` | Символика для генерации (Planet, RM4SCC и др.) | `EncodeTypes.Planet`, `EncodeTypes.RM4SCC` |
| `BarCodeImageFormat` | Формат выходного изображения | `.Png`, `.Jpeg`, `.Bmp` |

Когда вы **экспортируете изображение штрихкода**, библиотека растеризует векторные данные в выбранный формат. PNG — без потерь, идеально подходит для высококачественных этикеток. Если нужен меньший файл для веба, переключитесь на `BarCodeImageFormat.Jpeg` и настройте степень сжатия.

---

## Распространённые подводные камни и как их избежать

* **Неправильная ширина модуля** — слишком маленькое значение `XDimension.Pixels` может привести к слиянию полос при печати. Тестируйте на реальном принтере перед массовым производством.
* **Отсутствие прав записи** — метод `Save` бросит исключение, если целевая папка недоступна для записи. Всегда проверяйте путь или используйте `Path.GetTempPath()` для быстрых тестов.
* **Неправильная длина данных** — Planet ожидает числовую строку из 6‑8 цифр. Передача буквенных символов вызовет ошибку валидации.
* **Забывание освободить ресурсы** — `BarcodeGenerator` реализует `IDisposable`. В длительно работающих сервисах оборачивайте его в `using`, чтобы освободить нативные ресурсы.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(...))
{
    // configure and save...
}
```

---

## Ожидаемый результат – Что вы должны увидеть

После выполнения трёх примеров в папке `C:\Barcodes` появятся:

| Файл | Описание |
|------|----------|
| `PostalPlanetAuto.png` | Планетарный штрихкод со стандартной высотой (авто) |
| `PostalPlanetHeight100.png` | Планетарный штрихкод с **пользовательской высотой штрихкода** 100 px |
| `PostalRM4SCCHeight100.png` | Штрихкод RM4SCC, также с **пользовательской высотой штрихкода** 100 px |

Откройте любой из этих PNG‑файлов; вы увидите чистые вертикальные полосы с закодированными цифрами под (или над) ними, в зависимости от символьной системы. Сканируйте их приложением‑сканером штрихкодов на смартфоне — если приложение распознаёт «123456», вы успешно **создали планетарный штрихкод** и **экспортировали изображение штрихкода**.

---

## Дальнейшие шаги – Что дальше и связанные темы

* **Пакетная генерация** — переберите список почтовых кодов из CSV и автоматически сохраняйте каждый штрихкод.
* **Встраивание в PDF** — используйте `PdfDocument` из Aspose.PDF, чтобы разместить PNG непосредственно на транспортной этикетке.
* **Динамический размер** — рассчитывайте `BarHeight.Pixels` исходя из DPI этикетки, чтобы гарантировать одинаковые физические размеры.
* **Другие почтовые символьные системы** — изучите `EncodeTypes.Postnet`, `EncodeTypes.USPSIntelligentMail` или `EncodeTypes.Aztec` для более широкого охвата.

Если вам интересны расчёты **пользовательской высоты штрихкода**, обратитесь к официальной документации Aspose.Barcode по *module dimensions* — формулы просты и работают для всех поддерживаемых символьных систем.

---

## Заключение

Мы прошли полный практический процесс создания изображений **планетарного штрихкода** в C#. Начиная с простого генератора, мы научились **генерировать планетарный штрихкод**, применять **пользовательскую высоту штрихкода** и, наконец, **экспортировать изображение штрихкода**, соответствующее почтовым стандартам. Путём изменения лишь нескольких свойств вы также можете **настроить почтовый штрихкод** для RM4SCC или любого другого поддерживаемого формата.

Попробуйте: измените строку данных, поэкспериментируйте с разными значениями `XDimension`, или замените PNG на JPEG. Библиотека достаточно гибка, чтобы покрыть большинство реальных сценариев, а теперь у вас есть прочная база для дальнейшего развития.

Есть вопросы или хотите поделиться своими приёмами работы со штрихкодами? Оставляйте комментарий ниже, и счастливого кодинга!

## Что следует изучить дальше?

Следующие учебные материалы охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [Create Barcode Custom Height – One-Dimensional Barcodes](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}