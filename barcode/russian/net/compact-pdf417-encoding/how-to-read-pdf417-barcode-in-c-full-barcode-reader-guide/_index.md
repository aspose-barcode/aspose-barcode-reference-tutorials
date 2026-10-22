---
category: general
date: 2026-10-21
description: Как считывать штрих‑код PDF417 в C# с помощью считывателя штрих‑кодов
  из изображения. Следуйте этому пошаговому примеру считывателя штрих‑кодов на C#
  для надёжного декодирования.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode from image c#
- c# barcode reader example
- macro pdf417 decoding
- barcode extended fields c#
language: ru
lastmod: 2026-10-21
og_description: Как считывать штрих‑код PDF417 в C# с полным примером считывателя
  штрих‑кодов. Узнайте, как декодировать изображения Macro PDF417 и получить доступ
  ко всем расширенным полям.
og_image_alt: Console output showing decoded PDF417 barcode fields in a C# application
og_title: Как считать штрих‑код PDF417 в C# – подробное руководство
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  headline: How to read PDF417 barcode in C# – full barcode reader guide
  type: TechArticle
- description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  name: How to read PDF417 barcode in C# – full barcode reader guide
  steps:
  - name: Initialise the `BarCodeReader` for the specific `DecodeType`.
    text: Initialise the `BarCodeReader` for the specific `DecodeType`.
  - name: Iterate through the returned `BarCodeResult` collection.
    text: Iterate through the returned `BarCodeResult` collection.
  - name: Access both basic and extended PDF417 fields.
    text: Access both basic and extended PDF417 fields.
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the Aspose.BarCode package** (as shown earlier).'
    text: '**Add the Aspose.BarCode package** (as shown earlier).'
  - name: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
    text: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
  - name: '**Build and run**'
    text: '**Build and run**'
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Как считывать штрих‑код PDF417 в C# — полное руководство по чтению штрих‑кода
url: /ru/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-full-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как считывать штрих‑код PDF417 в C# – полное руководство по чтению штрих‑кодов

Если вам нужно **как считывать штрих‑код PDF417** в приложении .NET, это руководство покажет готовое решение, которое можно сразу запустить. Вы увидите, как **читать штрих‑код из изображения C#** с помощью популярной библиотеки штрих‑кодов и получить каждый атрибут Macro PDF417 без дополнительного инструментария.

В уроке рассматривается всё, что требуется для **примера считывателя штрих‑кодов C#**: настройка проекта, разбор кода и советы по обработке граничных случаев. К концу вы сможете вставить код в консольный проект и сразу начать декодировать изображения PDF417.

## Что понадобится

Прежде чем начать, убедитесь, что у вас есть следующие предварительные условия:

| Требование | Причина |
|------------|---------|
| .NET 6.0 SDK или новее | Предоставляет среду выполнения для консольного приложения C# |
| Visual Studio 2022 (или любая IDE для C#) | Обеспечивает простое создание проекта и отладку |
| Aspose.BarCode for .NET (пакет NuGet) | Содержит классы `BarCodeReader` и `DecodeType` |
| Файл изображения Macro PDF417 (например, `MacroPdf417.png`) | Является входными данными для декодирования |

Библиотеку можно установить через dotnet CLI:

```bash
dotnet add package Aspose.BarCode
```

## Как считывать штрих‑код PDF417 из изображения в C#

Ядро процесса **чтения штрих‑кода из изображения C#** состоит из трёх действий:

1. Инициализировать `BarCodeReader` для конкретного `DecodeType`.
2. Пройтись по полученной коллекции `BarCodeResult`.
3. Получить как базовые, так и расширенные поля PDF417.

Ниже приведён полный, готовый к запуску код. Сохраните его как `Program.cs` в консольном проекте.

```csharp
using System;
using Aspose.BarCode;               // Provides BarCodeReader, DecodeType, BarCodeResult
using Aspose.BarCode.BarCodeRecognition; // Contains extended PDF417 structures

class Program
{
    static void Main()
    {
        // Step 1: Initialise a BarCodeReader for a Macro PDF417 image
        // Replace the path with the location of your MacroPdf417.png file
        string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes present in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // Step 3: Display basic barcode information
                Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
                Console.WriteLine($"CodeText: {barcodeResult.CodeText}");

                // Step 4: Show Macro PDF417 specific extended fields
                Console.WriteLine($"File ID: {barcodeResult.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name: {barcodeResult.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {barcodeResult.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size: {barcodeResult.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"TimeStamp: {barcodeResult.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {barcodeResult.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {barcodeResult.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {barcodeResult.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

### Пояснение каждого шага

* **Шаг 1 – Инициализация считывателя**  
  Конструктор `BarCodeReader` принимает путь к файлу изображения и `DecodeType`. `DecodeType.MacroPdf417` указывает библиотеке искать символы Macro PDF417, которые содержат дополнительную мета‑информацию помимо обычных штрих‑кодов PDF417.

* **Шаг 2 – ReadBarCodes()**  
  Этот метод возвращает `IEnumerable<BarCodeResult>`, который может содержать несколько штрих‑кодов, если на изображении их больше одного. Цикл `foreach` гарантирует, что каждый обнаруженный символ будет обработан.

* **Шаг 3 – Базовая информация**  
  `CodeTypeName` определяет формат штрих‑кода (например, “MacroPDF417”). `CodeText` содержит строку необработанных данных, закодированных в символе.

* **Шаг 4 – Расширенные поля**  
  Macro PDF417 добавляет набор расширенных свойств в `barcodeResult.Extended.Pdf417`. Эти поля раскрывают данные уровня файла, такие как `FileID`, `SegmentID` и `FileName`. Прямой доступ к ним позволяет восстанавливать много‑сегментные документы или проверять целостность.

#### Ожидаемый вывод в консоли

```
CodeType: MacroPDF417
CodeText: 1234567890
File ID: 5
Segment ID: 1
Segments Count: 3
File Name: invoice_2024.pdf
Checksum: 0A3F
File Size: 254321
TimeStamp: 2024-03-15T10:45:12Z
Addressee: Acme Corp.
Sender: Warehouse 12
Terminator: END
----------------------------------------
```

Точные значения отражают содержимое, закодированное в вашем `MacroPdf417.png`. Если изображение содержит один сегмент, `SegmentsCount` будет 1, а `SegmentID` 0.

## Настройка среды считывателя штрих‑кодов C#

Надёжный **пример считывателя штрих‑кодов C#** зависит от чистой конфигурации проекта:

1. **Создайте новый консольный проект**  
   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```
2. **Добавьте пакет Aspose.BarCode** (как показано выше).  
3. **Скопируйте файл изображения** в папку проекта или укажите абсолютный путь к нему.  
4. **Соберите и запустите**  
   ```bash
   dotnet run
   ```

Если сборка завершилась ошибкой из‑за отсутствующей ссылки, проверьте, что директивы `using Aspose.BarCode;` соответствуют установленной версии пакета. API библиотеки стабилен как в .NET 6, так и в .NET 8, поэтому вы можете обновлять среду выполнения без изменений кода.

## Декодирование штрих‑кода Macro PDF417

При вызове `ReadBarCodes()` библиотека внутри себя выполняет следующее:

* **Предобработка изображения** – преобразует bitmap в бинарную матрицу, исправляя вращение и шум.  
* **Обнаружение шаблонов** – сканирует стартовые/концевые шаблоны PDF417 и извлекает ширину модуля.  
* **Коррекция ошибок** – применяет коды Рида‑Соломона для восстановления повреждённых кодовых слов.  
* **Извлечение макроса** – разбирает заголовок расширенного сегмента PDF417 и заполняет объект `Extended.Pdf417`.

Понимание этого конвейера помогает решить, когда стоит менять параметры декодера. Например, если ваши изображения имеют низкий контраст, можно включить свойство `ReadQuality` у `BarCodeReader` (доступно в более новых версиях) для повышения уровня обнаружения.

## Интерпретация расширенных полей PDF417

Расширенные поля напрямую соответствуют спецификации Macro PDF417:

| Поле | Значение |
|------|----------|
| `MacroPdf417FileID` | Уникальный идентификатор всего файла во всех сегментах |
| `MacroPdf417SegmentID` | Нулевой индекс текущего сегмента |
| `MacroPdf417SegmentsCount` | Общее количество сегментов, составляющих файл |
| `MacroPdf417FileName` | Исходное имя файла, сохранённое при кодировании |
| `MacroPdf417Checksum` | 16‑битовая контрольная сумма для проверки целостности |
| `MacroPdf417FileSize` | Размер исходного файла в байтах |
| `MacroPdf417TimeStamp` | UTC‑метка времени генерации штрих‑кода |
| `MacroPdf417Addressee` | Предназначенный получатель документа |
| `MacroPdf417Sender` | Отправитель документа |
| `MacroPdf417Terminator` | Буквальная строка “END”, обозначающая последний сегмент |

Эти значения можно использовать для восстановления много‑сегментного PDF, проверки отсутствия сегментов или ведения аудита в целях соответствия требованиям.

## Распространённые проблемы и их решение

| Симптом | Вероятная причина | Решение |
|---------|-------------------|---------|
| Нет вывода | Неправильный путь к изображению или неподдерживаемый формат | Укажите абсолютный путь и убедитесь, что файл PNG/JPEG поддерживается Aspose.BarCode |
| `CodeType` показывает “PDF417” вместо “MacroPDF417” | На изображении обычный PDF417, а не макрос | Проверьте, что исходный штрих‑код закодирован с расширениями Macro PDF417 |
| Некоторые поля пусты | Штрих‑код был сгенерирован без этих макрос‑полей | Сгенерируйте штрих‑код с полным макрос‑нагрузом или обрабатывайте null‑значения в коде |
| Декодер бросает `ArgumentException` | Указан неверный `DecodeType` | Замените `DecodeType.MacroPdf417` на `DecodeType.Pdf417`, если нужны только стандартные данные PDF417 |

**Совет:** Оборачивайте доступ к полям в проверки на null, если ожидаете обычные (не‑macro) штрих‑коды. Объект `Extended.Pdf417` возвращает значения по умолчанию (например, `0` для числовых полей), когда данные отсутствуют.

```csharp
int fileId = barcodeResult.Extended?.Pdf417?.MacroPdf417FileID ?? -1;
```

## Итоговый полностью рабочий пример

Объединив всё вместе, окончательная программа состоит из директив `using`, метода `Main` и четырёхшагового цикла, показанного ранее. Дополнительные файлы конфигурации не требуются. Скомпилируйте и запустите проект, чтобы увидеть вывод в консоли со всеми свойствами Macro PDF417.

## Заключение

Теперь вы знаете **как считывать штрих‑код PDF417** в C# с помощью лаконичного **примера считывателя штрих‑кодов C#**. Руководство провело вас через настройку среды, реализацию кода и интерпретацию каждого расширенного поля Macro PDF417. Имея эту основу, вы сможете интегрировать сканирование штрих‑кодов в системы учёта, документооборота или мобильные бек‑энды.

### Далее


## Что изучать дальше?


Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [How to read PDF417 in C# – complete barcode reader guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/)
- [How to decode PDF417 in C# with a barcode reader example](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [How to create PDF417 barcode image in C# with Macro PDF417 options](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}