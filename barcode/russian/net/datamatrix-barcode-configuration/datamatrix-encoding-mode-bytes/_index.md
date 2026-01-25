---
date: 2026-01-25
description: Узнайте, как создавать PNG‑файлы штрихкодов с помощью Aspose.BarCode
  для .NET, кодируя DataMatrix в режиме Bytes. Следуйте этому руководству по генерации
  штрихкодов для простой реализации.
linktitle: DataMatrix Encoding Mode (Bytes)
second_title: Aspose.BarCode .NET API
title: Создать PNG штрихкода с помощью Aspose.BarCode для .NET – байты DataMatrix
url: /ru/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание PNG‑штрихкода – кодирование DataMatrix в режиме Bytes с Aspose.BarCode для .NET

В этом руководстве вы узнаете, **как создавать PNG‑изображения штрихкодов** с помощью Aspose.BarCode для .NET. Мы пройдём полный **путеводитель по генерации штрихкодов** для DataMatrix — в частности в режиме кодирования Bytes—чтобы вы могли генерировать, отображать и считывать штрихкоды DataMatrix в своих .NET‑приложениях.

## Быстрые ответы
- **Что означает “create barcode PNG”?** Это генерация растрового PNG‑изображения, содержащего штрихкод.
- **Какая библиотека лучше всего подходит?** Aspose.BarCode для .NET предоставляет полнофункциональный API для создания и распознавания штрихкодов.
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для разработки; коммерческая лицензия требуется для продакшна.
- **Можно ли считать штрихкод обратно?** Да, та же библиотека включает BarCodeReader для **чтения данных штрихкода DataMatrix**.
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Как создать PNG‑штрихкод с Aspose.BarCode для .NET
Ниже вы найдёте всё необходимое — от требований до пошагового разбора кода, который позволит вам **создать PNG‑штрихкод**, задать отображаемый текст и проверить результат встроенным считывателем.

## Требования

Прежде чем приступить к процессу кодирования, убедитесь, что у вас есть следующие условия:

1. Aspose.BarCode для .NET: Чтобы начать, необходимо установить библиотеку Aspose.BarCode для .NET. Скачать её можно [здесь](https://releases.aspose.com/barcode/net/).

2. Среда разработки: Убедитесь, что у вас настроена среда разработки, включая Visual Studio или любую другую IDE по вашему выбору.

3. Базовые знания C#: В этом руководстве предполагается, что вы знакомы с программированием на C#.

С этими условиями вы готовы начать кодировать данные в формате DataMatrix в режиме Bytes.

## Импорт пространств имён

Чтобы использовать Aspose.BarCode для .NET, необходимо импортировать нужные пространства имён в ваш C#‑код. Добавьте следующие строки в начало файла кода:

```csharp
using System;
using System.Text;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Теперь разберём процесс кодирования данных в формате DataMatrix в режиме Bytes на несколько шагов.

## Шаг 1: Инициализация BarcodeGenerator

Создайте объект BarcodeGenerator, указав EncodeType как DataMatrix и данные, которые нужно закодировать. Вместо `"Your Directory Path"` подставьте реальный путь, где будет сохранено изображение штрихкода.

```csharp
string path = "Your Directory Path";
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, strBld.ToString()))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
```

## Шаг 2: Установка режима кодирования DataMatrix в Bytes

Установите режим кодирования DataMatrix в Bytes с помощью следующего кода:

```csharp
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Bytes;
```

## Шаг 3: Задание отображаемого текста

Можно задать отображаемый текст для штрихкода. В этом примере мы установили его как «Bytes mode».

```csharp
    gen.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Bytes mode";
```

## Шаг 4: Сохранение изображения штрихкода

Сохраните сгенерированное изображение штрихкода по указанному пути. В данном случае файл будет назван «DataMatrixEncodeModeBytes.png».

```csharp
    gen.Save($"{path}DataMatrixEncodeModeBytes.png", BarCodeImageFormat.Png);
```

## Шаг 5: Попытка распознавания

Теперь попробуем распознать закодированный штрихкод DataMatrix. Для этого используем BarCodeReader.

```csharp
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
```

## Шаг 6: Итерация и вывод результатов

Пройдитесь по результатам и выведите закодированные данные.

```csharp
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixEncodeModeBytes:" + BitConverter.ToString(result.CodeBytes));
    }
}
```

С помощью этих шагов вы успешно **создали PNG‑штрихкод** в режиме DataMatrix Bytes с Aspose.BarCode для .NET. Эта мощная библиотека упрощает генерацию и распознавание штрихкодов, делая её незаменимым инструментом для разработчиков.

Теперь вы готовы интегрировать кодирование и декодирование штрихкодов в свои .NET‑приложения с лёгкостью, благодаря Aspose.BarCode.

## Заключение

В этом руководстве мы рассмотрели, как с помощью Aspose.BarCode для .NET **создавать PNG‑файлы штрихкодов** в формате DataMatrix в режиме Bytes. Следуя этим простым шагам, вы сможете обогатить свои приложения надёжными возможностями генерации и распознавания штрихкодов. Если возникнут проблемы, сообщество Aspose.BarCode готово помочь.

Если у вас есть вопросы или проблемы, не стесняйтесь обращаться за помощью к сообществу Aspose.BarCode по адресу [Aspose.BarCode Support](https://forum.aspose.com/c/barcode/13).

## Часто задаваемые вопросы

### Q1: Что такое режим кодирования DataMatrix?

A1: Режим кодирования DataMatrix — это метод, используемый для преобразования данных в двумерный штрихкод. Он предоставляет различные варианты кодирования, включая режим Bytes, подходящий для бинарных данных.

### Q2: Как получить бесплатную пробную версию Aspose.BarCode для .NET?

A2: Бесплатную пробную версию Aspose.BarCode для .NET можно получить [здесь](https://releases.aspose.com/).

### Q3: Где найти документацию по Aspose.BarCode для .NET?

A3: Документация по Aspose.BarCode для .NET доступна [здесь](https://reference.aspose.com/barcode/net/).

### Q4: Подходит ли Aspose.BarCode для .NET для коммерческого использования?

A4: Да, Aspose.BarCode для .NET подходит для коммерческого использования. Приобрести лицензию можно [здесь](https://purchase.aspose.com/buy).

### Q5: Можно ли использовать временную лицензию для Aspose.BarCode для .NET?

A5: Да, временную лицензию для Aspose.BarCode для .NET можно получить [здесь](https://purchase.aspose.com/temporary-license/).

## Часто задаваемые вопросы

**Q: Как **прочитать штрихкод DataMatrix** после его создания?**  
A: Используйте класс `BarCodeReader` с `DecodeType.DataMatrix`, как показано в Шаге 5 и Шаге 6 примера кода.

**Q: Можно ли изменить размер генерируемого PNG?**  
A: Да, отрегулируйте `gen.Parameters.Barcode.XDimension.Pixels` или задайте параметры `ImageWidth` и `ImageHeight` перед вызовом `Save`.

**Q: Что делать, если нужно закодировать текст вместо байтов?**  
A: Переключите режим кодирования на `DataMatrixEncodeMode.Text` и передайте строку, которую хотите закодировать.

**Q: Как скрыть человекочитаемый текст на штрихкоде?**  
A: Установите `gen.Parameters.Barcode.CodeTextParameters.ShowCodeText = false`, чтобы скрыть отображаемый текст.

**Q: Поддерживает ли Aspose.BarCode .NET Core?**  
A: Аб работает с .NET Core, .NET 5, .NET 6 и более новыми версиями.

---

**Последнее обновление:** 2026-01-25  
**Тестировано с:** Aspose.BarCode 24.11 для .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}