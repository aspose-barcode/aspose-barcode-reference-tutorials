---
category: general
date: 2026-07-18
description: Создайте изображения штрих‑кодов GS1 на C# с помощью этого пошагового
  руководства по генерации штрих‑кода в C# с использованием Aspose.BarCode — без лишних
  слов, только работающий код.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create gs1 barcode images
- how to generate barcode c#
language: ru
lastmod: 2026-07-18
og_description: Создайте изображения штрихкодов GS1 на C# с помощью этого краткого
  руководства. Узнайте, как генерировать штрихкоды в C# с использованием Aspose.BarCode
  и сохранять PNG‑файлы за считанные секунды.
og_image_alt: Screenshot of a generated GS1‑MicroPDF417 barcode saved as a PNG file
og_title: Создание изображений штрих‑кодов GS1 на C# — Полное руководство
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create GS1 barcode images in C# with this step‑by‑step guide on how
    to generate barcode C# using Aspose.BarCode – no fluff, just working code.
  headline: Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly
  type: TechArticle
tags:
- barcode
- csharp
- gs1
- aspose
title: Создание изображений штрих‑кодов GS1 в C# – Как быстро генерировать штрих‑код
  в C#
url: /ru/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание изображений штрих‑кодов GS1 в C# – Как генерировать штрих‑коды C#

Когда‑нибудь вам нужно было **create gs1 barcode images** для упаковочной этикетки, но вы не знали, с чего начать? Вы не одиноки. В этом руководстве вы увидите точно **how to generate barcode c#** код, который создает изображения GS1‑MicroPDF417 за считанные минуты.

Мы пройдем весь процесс — установку библиотеки, настройку генератора, замену данных AI (Application Identifier) и, наконец, сохранение набора PNG‑файлов. К концу вы получите готовое консольное приложение, которое выдаст несколько изображений штрих‑кодов GS1, каждое с разной комбинацией AI.

---

## Что понадобится

- **.NET 6+** (или .NET Framework 4.6+). Последняя версия среды выполнения лучше всего работает с Aspose.BarCode.
- **Aspose.BarCode for .NET** – установить через NuGet (`Install-Package Aspose.BarCode`).
- Папка на диске, куда будут записываться PNG‑файлы (мы назовём её `YOUR_DIRECTORY`).
- Базовое понимание синтаксиса C# — ничего сложного не требуется.

Если у вас уже есть всё это, отлично. Если нет, сначала скачайте пакет NuGet; это одна строка в консоли Package Manager Console, которая позаботится обо всех зависимостях.

---

## Шаг 1: Создайте минимальный консольный проект

Откройте любимую IDE (Visual Studio, Rider или VS Code) и создайте новый консольный проект:

```bash
dotnet new console -n Gs1BarcodeDemo
cd Gs1BarcodeDemo
dotnet add package Aspose.BarCode
```

Замените автоматически сгенерированный `Program.cs` кодом, показанным в следующих шагах. Этот скелет дает нам чистый лист для **create gs1 barcode images** без лишних деталей.

---

## Шаг 2: Как создать gs1 barcode images – инициализация генератора

Сердцем операции является `BarcodeGenerator`. Мы запустим его с начальным значением GS1‑MicroPDF417, например `(17)991231(10)ABCD`. Эта строка кодирует два AI: срок годности (17) и партия/лот (10).

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with a GS1‑MicroPDF417 barcode type
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(17)991231(10)ABCD");
```

**Почему это важно:** `EncodeTypes.GS1MicroPdf417` сообщает Aspose, что мы работаем с компактным, высокоплотным форматом GS1. Начало с корректной строки AI гарантирует, что первое PNG‑изображение уже соответствует стандартам GS1.

---

## Шаг 3: Настройте визуальные параметры – точная настройка размера и макета

Штрих‑код, который слишком маленький или имеет странную форму, не будет считываться. Здесь мы задаём X‑dimension (ширину модуля) в 2 пикселя, ограничиваем количество столбцов, чтобы изображение оставалось узким, и включаем связывание, чтобы при необходимости позже можно было соединять несколько штрих‑кодов.

```csharp
        // Set visual parameters for a crisp, scannable image
        barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;      // module width
        barcodeGen.Parameters.Barcode.Pdf417.Columns = 2;        // column count
        barcodeGen.Parameters.Barcode.Pdf417.IsLinked = true;   // enable linking
```

**Подсказка:** Если нужен более высокий штрих‑код, увеличьте `Rows` вместо столбцов. Поиграйте с `XDimension`, чтобы достичь минимального размера модуля 0,33 мм, требуемого большинством сканеров.

---

## Шаг 4: Сохраните первый штрих‑код – AI 17 + AI 10

Теперь мы действительно записываем изображение на диск. Имя файла отражает используемые AI, что упрощает последующее поиск.

```csharp
        // Save the first image (AI 17 + AI 10)
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_17_10.png",
                        BarCodeImageFormat.Png);
