---
date: 2026-03-07
description: Узнайте, как создавать одноразмерные штрихкоды Databar, закодированные
  по стандарту GS1, в .NET с помощью Aspose.BarCode. В этом руководстве показано,
  как установить GS1, настроить генератор штрихкодов и быстро генерировать штрихкоды.
linktitle: One-Dimensional Databar GS1 Encoding
second_title: Aspose.BarCode .NET API
title: Создать одностороннее кодирование Databar GS1 с помощью Aspose.BarCode
url: /ru/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание одномерного Databar с кодированием GS1 с помощью Aspose.BarCode

В этом руководстве вы **создадите одномерные databar** штрихкоды, соответствующие стандарту GS1, используя библиотеку Aspose.BarCode для .NET. Независимо от того, нужна ли вам строгая проверка GS1 или более гибкий штрихкод, мы пройдем каждый шаг — от установки библиотеки до обработки исключений кодирования — чтобы вы могли генерировать надёжные штрихкоды в своих приложениях.

## Быстрые ответы
- **Что означает «create one-dimensional databar»?** Это генерирование линейного (1‑D) штрихкода семейства Databar, часто используемого в розничной торговле и логистике.  
- **Как установить проверку GS1?** Установите `IsAllowOnlyGS1Encoding` в `true` в параметрах `DataBar`.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для разработки; для продакшн требуется коммерческая лицензия.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Где можно скачать библиотеку?** На официальной странице релизов Aspose (см. требования).

## Что такое «create one-dimensional databar»?
Одномерный Databar (также известный как RSS) — это компактный линейный штрихкод, способный кодировать числовые данные, даты или строки AI (Application Identifier). При использовании кодирования GS1 штрихкод следует глобально признанной структуре данных, что делает его идеальным для розничной торговли, здравоохранения и цепочек поставок.

## Почему стоит использовать Aspose.BarCode для .NET?
Aspose.BarCode предоставляет удобный API, полную поддержку GS1 и возможность точно настраивать каждый визуальный аспект штрихкода. Он устраняет догадки при низкоуровневом кодировании и позволяет сосредоточиться на бизнес‑логике.

## Требования

1. **Aspose.BarCode for .NET** – скачайте и установите его с [here](https://releases.aspose.com/barcode/net/).  
2. **Your Directory Path** – замените `"Your Directory Path"` в примерах на папку, в которой у вас есть права записи.

## Импорт пространств имён

Добавьте необходимые директивы `using` в начало вашего C# файла:

```csharp
using Aspose.BarCode;
using System;
```

## Шаг 1: Инициализация генератора штрихкода

Создайте экземпляр `BarcodeGenerator` и укажите символьный набор Databar Expanded:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## Шаг 2: Как установить GS1 – Генерация штрихкода со строгой проверкой GS1

Включите кодирование только GS1, задайте кодтекст, соответствующий GS1, и сохраните изображение:

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## Шаг 3: Генерация штрихкода с Aspose – Переменное кодирование (без проверки GS1)

Если вам нужен штрихкод, который **не** применяет правила GS1, отключите проверку:

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## Шаг 4: Проверка GS1 генератора штрихкода – Обработка исключения

Когда `IsAllowOnlyGS1Encoding` установлен в `true`, но кодтекст не соответствует GS1, Aspose генерирует исключение. Ниже показан шаблон, как его перехватить и записать в лог:

```csharp
try
{
    gen.CodeText = "ASPOSE";
    gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### Распространённые ошибки и советы
- **Ошибка:** Предоставление строки, не соответствующей GS1, при включённой проверке GS1 приведёт к отмене генерации штрихкода.  
- **Совет:** Проверьте строки AI перед присвоением их `CodeText`, чтобы избежать ошибок во время выполнения.  
- **Подсказка:** Используйте абсолютные пути или `Path.Combine` для безопасного построения имён файлов на разных платформах.

## Заключение

Теперь вы знаете, как **создавать одномерные databar** штрихкоды с кодированием GS1, как переключать проверку GS1 и как обрабатывать связанные исключения — всё с помощью Aspose.BarCode для .NET. Не стесняйтесь исследовать дополнительные параметры оформления, такие как размер штрихкода, цвет и отступы, через объект `Parameters.Barcode`.

Если возникнут проблемы, официальная документация и форум сообщества — отличные ресурсы:

- [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/)  
- [Aspose.BarCode support forum](https://forum.aspose.com/c/barcode/13)

## Часто задаваемые вопросы

### 1. Что такое кодирование GS1 в штрихкодах?
Кодирование GS1 — это стандартизированный способ структурировать данные (например, идентификаторы продуктов) внутри штрихкода, обеспечивая совместимость между розничными продавцами, производителями и логистическими провайдерами.

### 2. Можно ли настроить внешний вид сгенерированных штрихкодов?
Да. Aspose.BarCode позволяет регулировать размер, цвета, отступы и даже добавлять человекочитаемый текст через настройки `Parameters.Barcode`.

### 3. Где можно найти дополнительные ресурсы и документацию по Aspose.BarCode?
Полную документацию и примеры можно найти на странице [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/). Это ценный ресурс для обучения и устранения неполадок.

### 4. Есть ли пробная версия Aspose.BarCode?
Да, бесплатную пробную версию Aspose.BarCode для .NET можно получить по ссылке [here](https://releases.aspose.com/).

### 5. Как приобрести лицензию на Aspose.BarCode для .NET?
Чтобы приобрести лицензию на Aspose.BarCode для .NET, посетите страницу [purchase page](https://purchase.aspose.com/buy) на сайте Aspose.

---

**Последнее обновление:** 2026-03-07  
**Тестировано с:** Aspose.BarCode 24.11 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}