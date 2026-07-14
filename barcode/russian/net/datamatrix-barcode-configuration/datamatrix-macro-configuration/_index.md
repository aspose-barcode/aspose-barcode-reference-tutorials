---
date: 2026-01-17
description: Узнайте, как генерировать штрих‑код DataMatrix с макросимволами с помощью
  Aspose.BarCode для .NET, и откройте для себя способы использования DataMatrix в
  ваших приложениях.
linktitle: DataMatrix Macro Configuration
second_title: Aspose.BarCode .NET API
title: Как сгенерировать штрих‑код DataMatrix с помощью Aspose.BarCode для .NET
url: /ru/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Основная конфигурация макроса DataMatrix с Aspose.BarCode для .NET

## Введение

В современных .NET‑приложениях **генерация штрих‑кодов DataMatrix** является надёжным способом закодировать большие объёмы данных в небольшом пространстве. Этот учебник проведёт вас через процесс **генерации штрих‑кода DataMatrix** с макросимволами, объяснит *как эффективно использовать DataMatrix* и покажет, как проверить результат с помощью Aspose.BarCode для .NET. К концу вы сможете уверенно создавать, настраивать и считывать штрих‑коды DataMatrix.

## Краткие ответы
- **Какая основная библиотека?** Aspose.BarCode for .NET  
- **Могу ли я сгенерировать штрих‑код DataMatrix с макросимволами?** Да, используя свойство `MacroCharacters`.  
- **Нужна ли лицензия для продакшн?** Требуется действующая лицензия Aspose для использования в продакшн.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Доступна ли бесплатная пробная версия?** Конечно – скачайте её с официального сайта Aspose.

## Требования

Прежде чем приступить к настройке макроса, убедитесь, что у вас есть следующее:

1. **Visual Studio** – любой современный выпуск подойдет.  
2. **Aspose.BarCode for .NET** – скачайте её по [the download link](https://releases.aspose.com/barcode/net/).  
3. **Basic .NET knowledge** – знание C# и экосистемы .NET.

## Импорт пространств имён

Мы начинаем с подключения пространств имён, необходимых для генерации и распознавания штрих‑кодов.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

## Что такое «генерация штрих‑кода DataMatrix» с макросимволами?

Штрих‑код DataMatrix с поддержкой макросов может нести дополнительную информацию (например, ссылку на другой штрих‑код), используя специальные макросимволы (Macro05, Macro06 и т.д.). Это полезно в логистике и производстве, где один символ может потребоваться связать с более крупным набором данных.

## Зачем использовать Aspose.BarCode для генерации штрих‑кода DataMatrix?

- **Full control** над размером, коррекцией ошибок и настройками макросов.  
- **Cross‑platform** поддержка .NET Framework, .NET Core и .NET 5/6.  
- **Built‑in recognition** позволяет сразу после создания проверять штрих‑код.

## Пошаговое руководство

### Шаг 1: Настройка проекта

Создайте новое консольное приложение (или любой .NET‑проект) в Visual Studio. Добавьте ссылку на DLL‑файлы Aspose.BarCode, полученные из загрузки.

### Шаг 2: Конфигурация макроса DataMatrix

Суть учебника – здесь мы действительно **генерируем штрих‑код DataMatrix** с макросимволом.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixMacro:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    // Set the macro character to 05
    gen.Parameters.Barcode.DataMatrix.MacroCharacters = MacroCharacter.Macro05;
    gen.Save($"{path}DataMatrixMacro.png", BarCodeImageFormat.Png);

    // Try to recognize it
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixMacro:" + result.CodeText);
    }
}
```

> **Pro tip:** Замените `"ASPOSE"` любой строкой, которую нужно закодировать. Макросимвол (`Macro05`) сообщает сканерам, что этот штрих‑код является частью макросеквенции.

### Шаг 3: Настройка параметров штрих‑кода

Перед сохранением вы можете изменить дополнительные настройки:

- **XDimension** – управляет размером каждого модуля (пиксель).  
- **Margin**, **ErrorCorrection** и **EncodingMode** – все доступны через `gen.Parameters.Barcode.DataMatrix`.

### Шаг 4: Сохранение штрих‑кода

Приведённый выше фрагмент сохраняет изображение как `DataMatrixMacro.png` в указанной вами папке. PNG — без потерь, что делает его идеальным для дальнейшей обработки.

### Шаг 5: Распознавание штрих‑кода

С помощью `BarCodeReader` мы сразу считываем сгенерированное изображение, чтобы подтвердить правильность макросимвола и данных. Такая проверка в обе стороны особенно полезна при автоматическом тестировании.

## Как использовать DataMatrix в реальных сценариях?

- **Product labeling** – внедрение серийных номеров, идентификаторов партии или URL.  
- **Document tracking** – связывание печатной формы с цифровой записью через макросеквенции.  
- **Healthcare** – кодирование информации о пациенте на компактных метках для оборудования.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|---------|---------|
| Штрих‑код не распознаётся | Некорректный `XDimension` или низкое разрешение изображения | Увеличьте `XDimension.Pixels` до 4‑6 и сохраняйте в формате PNG или TIFF |
| Игнорируется макросимвол | Сканер не поддерживает режим макросов | Используйте сканер/ридер, который явно поддерживает макросы DataMatrix (например, более новые версии ZXing) |
| Путь не найден | Недопустимая переменная `path` | Убедитесь, что каталог существует, или используйте `Path.Combine` с `Environment.CurrentDirectory` |

## Часто задаваемые вопросы

**В: Что такое Aspose.BarCode for .NET?**  
О: Aspose.BarCode for .NET — мощная библиотека, позволяющая разработчикам .NET генерировать и распознавать штрих‑коды в различных форматах, включая DataMatrix, QR и другие.

**В: Почему стоит использовать штрих‑коды DataMatrix?**  
О: Штрих‑коды DataMatrix компактны, высоконадежны и могут хранить большие объёмы данных, что делает их идеальными для производства, логистики и здравоохранения.

**В: Где можно найти документацию по Aspose.BarCode for .NET?**  
О: Документацию можно найти по ссылке [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).

**В: Доступна ли бесплатная пробная версия Aspose.BarCode for .NET?**  
О: Да, бесплатную пробную версию можно скачать по [the free trial link](https://releases.aspose.com/).

**В: Где можно получить поддержку по Aspose.BarCode for .NET?**  
О: При возникновении вопросов или необходимости поддержки вы можете посетить форум Aspose.BarCode for .NET по адресу [the support forum](https://forum.aspose.com/c/barcode/13).

---

**Последнее обновление:** 2026-01-17  
**Тестировано с:** Aspose.BarCode 24.11 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}