```

После запуска программы вы должны увидеть чёткое PNG‑изображение в `YOUR_DIRECTORY`. Откройте его — вы увидите крошечные полоски и человекочитаемый текст под ними. Это первое из множества **gs1 barcode images**, которые мы будем генерировать.

---

## Шаг 5: Измените закодированные данные – повторное использование того же генератора

Вместо создания нового `BarcodeGenerator` для каждой пары AI, мы просто меняем свойство `CodeText` и снова вызываем `Save`. Такой подход — самый эффективный способ **create gs1 barcode images** оптом.

```csharp
        // AI 15 (best before) + AI 10 (batch)
        barcodeGen.CodeText = "(15)991231(10)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_15_10.png",
                        BarCodeImageFormat.Png);

        // AI 13 (production date) + AI 21 (serial)
        barcodeGen.CodeText = "(13)991231(21)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_13_21.png",
                        BarCodeImageFormat.Png);

        // AI 11 (manufacture date) + AI 21 (serial)
        barcodeGen.CodeText = "(11)991231(21)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_11_21.png",
                        BarCodeImageFormat.Png);

        // Only AI 17 (expiration) – no batch number
        barcodeGen.CodeText = "(17)991231";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_17.png",
                        BarCodeImageFormat.Png);
```

**Почему повторное использование?** Изменение `CodeText` избавляет от накладных расходов на повторную инициализацию генератора и гарантирует одинаковые визуальные настройки для всех изображений.

---

## Шаг 6: Запустите, проверьте и настройте

Скомпилируйте и запустите:

```bash
dotnet run
```

Теперь у вас должно быть пять PNG‑файлов, каждый назван в соответствии с содержащейся парой AI. Откройте любой из них в просмотрщике изображений — вы увидите штрих‑код и закодированный текст под ним. Чтобы двойной проверкой убедиться в правильности данных, используйте бесплатное приложение‑сканер GS1 на телефоне — наведите его на PNG‑изображение на экране и посмотрите, какие значения AI появятся.

**Распространённые проблемы и как их избежать**

| Проблема | Причина | Решение |
|----------|---------|----------|
| Штрих‑код нечитаем | `XDimension` слишком низкое (например, 1 пиксель) | Увеличьте до 2 или 3 пикселей |
| Отсутствуют скобки AI | Неправильный формат `CodeText` | Всегда оборачивайте каждый AI в скобки |
| Изображение слишком большое | Слишком много столбцов/строк | Уменьшите `Columns` или позвольте Aspose автоматически подобрать размер |
| Ошибка выполнения `EncodeTypes` не найдено | Отсутствует `using Aspose.BarCode.Generation` | Добавьте недостающую директиву `using` |

---

## Шаг 7: Расширение примера – генерация дополнительных комбинаций AI

Если вам нужно **create gs1 barcode images** для десятков вариантов продукта, рассмотрите загрузку пар AI из CSV‑файла:

```csharp
using System.IO;

string[] lines = File.ReadAllLines(@"ai_pairs.csv"); // format: "(17)991231,(10)ABCD"
foreach (var line in lines)
{
    barcodeGen.CodeText = line.Replace(',', ' ');
    string fileName = $"GS1MicroPdf417_{line.Replace("(", "").Replace(")", "").Replace(",", "_")}.png";
    barcodeGen.Save(Path.Combine(@"YOUR_DIRECTORY", fileName), BarCodeImageFormat.Png);
}
```

Этот крошечный цикл читает каждую строку, меняет данные и сохраняет PNG с описательным именем — идеально для масштабных конвейеров печати этикеток.

---

## Заключение

Теперь у вас есть полностью готовая к запуску программа на C#, которая **creates gs1 barcode images** для множества сценариев с AI, демонстрируя самый простой способ **how to generate barcode c#** с использованием Aspose.BarCode. Переиспользуя один экземпляр `BarcodeGenerator`, настраивая визуальные параметры и меняя `CodeText`, вы сможете создавать столько соответствующих GS1‑MicroPDF417 PNG‑файлов, сколько потребуется вашему проекту.

Что дальше? Попробуйте добавить цвета (`barcodeGen.Parameters.Barcode.ForeColor`), внедрить штрих‑код в PDF или переключиться на другую симболику GS1, например DataMatrix. Тот же шаблон применим — инициализировать, настроить, задать `CodeText` и сохранить.

Не стесняйтесь оставить комментарий, если столкнётесь с проблемами, или поделиться своими вариантами. Приятного кодинга, и пусть ваши сканирования всегда проходят без ошибок!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Как создать тихую зону штрих‑кода для Code 16K с помощью Aspose.BarCode для .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Как создать тихую зону штрих‑кода для ITF-14 с помощью Aspose.BarCode для .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Как генерировать штрих‑код – конфигурация Code 39 с Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}