---
title: Создавайте штрих-коды DataMatrix с помощью Aspose.BarCode для .NET
linktitle: Версии DataMatrix
second_title: API Aspose.BarCode .NET
description: Узнайте, как генерировать штрих-коды DataMatrix в .NET с помощью Aspose.BarCode для .NET. Пользовательские размеры, поддержка ECC и многое другое.
type: docs
weight: 12
url: /ru/net/datamatrix-barcode-reading/datamatrix-versions/
---
Если вы ищете надежное решение для создания штрих-кодов DataMatrix в ваших .NET-приложениях, вам подойдет Aspose.BarCode for .NET. В этом пошаговом руководстве мы покажем вам процесс использования Aspose.BarCode для .NET для создания штрих-кодов DataMatrix. Мы разобьем каждый пример на несколько шагов, чтобы вы могли легко следовать им.

## Предварительные условия

Прежде чем мы углубимся в код, убедитесь, что у вас есть следующие предварительные условия:
- Среда разработки с поддержкой .NET.
- Копия Aspose.BarCode для .NET, которую можно загрузить с сайта[эта ссылка](https://releases.aspose.com/barcode/net/).
- Базовые знания C# и .NET framework.

Теперь давайте рассмотрим версии DataMatrix и способы их создания с помощью Aspose.BarCode для .NET.

## Импортировать пространства имен

В любом проекте C# важно импортировать необходимые пространства имен. В случае Aspose.BarCode вам необходимо включить следующее:

```csharp
using Aspose.BarCode.Generation;
```

 Это пространство имен обеспечивает доступ к`BarcodeGenerator` класс, который имеет решающее значение для генерации штрих-кодов.

Теперь давайте разобьем пример на несколько этапов.

## Шаг 1. Настройте путь к каталогу

Начните с определения пути к каталогу, в котором вы хотите сохранить сгенерированные штрих-коды DataMatrix.

```csharp
string path = "Your Directory Path";
```

 Заменять`"Your Directory Path"` с фактическим путем, по которому вы хотите сохранить изображения штрих-кода.

## Шаг 2. Инициализируйте генератор штрих-кода

 Создайте экземпляр`BarcodeGenerator` class и укажите тип штрих-кода как`DataMatrix`. Вы также можете предоставить данные, которые хотите закодировать в штрих-коде.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Код для генерации штрих-кодов находится здесь
}
```

## Шаг 3. Настройте свойства штрих-кода

Вы можете настроить различные свойства штрих-кода DataMatrix, такие как его размеры и тип ECC (код исправления ошибок). Вот пример установки размера X на 4 пикселя и выбора ECC200:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4;
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

## Шаг 4. Установите версию DataMatrix и сохраните

Вы можете указать версию DataMatrix, задав количество строк и столбцов. После настройки версии сохраните изображение штрих-кода.

Например, чтобы создать штрих-код DataMatrix с 22 строками и 22 столбцами с использованием ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC200_22x22;
generator.Save($"{path}DataMatrixRows22Columns22Ecc200.png", BarCodeImageFormat.Png);
```

Аналогичным образом вы можете создать штрих-код с различными параметрами, изменив при необходимости версию и тип ECC.

## Шаг 5. Повторите действия для других версий.

Вы можете повторить шаг 4 для других версий DataMatrix. Например, чтобы создать штрих-код с 12 строками и 64 столбцами с использованием ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.DMRE_12x64;
generator.Save($"{path}DataMatrixRows12Columns64Ecc200.png", BarCodeImageFormat.Png);
```

## Шаг 6. Переключите типы ECC

Если вы хотите изменить тип ECC на Ecc140, вы можете сделать это, обновив свойство ECC:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;
```

## Шаг 7. Создайте штрих-коды с разными версиями и ECC

Повторите шаг 4 для других версий DataMatrix и типов ECC, сохраняя каждый штрих-код под уникальным именем файла.

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC000_140_29x29;
generator.Save($"{path}DataMatrixRows29Columns29Ecc140.png", BarCodeImageFormat.Png);
```

Теперь, когда вы научились генерировать штрих-коды DataMatrix с помощью Aspose.BarCode для .NET, вы можете легко интегрировать эту функцию в свои .NET-приложения.

## Заключение

Aspose.BarCode для .NET упрощает процесс создания штрих-кодов DataMatrix в ваших .NET-приложениях. С помощью этого пошагового руководства вы сможете создавать штрих-коды различных версий и типов ECC, обеспечивая гибкость и настройку в соответствии с вашими конкретными потребностями.

 Если у вас есть какие-либо вопросы или вам нужна помощь, не стесняйтесь посетить[Документация Aspose.BarCode для .NET](https://reference.aspose.com/barcode/net/) или проверьте[Форум Aspose.BarCode](https://forum.aspose.com/c/barcode/13) для поддержки.

## Часто задаваемые вопросы

### Вопрос 1. Что такое ECC в штрих-кодах DataMatrix?

A1: ECC (код исправления ошибок) — это жизненно важный компонент штрих-кодов DataMatrix, который помогает обеспечить целостность данных. Различные уровни ECC обеспечивают различную степень исправления ошибок.

### Вопрос 2. Могу ли я генерировать штрих-коды DataMatrix с нестандартными размерами, используя Aspose.BarCode для .NET?

О2: Да, вы можете настроить размеры штрих-кодов DataMatrix, задав количество строк и столбцов, как показано в руководстве.

### Вопрос 3: Где я могу скачать Aspose.BarCode для .NET?

 A3: Вы можете скачать Aspose.BarCode для .NET с сайта[эта ссылка](https://releases.aspose.com/barcode/net/).

### Вопрос 4. Существует ли бесплатная пробная версия Aspose.BarCode для .NET?

 О4: Да, вы можете получить доступ к бесплатной пробной версии Aspose.BarCode для .NET.[здесь](https://releases.aspose.com/).

### Вопрос 5: Как я могу получить временную лицензию на Aspose.BarCode для .NET?

 A5: Чтобы получить временную лицензию на Aspose.BarCode для .NET, посетите[эта ссылка](https://purchase.aspose.com/temporary-license/).