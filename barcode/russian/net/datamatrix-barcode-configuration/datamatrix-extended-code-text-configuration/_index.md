---
title: Настройка текста кода DataMatrix с помощью Aspose.BarCode для .NET
linktitle: Конфигурация расширенного текста кода DataMatrix
second_title: API Aspose.BarCode .NET
description: Научитесь настраивать текст расширенного кода DataMatrix с помощью Aspose.BarCode для .NET. Создавайте, распознавайте и интегрируйте штрих-коды в свои приложения .NET.
weight: 17
url: /ru/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Настройка текста кода DataMatrix с помощью Aspose.BarCode для .NET

В мире разработки программного обеспечения интеграция штрих-кодов стала насущной необходимостью для различных приложений. С помощью таких библиотек, как Aspose.BarCode для .NET, вы можете легко создавать и распознавать штрих-коды в своих .NET-приложениях. В этом руководстве вы узнаете, как настроить текст расширенного кода DataMatrix с помощью Aspose.BarCode для .NET. Прежде чем мы углубимся в детали, давайте взглянем на необходимые условия для этого руководства.

## Предварительные условия

Прежде чем приступить к работе, убедитесь, что у вас есть следующее:

1. Aspose.BarCode для библиотеки .NET
Вам потребуется установить Aspose.BarCode для .NET. Если вы еще этого не сделали, вы можете скачать его с сайта.[здесь](https://releases.aspose.com/barcode/net/).

2. Среда разработки .NET
Чтобы следовать этому руководству, в вашей системе должна быть настроена среда разработки .NET. Вы можете использовать Visual Studio или любую другую предпочтительную IDE.

3. Базовые знания C#
Для изучения этого руководства необходимо базовое понимание программирования на C#.

Теперь, когда у вас есть необходимые инструменты и знания, давайте разобьем процесс настройки текста расширенного кода DataMatrix с помощью Aspose.BarCode для .NET на простые пошаговые инструкции.

## Импортировать пространства имен

Первым шагом в работе с Aspose.BarCode для .NET является импорт необходимых пространств имен. Добавьте в свой код следующие пространства имен:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Эти пространства имен предоставляют необходимые классы и методы для работы со штрих-кодами.

## Шаг 1. Конфигурация расширенного текста кода DataMatrix

На этом этапе мы покажем вам процесс настройки расширенного текста кода DataMatrix.

## Шаг 2. Определите путь к каталогу

 Вам необходимо указать путь к каталогу, в котором вы хотите сохранить сгенерированный штрих-код DataMatrix. Заменять`"Your Directory Path"` с фактическим путем в вашей системе.

```csharp
string path = "Your Directory Path";
```

## Шаг 3. Создайте кодовый текст

 Чтобы создать кодовый текст для штрих-кода DataMatrix, вы будете использовать`DataMatrixExtCodetextBuilder`. Этот конструктор позволяет добавлять различные типы кодового текста с разными кодировками.

```csharp
DataMatrixExtCodetextBuilder codetextBuilder = new DataMatrixExtCodetextBuilder();
codetextBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
codetextBuilder.AddECICodetextWithEncodeMode(ECIEncodings.UTF8, DataMatrixEncodeMode.C40, "ABCDE");
codetextBuilder.AddPlainCodetext("test");
codetextBuilder.AddCodetextWithEncodeMode(DataMatrixEncodeMode.Text, "abcde");
```

Этот код настраивает кодовый текст, используя сочетание различных кодировок.

## Шаг 4: Создайте кодовый текст

После настройки текста кода сгенерируйте строку текста кода DataMatrix.

```csharp
string codetext = codetextBuilder.GetExtendedCodetext();
```

## Шаг 5. Создайте штрих-код DataMatrix

Теперь создайте штрих-код DataMatrix, используя сгенерированный кодовый текст. Вы также можете установить различные параметры для штрих-кода, такие как размер X и отображение текста кода.

```csharp
using (var generator = new BarcodeGenerator(EncodeTypes.DataMatrix, codetext))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended Codetext";
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ExtendedCodetext;

    generator.Save($"{path}DataMatrixExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Этот код генерирует и сохраняет изображение штрих-кода DataMatrix с указанными настройками.

## Шаг 6: Попытайтесь распознать

 Чтобы обеспечить распознавание штрих-кода, вы можете использовать`BarCodeReader`класс для чтения штрих-кода.

```csharp
using (var reader = new BarCodeReader(generator.GenerateBarCodeImage(), DecodeType.DataMatrix))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("DataMatrixExtendedCodetext:" + result.CodeText);
}
```

На этом этапе проверяется сгенерированный штрих-код, пытаясь его распознать.

Поздравляем! Вы успешно настроили расширенный текст кода DataMatrix с помощью Aspose.BarCode для .NET. Теперь вы можете интегрировать эту функцию в свои приложения .NET.

## Заключение

В этом руководстве мы рассмотрели процесс настройки текста расширенного кода DataMatrix с помощью Aspose.BarCode для .NET. Мы рассмотрели предварительные условия, пошаговые инструкции и продемонстрировали, как генерировать и распознавать штрих-код. Обладая этими знаниями, вы можете улучшить свои приложения .NET, добавив возможности создания и распознавания штрих-кодов.

## Часто задаваемые вопросы

### Вопрос 1. Что такое Aspose.BarCode для .NET?

A1: Aspose.BarCode для .NET — это мощная библиотека, которая позволяет разработчикам создавать и распознавать штрих-коды в приложениях .NET. Он поддерживает широкий спектр символики штрих-кодов и предлагает различные возможности настройки.

### Вопрос 2. Где я могу найти документацию по Aspose.BarCode для .NET?

A2: Вы можете получить доступ к документации по Aspose.BarCode для .NET.[здесь](https://reference.aspose.com/barcode/net/).

### Вопрос 3. Существует ли бесплатная пробная версия Aspose.BarCode для .NET?

 О3: Да, вы можете получить бесплатную пробную версию Aspose.BarCode для .NET.[здесь](https://releases.aspose.com/).

### Вопрос 4: Как получить временную лицензию на Aspose.BarCode для .NET?

 О4: Если вам нужна временная лицензия для целей тестирования или оценки, вы можете получить ее.[здесь](https://purchase.aspose.com/temporary-license/).

### Вопрос 5: Где я могу получить поддержку или задать вопросы об Aspose.BarCode для .NET?

 О5: Для получения поддержки или вопросов, связанных с Aspose.BarCode для .NET, вы можете посетить форум Aspose.BarCode.[здесь](https://forum.aspose.com/c/barcode/13).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
