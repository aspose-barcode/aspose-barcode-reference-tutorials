---
date: 2026-01-20
description: Изучите, как генерировать штрих‑код DataMatrix и декодировать штрих‑код
  DataMatrix с конфигурацией структурного добавления в .NET с помощью Aspose.BarCode
  для эффективной организации данных.
linktitle: DataMatrix Structured Append Configuration
second_title: Aspose.BarCode .NET API
title: Как создать штрих‑код DataMatrix с функцией Structured Append с помощью Aspose.BarCode
  для .NET
url: /ru/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Конфигурация Structured Append для DataMatrix с Aspose.BarCode для .NET

Если вы разработчик и хотите **генерировать DataMatrix barcode** с конфигурацией structured append в ваших .NET приложениях, Aspose.BarCode for .NET — ваше решение. В этом пошаговом руководстве мы пройдем процесс создания и чтения этих штрих‑кодов, разбивая каждый пример на легко‑усвояемые части, чтобы вы быстро освоили рабочий процесс.

## Быстрые ответы
- **Какую библиотеку использовать?** Aspose.BarCode for .NET  
- **Сколько строк кода? строк для генерации и чтения structured DataMatrix barcode  
-ческая лицензия требуется для продакшна  
- **Поддерживаемые платформы?** .NET Framework, .NET Core, .NET 5/6/7  
- **Можно ли также декодировать штрих‑код?** Да – см. раздел «How to decode DataMatrix barcode»

## Предварительные требования

Прежде чем приступить к руководству, убедитесь, что у вас есть:

1. **Aspose.BarCode for .NET Library** – скачайте её по ссылке [here](https://releases.aspose.com/barcode/net/).  
2. **Development Environment** – Visual Studio (любая современная версия) или другая IDE, совместимая с .NET.

Теперь давайте начнём пошаговое руководство по работе с DataMatrix structured append с использованием Aspose.BarCode for .NET.

## Импорт пространств имён

Сначала импортируйте пространства имён, которые предоставляют доступ к классам генерации и распознавания штрих‑кодов.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Теперь вы готовы генерировать и считывать **DataMatrix barcode**.

## Как сгенерировать DataMatrix barcode с Structured Append

Чтобы создать DataMatrix structured append штрих‑код, необходимо настроить несколько параметров, таких как barcode ID, общее количество штрих‑кодов в последовательности и file ID, связывающий их вместе.

```csharp
string path = "Your Directory Path";

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;

    // Set DataMatrix structured append mode
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodeId = 3;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodesCount = 5;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendFileId = 150;

    // Generate the barcode image
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

В этом фрагменте кода мы задали необходимые свойства, включающие функцию structured‑append.

## Как декодировать DataMatrix barcode с помощью Aspose.BarCode

После генерации штрих‑кода вам часто понадобится прочитать встроенную информацию. Следующий код использует `BarCodeReader` для извлечения деталей structured‑append из только что созданного изображения.

```csharp
    using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
    {
        reader.ReadBarCodes();

        Console.WriteLine("Barcode ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodeId);
        Console.WriteLine("Barcodes count: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodesCount);
        Console.WriteLine("File ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendFileId);
    }
}
```

Этот блок **декодирует DataMatrix barcode** и извлекает информацию, такую как barcode ID, подтверждая, что данные structured‑append были корректно встроены.

## Распространённые проблемы и советы

- **Неправильные размеры:** Убедитесь, что `XDimension.Pixels` соответствует разрешению принтера или дисп:** `StructuredAppendBarcodesCount всех частях последовательности.  
- **Ошибки лицензии:** Если появляются предупреждения о лицензировании, проверьте, что файл trial или коммерческой лицензии правильно указан в проекте.

## Заключение

Aspose.BarCode for .NET упрощает **генерацию DataMatrix barcode** и **декодирование DataMatrix barcode** с конфигурациями structured append. Следуя приведённым выше шагам, вы сможете интегрировать эти штрих‑коды в системы учёта, отслеживания документов или любые сценарии, где полезно разбивать большой объём данных на несколько штрих‑кодов.

## Часто задаваемые вопросы

### Q1: Что такое DataMatrix structured append и зачем он используется?

A1: DataMatrix structured append — это функция, позволяющая разбить большой объём данных на несколько более мелких штрих‑кодов. Это особенно полезно, когда место для одного штрих‑кода ограничено или требуется эффективная организация данных. Широко используется в таких отраслях, как логистика, здравоохранение и производство.

### Q2: Могу ли я использовать Aspose.BarCode for .NET в своём open-source проекте?

A2: Да, Aspose.BarCode for .NET предоставляет бесплатную trial‑версию, которую можно использовать в open-source проектах. Вы можете найти trial‑версию [here](https://releases.aspose.com/).

### Q3: Есть ли поддержка сообщества для Aspose.BarCode for .NET?

A3: Да, вы можете получить поддержку сообщества и общаться с другими пользователями на форуме Aspose.BarCode [here](https://forum.aspose.com/c/barcode/13).

### Q4: Как получить временную лицензию для Aspose.BarCode for .NET?

A4: Если вам нужна временная лицензия для оценки или тестирования, её можно получить по ссылке [here](https://purchase.aspose.com/temporary-license/).

### Q5: Поддерживает ли Aspose.BarCode for .NET другие типы штрих‑кодов?

A5: Да, Aspose.BarCode for .NET поддерживает широкий спектр типов штрих‑кодов, включая QR‑коды, Code 128, EAN‑13 и многие другие. Полную документацию можно изучить [here](https://reference.aspose.com/barcode/net/), чтобы увидеть полный список поддерживаемых типов штрих‑кодов.

**Последнее обновление:** 2026-01-20  
**Тестировано с:** Aspose.BarCode 24.11 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}