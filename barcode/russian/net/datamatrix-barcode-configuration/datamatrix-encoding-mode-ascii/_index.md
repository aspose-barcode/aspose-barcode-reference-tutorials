---
date: 2026-06-09
description: Узнайте, как создать штрих‑код DataMatrix в режиме ASCII с использованием
  Aspose.BarCode для .NET. Это руководство показывает, как быстро генерировать штрих‑код
  на C#.
keywords:
- create datamatrix barcode
- generate barcode c#
- how to encode barcode
- barcode generator example
linktitle: Режим кодирования DataMatrix (ASCII)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  headline: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  name: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  steps:
  - name: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
    text: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
  - name: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
    text: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
  - name: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
    text: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
  type: HowTo
- questions:
  - answer: Yes, a valid Aspose license is required for production use; a free trial
      is available for evaluation.
    question: Can I use this in a commercial application?
  - answer: Absolutely – Aspose.BarCode fully supports .NET Core 3.1+, .NET 5, .NET
      6, and later versions.
    question: Does the library work with .NET Core?
  - answer: Up to 2,335 alphanumeric characters fit in a single DataMatrix symbol
      when using ASCII encoding.
    question: How many characters can I encode in ASCII mode?
  - answer: Yes, adjust `generator.Parameters.Image.ForeColor` and `BackColor` to
      any `System.Drawing.Color` value.
    question: Can I change the barcode’s foreground or background color?
  - answer: The official documentation contains dozens of samples covering custom
      sizes, colors, and error‑correction levels.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Создать штрих‑код DataMatrix в режиме ASCII с Aspose.BarCode для .NET
url: /ru/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создать штрих‑код DataMatrix в режиме ASCII с Aspose.BarCode для .NET

## Введение

Готовы **создавать изображения штрих‑кода DataMatrix**, использующие эффективное кодирование ASCII? В этом руководстве вы узнаете, как генерировать штрих‑код DataMatrix в режиме ASCII с помощью Aspose.BarCode для .NET. Мы пройдём каждый шаг — от настройки проекта до сохранения конечного изображения — чтобы вы могли добавить генерацию штрих‑кодов в свои C#‑приложения за считанные минуты.

## Быстрые ответы
- **Какая библиотека лучшая для DataMatrix в .NET?** Aspose.BarCode for .NET  
- **Сколько строк кода требуется?** Около 5‑7 строк для базового ASCII‑штрих‑кода  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для разработки; для продакшна требуется лицензия  
- **Поддерживаемые платформы?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Можно ли изменить размер или цвета?** Да, Aspose.BarCode предоставляет свойства для размеров и цветов переднего/фонового плана  

## Что такое штрих‑код DataMatrix?
DataMatrix — двумерный штрих‑код, который хранит текст и бинарные данные в компактном квадратном шаблоне.  
Штрих‑код DataMatrix кодирует информацию в сетке чёрных и белых модулей, позволяя разместить до 2 335 буквенно‑цифровых символов в одном символе. Он широко используется в производстве, логистике и здравоохранении, поскольку может быть напечатан в очень небольших размерах, оставаясь при этом легко считываемым.

## Как создать штрих‑код DataMatrix в режиме ASCII?
Подключите пространство имён Aspose.BarCode, создайте объект `BarcodeGenerator`, установите `EncodeMode` в **EncodeMode.ASCII**, задайте строку данных и вызовите `Save` для записи файла изображения. Этот подход создаёт полностью соответствующий штрих‑код DataMatrix с кодированием только ASCII всего за несколько строк кода C#.

## Зачем использовать кодировку ASCII для DataMatrix?
Режим ASCII — это режим по умолчанию и самый эффективный для простого текстового ввода, обеспечивая минимальный размер символа для буквенно‑цифровых строк. Он поддерживает все 128 символов ASCII, обрабатывает данные быстрее, чем расширенные режимы, и гарантирует максимальную совместимость со старыми сканерами, ожидающими стандартные ASCII‑символы.

## Требования

1. **Среда разработки** — Visual Studio, Rider или любой совместимый с C# IDE.  
2. **Aspose.BarCode for .NET** — Скачайте последнюю версию пакета [здесь](https://releases.aspose.com/barcode/net/).  
   - Документация: [Документация Aspose.BarCode для .NET](https://reference.aspose.com/barcode/net/)  
   - Помощь сообщества: [Форум Aspose.BarCode](https://forum.aspose.com/c/barcode/13)  
3. **Базовые знания C#** — Знакомство со структурой проекта .NET ускорит выполнение шагов.  
4. **Другие продукты Aspose** можно найти [здесь](https://releases.aspose.com/).

## Импорт пространств имён

Для начала добавьте необходимые директивы `using` в верхнюю часть вашего C#‑файла:

```csharp
using Aspose.BarCode.Generation;
using System.Drawing;
```

Эти пространства имён дают доступ к классу `BarcodeGenerator` и типам, связанным с изображениями, необходимыми для сохранения результата.

## Шаг 1: Создать каталог

Выберите папку, в которой будут храниться сгенерированные изображения штрих‑кодов. Замените `"Your Directory Path"` на абсолютный или относительный путь, существующий на вашем компьютере.

```csharp
string outputDir = @"C:\Barcodes";
if (!System.IO.Directory.Exists(outputDir))
{
    System.IO.Directory.CreateDirectory(outputDir);
}
```

Код проверяет наличие каталога перед попыткой записи файлов, предотвращая ошибки во время выполнения.

## Шаг 2: Кодирование данных в режиме ASCII

Класс `BarcodeGenerator` создаёт и настраивает изображения штрих‑кодов. Перечисление `DataMatrixEncodeMode` выбирает алгоритм кодирования для символов DataMatrix.

```csharp
// Initialise the generator with the data you want to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "1234567890");

// Set the encoding mode to ASCII for optimal size
generator.Parameters.Barcode.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;

// Optional: adjust image dimensions or colors here
generator.Parameters.Image.Width = 200;
generator.Parameters.Image.Height = 200;

// Save the barcode as a PNG file
string filePath = System.IO.Path.Combine(outputDir, "datamatrix_ascii.png");
generator.Save(filePath, BarCodeImageFormat.Png);
```

После выполнения кода вы найдёте `datamatrix_ascii.png` в указанной папке. Изображение содержит штрих‑код DataMatrix, который кодирует строку `"1234567890"` в компактном режиме ASCII.

## Распространённые проблемы и решения

- **Ошибки доступа к файлам** — Убедитесь, что приложение имеет права записи в целевую папку. Запуск Visual Studio от имени администратора может решить проблемы с правами в Windows.  
- **Неправильный размер символа** — Если штрих‑код выглядит слишком большим или маленьким, отрегулируйте `generator.Parameters.Image.Width` и `Height` или позвольте Aspose автоматически вычислить оптимальный размер, убрав эти свойства.  
- **Неподдерживаемые символы** — Режим ASCII принимает только символы в диапазоне 0‑127. Для Unicode‑данных переключитесь на `DataMatrixEncodeMode.Base256` или другой подходящий режим.

## Часто задаваемые вопросы

**В: Можно ли использовать это в коммерческом приложении?**  
О: Да, для продакшн‑использования требуется действующая лицензия Aspose; бесплатная пробная версия доступна для оценки.

**В: Работает ли библиотека с .NET Core?**  
О: Абсолютно — Aspose.BarCode полностью поддерживает .NET Core 3.1+, .NET 5, .NET 6 и более новые версии.

**В: Сколько символов можно закодировать в режиме ASCII?**  
О: До 2 335 буквенно‑цифровых символов помещается в один символ DataMatrix при кодировании ASCII.

**В: Можно ли изменить цвет переднего или фонового плана штрих‑кода?**  
О: Да, измените `generator.Parameters.Image.ForeColor` и `BackColor` на любой `System.Drawing.Color`.

**В: Где найти более продвинутые примеры?**  
О: Официальная документация содержит десятки образцов, охватывающих пользовательские размеры, цвета и уровни коррекции ошибок.

## Вопросы и ответы

### Q1: Можно ли использовать Aspose.BarCode for .NET с другими языками программирования, кроме C#?

A1: Aspose.BarCode поддерживает несколько языков программирования, но в этом руководстве рассматривается C#.

### Q2: Какие разные режимы кодирования доступны в штрих‑кодах DataMatrix?

A2: Штрих‑коды DataMatrix поддерживают различные режимы кодирования, включая ASCII, C40, Text и Base256. Каждый режим подходит для разных типов данных.

### Q3: Можно ли настроить внешний вид сгенерированного штрих‑кода, например размер и цвет?

A3: Да, Aspose.BarCode предоставляет широкий набор параметров для настройки внешнего вида штрих‑кода, включая размер, цвет и многое другое.

### Q4: Есть ли бесплатная пробная версия Aspose.BarCode for .NET?

A4: Да, вы можете изучить Aspose.BarCode for .NET с бесплатной пробной версией [здесь](https://releases.aspose.com/).

### Q5: Где можно приобрести лицензию на Aspose.BarCode for .NET?

A5: Лицензию можно купить на сайте Aspose [здесь](https://purchase.aspose.com/buy).

**Последнее обновление:** 2026-06-09  
**Тестировано с:** Aspose.BarCode 24.11 for .NET  
**Автор:** Aspose

## Связанные руководства

- [Кодирование DataMatrix в байтах с Aspose.BarCode для .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Чтение штрих‑кода DataMatrix C# — Генерация режима DataMatrix (Auto)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Как генерировать штрих‑коды DataMatrix (ECC 200) с Aspose.BarCode для .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
```

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

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}