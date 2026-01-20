---
date: 2026-01-20
description: Узнайте, как генерировать штрихкоды DataMatrix с коррекцией ошибок DataMatrix
  в .NET, используя Aspose.BarCode. Узнайте, как быстро генерировать штрихкоды.
linktitle: DataMatrix Versions
second_title: Aspose.BarCode .NET API
title: Создавать штрихкоды DataMatrix с коррекцией ошибок DataMatrix
url: /ru/net/datamatrix-barcode-reading/datamatrix-versions/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание штрих‑кодов DataMatrix с коррекцией ошибок datamatrix с использованием Aspose.BarCode для .NET

Если вы ищете надежное решение для создания штрих‑кодов DataMatrix в ваших .NET приложениях, Aspose.BarCode для .NET — это то, что вам нужно. В этом пошаговом руководстве мы покажем, **как создать штрих‑код** с полной поддержкой **коррекции ошибок datamatrix**, чтобы вы могли создавать надежные, сканируемые символы для различных бизнес‑сценариев.

## Быстрые ответы
- **Какая библиотека поддерживает коррекцию ошибок datamatrix?** Aspose.BarCode for .NET
- **Какой уровень ECC обеспечивает наибольшую защиту?** Ecc140 (обеспечивает более высокую избыточность)
- **Сколько строк кода требуется?** Менее 20 строк для базового штрих‑кода
- **Можно ли настроить строки и столбцы?** Да — задайте версию DataMatrix вручную
- **Требуется ли лицензия для продакшн?** Да, необходима коммерческая лицензия

## Обзор коррекции ошибок datamatrix
Коррекция ошибок DataMatrix (ECC) добавляет избыточные данные в символ, позволяя сканерам восстановить исходную информацию даже при повреждении части штрих‑кода. Aspose.BarCode позволяет выбирать между ECC200, ECC140 и другими уровнями, давая вам контроль над балансом между размером символа и его устойчивостью.

## Требования

Прежде чем перейти к коду, убедитесь, что у вас есть следующие требования:
- Среда разработки с поддержкой .NET.
- Копия Aspose.BarCode для .NET, которую можно скачать по [this link](https://releases.aspose.com/barcode/net/).
- Базовые знания C# и .NET Framework.

Теперь давайте изучим версии DataMatrix и способы их генерации с помощью Aspose.BarCode для .NET.

## Импорт пространств имён

В любом проекте C# необходимо импортировать требуемые пространства имён. Для Aspose.BarCode вам понадобится включить следующее:

```csharp
using Aspose.BarCode.Generation;
```

Это пространство имён предоставляет доступ к классу `BarcodeGenerator`, который необходим для генерации штрих‑кодов.

Теперь разберём пример на несколько шагов.

## Шаг 1: Установите путь к каталогу

Начните с определения пути к каталогу, где вы хотите сохранять сгенерированные штрих‑коды DataMatrix.

```csharp
string path = "Your Directory Path";
```

Замените `"Your Directory Path"` на фактический путь, где вы хотите сохранять изображения штрих‑кодов.

## Шаг 2: Инициализируйте генератор штрих‑кодов

Создайте экземпляр класса `BarcodeGenerator` и укажите тип штрих‑кода как `DataMatrix`. Вы также можете задать данные, которые необходимо закодировать в штрих‑коде.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Code for generating barcodes goes here
}
```

## Шаг 3: Настройте свойства штрих‑кода для коррекции ошибок datamatrix

Вы можете настроить различные свойства штрих‑кода DataMatrix, такие как его размеры и тип ECC (Error Correction Code). Ниже пример установки X‑размера в 4 пикселя и выбора ECC200:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4;
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

## Шаг 4: Установите версию DataMatrix и сохраните

Вы можете задать версию DataMatrix, указав количество строк и столбцов. После настройки версии сохраните изображение штрих‑кода.

Например, чтобы создать штрих‑код DataMatrix с 22 строками и 22 столбцами, используя ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC200_22x22;
generator.Save($"{path}DataMatrixRows22Columns22Ecc200.png", BarCodeImageFormat.Png);
```

Аналогично, вы можете генерировать штрих‑коды с другими параметрами, изменяя версию и тип ECC по необходимости.

## Шаг 5: Повторите для других версий

Вы можете повторить Шаг 4 для других версий DataMatrix. Например, чтобы создать штрих‑код с 12 строками и 64 столбцами, используя ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.DMRE_12x64;
generator.Save($"{path}DataMatrixRows12Columns64Ecc200.png", BarCodeImageFormat.Png);
```

## Шаг 6: Переключите типы ECC

Если вы хотите изменить тип ECC на Ecc140, сделайте это, обновив свойство ECC:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;
```

## Шаг 7: Генерируйте штрих‑коды с разными версиями и ECC

Повторите Шаг 4 для других версий DataMatrix и типов ECC, сохраняя каждый штрих‑код под уникальным именем файла.

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC000_140_29x29;
generator.Save($"{path}DataMatrixRows29Columns29Ecc140.png", BarCodeImageFormat.Png);
```

Теперь, когда вы узнали, как генерировать штрих‑коды DataMatrix с помощью Aspose.BarCode для .NET, вы можете легко интегрировать эту возможность в свои .NET приложения.

## Заключение

Aspose.BarCode для .NET упрощает процесс создания штрих‑кодов DataMatrix в ваших .NET приложениях. С этим пошаговым руководством вы можете создавать штрих‑коды с разными версиями и типами ECC, предоставляя гибкость и возможность настройки под ваши конкретные требования.

Если у вас есть вопросы или нужна помощь, не стесняйтесь посетить [документацию Aspose.BarCode для .NET](https://reference.aspose.com/barcode/net/) или заглянуть на [форум Aspose.BarCode](https://forum.aspose.com/c/barcode/13) за поддержкой.

 сскими размерами, используя, вы можете настраивать размеры штрих‑кодов DataMatrix, задавая количество строк и столбцов,A3: Вы можете скачать Aspose.BarCode для .NET по [this link](https://releases.aspose.com/barcode/net/).

### Вопрос 4: Доступна ли бесплатная пробная версия Aspose.BarCode для .NET?

A4: Да, бесплатную пробную версию Aspose.BarCode для .NET можно получить [здесь](https://releases.aspose.com/).

### Вопрос 5: Как получить временную лицензию?

A5: Чтобы получить временную лицензию для Aspose.BarCode для .NET, посетите [this link](https://purchase.aspose.com/temporary-license/).

## уровень ECCитесь на устойчивость к повреждениям.

**Вопрос: Могу ли я генерировать штрих‑коды в форматах, отличных от PNG?**  
**Ответ:** Конечно — BarCodeImageFormat поддерживает JPEG, BMP, GIF и другие форматы.

**Вопрос: Что делать, если нужно генерировать множество штрих‑кодов в цикле?**  
**Ответ:** Создайте один экземпляр `BarcodeGenerator`, обновляйте данные и версию внутри цикла и вызывайте `Save` для каждой итерации, чтобы повысить производительность.

---

**Последнее обновление:** 2026-01-20  
**Тестировано с:** Aspose.BarCode 24.11 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}