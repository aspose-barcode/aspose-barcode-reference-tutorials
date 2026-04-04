---
date: 2026-01-15
description: 'Пошаговое руководство по работе со штрих‑кодами: чтение DataMatrix‑кода
  на C# и генерация изображения штрих‑кода на C# с использованием Aspose.BarCode для
  .NET.'
linktitle: DataMatrix Encoding Mode (Auto)
second_title: Aspose.BarCode .NET API
title: Чтение штрих‑кода DataMatrix C# – Генерация режима DataMatrix (Авто)
url: /ru/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Чтение штрих‑кода DataMatrix C# – Генерация режима DataMatrix (Auto)

В современном быстро меняющемся цифровом мире возможность **read DataMatrix barcode C#** быстро и надёжно является ключевой для всего, от учёта запасов до безопасной обработки документов. В этом руководстве мы пошагово покажем, как сгенерировать штрих‑код DataMatrix в режиме *Auto* с помощью Aspose.BarCode для .NET, а затем продемонстрируем, как считать этот штрих‑код обратно в C#. Независимо от того, следуете ли вы **barcode tutorial guide** или просто нуждаетесь в надёжном примере кода, вы завершите это руководство работающим решением, которое можно внедрить в свои проекты.

## Быстрые ответы
- **Что делает режим “Auto”?** Он позволяет Aspose.BarCode автоматически выбирать лучшую схему кодирования для ваших данных.  
- **Какая библиотека требуется?** Aspose.BarCode for .NET (доступна бесплатная пробная версия).  
- **Можно ли считывать штрих‑код в том же приложении?** Да — используйте `BarCodeReader` с `DecodeType.DataMatrix`.  
- **Нужна ли лицензия для продакшн?** Для использования в продакшене требуется коммерческая лицензия.  
- **Поддерживаемые версии .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Что такое read DataMatrix barcode C#?
Чтение штрих‑кода DataMatrix в C# означает декодирование двумерной матрицы чёрных и белых модулей обратно в исходный текст или данные. Aspose.BarCode предоставляет простой API, который абстрагирует низкоуровневую обработку изображений, позволяя сосредоточиться на бизнес‑логике.

## Почему стоит использовать Aspose.BarCode для генерации изображения штрих‑кода C#?
- **Надёжность:** Обрабатывает все стандарты DataMatrix и автоматически выбирает оптимальное кодирование.  
- **Гибкость:** Полный контроль над размерами, кодированием ECI и форматом изображения.  
- **Кросс‑платформенность:** Работает с .NET Framework, .NET Core и приложениями .NET 5+.

## Предварительные требования

1. **.NET Environment** – Установите последнюю среду выполнения .NET с [веб‑сайта .NET](https://dotnet.microsoft.com/download/dotnet).  
2. **Aspose.BarCode for .NET** – Скачайте библиотеку с [веб‑сайта](https://releases.aspose.com/barcode/net/).  

## Импорт пространств имён

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Теперь, когда пространства имён импортированы, давайте пройдёмся по коду шаг за шагом.

## Шаг 1: Установите путь к директории

```csharp
string path = "Your Directory Path";
```

Замените `"Your Directory Path"` на путь к папке, где вы хотите сохранить сгенерированный PNG (или другой формат).

## Шаг 2: Создайте штрих‑код DataMatrix в режиме Auto

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose常に先を行く"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Auto;
    generator.Parameters.Barcode.DataMatrix.ECIEncoding = ECIEncodings.UTF8;
    Bitmap bitmap = generator.GenerateBarCodeImage();
}
```

Параметр `DataMatrixEncodeMode.Auto` позволяет библиотеке выбрать наилучшее кодирование для предоставленного текста. Не стесняйтесь заменить пример текста любой строкой, для которой вам нужно **generate barcode image C#**.

## Шаг 3: Считайте штрих‑код (read DataMatrix barcode C#)

```csharp
using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
{
    reader.ReadBarCodes();
    Console.WriteLine(reader.FoundBarCodes[0].CodeText);
}
```

Этот фрагмент кода декодирует только что сгенерированное изображение и выводит оригинальный текст в консоль, демонстрируя полный цикл от генерации до чтения.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|---------|----------|
| **Штрих‑код не обнаружен** | Разрешение изображения слишком низкое | Увеличьте `XDimension.Pixels` (например, до 6) |
| **Мусорные символы** | Неправильное кодирование ECI | Установите `ECIEncoding` в соответствии с вашими данными (UTF‑8, ASCII и т.д.) |
| **Исключение при `ReadBarCodes`** | Bitmap освобождён до чтения | Сохраните экземпляр `Bitmap` живым до завершения чтения |

## Часто задаваемые вопросы

**В: Что такое режим кодирования DataMatrix "Auto"?**  
A: Он позволяет Aspose.BarCode автоматически выбирать оптимальный метод кодирования для предоставленных данных, упрощая процесс **how to generate datamatrix barcode**.

**В: Можно ли настроить размеры генерируемого штрих‑кода?**  
A: Да — измените `generator.Parameters.Barcode.XDimension.Pixels`, чтобы изменить размер модуля.

**В: Подходит ли Aspose.BarCode для .NET для коммерческого использования?**  
A: Абсолютно. Приобретите лицензию на [веб‑сайте](https://purchase.aspose.com/buy).

**В: Доступна ли бесплатная пробная версия?**  
A: Да, вы можете ознакомиться с Aspose.BarCode с помощью бесплатной пробной версии по [этой ссылке](https://releases.aspose.com/).

**В: Какие варианты кодирования доступны для штрих‑кодов DataMatrix?**  
A: Aspose.BarCode поддерживает UTF‑8, ASCII и другие кодировки ECI; задайте нужное значение через `ECIEncoding`.

## Заключение

Теперь у вас есть полноценный, готовый к продакшену пример, который **reads DataMatrix barcode C#**, генерирует штрих‑код в режиме Auto и проверяет результат — всё с помощью Aspose.BarCode для .NET. Экспериментируйте с разными текстами, размерами и настройками ECI, чтобы подобрать оптимальное решение для вашей задачи, и обратитесь к официальной [документации](https://reference.aspose.com/barcode/net/) для более глубокой кастомизации.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose