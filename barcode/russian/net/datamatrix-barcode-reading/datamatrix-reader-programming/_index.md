---
date: 2026-01-30
description: Узнайте, как создавать штрих‑код DataMatrix и использовать считыватель
  штрих‑кодов в C#. Это руководство охватывает генерацию штрих‑кодов с помощью Aspose,
  их чтение и программирование считывателя с использованием Aspose.BarCode для .NET.
linktitle: DataMatrix Reader Programming
second_title: Aspose.BarCode .NET API
title: Как создать штрих‑код DataMatrix с помощью Aspose.BarCode для .NET
url: /ru/net/datamatrix-barcode-reading/datamatrix-reader-programming/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать штрих‑код DataMatrix и считать его с помощью Aspose.BarCode для .NET

Готовы открыть для себя мир программирования считывателей штрих‑кодов DataMatrix с Aspose.BarCode для .NET? В этом руководстве вы **создадите изображения штрих‑кода DataMatrix**, внедрите данные программирования считывателя и научитесь **использовать функциональность считывателя штрих‑кодов** в приложении на C#. В конце у вас будет надёжный, готовый к продакшну пример, который можно сразу добавить в свои проекты.

## Быстрые ответы
- **Что я могу получить?** Сгенерировать штрих‑код DataMatrix и считать его флаг программирования считывателя.  
- **Какая библиотека?** Aspose.BarCode для .NET (поддерживает .NET Framework и .NET Core).  
- **Основной язык?** C# – код работает в Visual Studio 2022 и новее.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для разработки; для продакшна требуется коммерческая лицензия.  
- **Сколько времени займет?** Около 10‑15 минут, чтобы скопировать, запустить и адаптировать пример.

## Что такое программирование «создать штрих‑код DataMatrix»?
Создание штрих‑кода DataMatrix означает кодирование данных в двумерную матрицу чёрных и белых ячеек. Когда установлен флаг **IsReaderProgramming**, штрих‑код также содержит инструкции, которые некоторые сканеры могут использовать для автоматической настройки себя.

## Почему стоит использовать Aspose.BarCode для .NET?
Aspose.BarCode предоставляет единый, хорошо документированный API для сценариев **генерации штрих‑кода Aspose** и **использования считывателя штрих‑кода**. Он поддерживает новейшие версии .NET, обеспечивает высокопроизводительное кодирование/декодирование и не требует внешних нативных зависимостей.

## Предварительные требования
1. **Visual Studio** (любая современная версия) с установленным .NET Framework или .NET Core SDK.  
2. **Aspose.BarCode для .NET** – загрузите с [страницы загрузки](https://releases.aspose.com/barcode/net/).  
3. Базовые знания **C#** – в примере используются только стандартные классы .NET.

## Подключение пространств имён
В .NET необходимо импортировать нужные пространства имён, чтобы компилятор знал, где находятся классы штрих‑кода.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

## Как программно создать штрих‑код DataMatrix

### Шаг 1: Определите путь к каталогу
Укажите папку, в которой будет сохранено сгенерированное изображение.

```csharp
string path = "Your Directory Path";
```

### Шаг 2: Инициализируйте BarcodeGenerator
Создайте экземпляр `BarcodeGenerator`, выберите **EncodeTypes.DataMatrix** и включите программирование считывателя.

```csharp
System.Console.WriteLine("DataMatrixReaderProgramming:");

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    // Set a flag that indicates data is encoded for reader programming
    generator.Parameters.Barcode.DataMatrix.IsReaderProgramming = true;
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

### Шаг 3: Сгенерируйте изображение штрих‑кода
Вызов ниже отрисовывает штрих‑код в объект `Bitmap`.

```csharp
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

### Шаг 4: Используйте считыватель штрих‑кода для проверки флага
Теперь прочитайте изображение обратно с помощью **BarCodeReader** и подтвердите наличие флага **IsReaderProgramming**.

```csharp
    using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
    {
        reader.ReadBarCodes();
        Console.WriteLine("Is reader programming: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.IsReaderProgramming);
    }
}
```

## Распространённые проблемы и их решение
- **Недопустимый путь** – убедитесь, что папка в `path` существует и приложение имеет права записи.  
- **Отсутствует лицензия** – запуск без действующей лицензии добавит водяной знак к сгенерированному изображению.  
- **Неподдерживаемая версия .NET** – проверьте, что вы используете поддерживаемый фреймворк (например, .NET 6, .NET Framework 4.7.2).  

## Часто задаваемые вопросы

### Q1: Что такое программирование считывателя DataMatrix?
A1: Программирование считывателя DataMatrix подразумевает кодирование данных в формате штрих‑кода DataMatrix, который может быть легко считан сканерами или программным обеспечением. Такое программирование часто используется в отраслях, таких как производство, здравоохранение и логистика, для хранения и извлечения данных.

### Q2: Почему выбирать Aspose.BarCode для .NET?
A2: Aspose.BarCode для .NET – это надёжная и универсальная библиотека, упрощающая генерацию, чтение и манипуляцию штрих‑кодами в .NET‑приложениях. Она предоставляет широкую поддержку различных типов штрих‑кодов, что делает её предпочтительным выбором для разработчиков.

### Q3: Можно ли использовать Aspose.BarCode бесплатно?
A3: Aspose.BarCode предлагает бесплатную пробную версию для оценки. Однако для коммерческого использования необходимо приобрести лицензию. Лицензию можно получить по [этой ссылке](https://purchase.aspose.com/buy).

### Q4: Как получить временную лицензию для Aspose.BarCode?
A4: Если нужна временная лицензия для краткосрочных проектов, её можно получить по [этой ссылке](https://purchase.aspose.com/temporary-license/).

### Q5: Совместима ли Aspose.BarCode с последним .NET Framework?
A5: Да, Aspose.BarCode для .NET разработана так, чтобы быть совместимой с различными версиями .NET Framework, включая последние релизы.

## Часто задаваемые вопросы (дополнительно)

**В: Как сгенерировать штрих‑код DataMatrix в C# без программирования считывателя?**  
О: Просто опустите строку `generator.Parameters.Barcode.DataMatrix.IsReaderProgramming = true;`, и штрих‑код будет сгенерирован обычным способом.

**В: Можно ли считывать другие типы штрих‑кодов тем же считывателем?**  
О: Да, `BarCodeReader` поддерживает множество символогий. Замените `DecodeType.DataMatrix` на нужный тип (например, `DecodeType.QR`).

**В: Поддерживает ли Aspose.BarCode .NET Core / .NET 5+?**  
О: Абсолютно. Библиотека полностью совместима с .NET Core 3.1, .NET 5, .NET 6 и более новыми версиями.

**В: Есть ли способ пакетной обработки нескольких изображений?**  
О: Оберните логику `BarCodeReader` в цикл, который проходит по коллекции путей к файлам или объектам `Bitmap`.

## Заключение
Matrix**, внедрить данные программирования считывателя и **использовать возможности считывателя штрих‑кода** с Aspose.BarCode для .NET. Экспериментируйте с различными значениями `XDimension`, добавляйте пользовательский текст или интегрируйте код в более крупные системы управления запасами.

Для более подробной информации изучайте официальную [документацию](https://reference.aspose.com/barcode/net/) или присоединяйтесь к сообществу на [форуме поддержки Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Последнее обновление:** 2026-01-30  
**Тестировано с:** Aspose.BarCode 24.12 для .NET  
**Автор:** Aspose  

---