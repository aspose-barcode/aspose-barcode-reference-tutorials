---
date: 2026-01-02
description: Узнайте, как использовать генератор штрих‑кодов Aztec с Aspose.BarCode
  для .NET — пошаговое руководство по настройке режима символов Aztec (Auto, FullRange,
  Compact, Rune).
linktitle: Aztec Symbol Mode Example
second_title: Aspose.BarCode .NET API
title: Генератор штрихкодов Aztec – Освоение режима символов Aztec с Aspose.BarCode
  для .NET
url: /ru/net/aztec-barcode-encoding/aztec-symbol-mode-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# barcode generator aztec – Освоение режима Aztec Symbol с Aspose.BarCode для .NET

Если вы хотите добавить мощные возможности генерации штрих‑кодов в свои .NET‑приложения, **barcode generator aztec** от Aspose.BarCode для .NET — отличное решение. В этом руководстве мы подробно рассмотрим режим Aztec Symbol, покажем **как задать параметры aztec**, и пройдём через практические примеры кода, которые можно сразу вставить в проект.

## Быстрые ответы
- **Какой основной класс?** `BarcodeGenerator` из `Aspose.BarCode.Generation`.
- **Какие режимы Symbol доступны?** Auto, FullRange, Compact и Rune.
- **Нужна ли лицензия?** Временная лицензия подходит для тестирования; полная лицензия требуется для продакшена.
- **Можно ли изменить текст кода?** Да, задайте `gen.CodeText` перед сохранением.
- **Какие форматы изображений поддерживаются?** PNG, JPEG, BMP, GIF, TIFF и другие.

## Что такое barcode generator aztec?
barcode generator aztec создаёт двумерные коды Aztec — компактный матричный штрих‑код, способный хранить большой объём данных в небольшом пространстве. Он идеален для мобильных билетов, URL‑адресов и бинарных данных, где важна экономия места.

## Почему стоит использовать Aspose.BarCode для .NET?
- **Полная поддержка .NET** — работает с .NET Framework, .NET Core и .NET 5/6.  
- **Богатый набор функций** — несколько режимов Symbol, коррекция ошибок и широкие возможности кастомизации.  
- **Без внешних зависимостей** — генерируйте штрих‑коды полностью в процессе.  
- **Кросс‑платформенный** — работает на Windows, Linux и macOS.

## Предварительные требования

- Знания разработки на .NET.  
- Установленная Visual Studio.  
- Копия Aspose.BarCode для .NET. Скачать её можно [здесь](https://releases.aspose.com/barcode/net/).

Теперь, когда всё готово, давайте изучим параметры режима Aztec Symbol.

## Как задать режим Aztec Symbol с barcode generator aztec

### Импорт пространств имён

Сначала добавьте необходимое пространство имён в начало вашего C#‑файла:

```csharp
using Aspose.BarCode.Generation;
```

После импорта пространства имён вы можете приступить к созданию штрих‑кодов Aztec.

### Шаг 1: Настройка генератора штрих‑кода

Инициализируйте генератор с типом кодирования Aztec и укажите текст, который нужно закодировать:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

> **Совет:** используйте строку в кодировке UTF‑8 для международных символов, как показано выше.

### Шаг 2: Установка режима Symbol в Auto

Режим **Auto** позволяет библиотеке автоматически выбрать оптимальный размер на основе длины данных:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

Сгенерированный PNG будет сохранён в указанную папку.

### Шаг 3: Установка режима Symbol в FullRange

Если вы хотите, чтобы библиотека использовала весь диапазон размеров символов Aztec, выберите **FullRange**:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

### Шаг 4: Установка режима Symbol в Compact

Для более компактного штрих‑кода, сохраняющего хорошую читаемость, используйте **Compact**:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

### Шаг 5: Установка режима Symbol в Rune

Режим **Rune** предназначен для специальных случаев, когда требуется иной визуальный стиль:

```csharp
gen.CodeText = "123"; // Change the code text if needed
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

### Распространённые проблемы и решения

| Проблема | Решение |
|----------|----------|
| Изображение штрих‑кода пустое | Убедитесь, что `path` указывает на существующую директорию с правом записи. |
| Неподдерживаемые символы | Используйте только символы, поддерживаемые стандартом Aztec, или переключитесь на кодировку UTF‑8. |
| Неправильный размер символа | Поэкспериментируйте с `AztecSymbolMode.Auto`, чтобы библиотека выбрала лучший размер. |

## Часто задаваемые вопросы

**В: Какова цель режима Aztec Symbol при генерации штрих‑кода?**  
О: Он позволяет управлять визуальной плотностью и уровнем коррекции ошибок кода Aztec, подстраивая штрих‑код под ваши требования к пространству и читаемости.

**В: Можно ли изменить текст кода для штрих‑кодов Aztec в Aspose.BarCode для .NET?**  
О: Да, просто присвойте новую строку `gen.CodeText` перед вызовом `Save`.

**В: Есть ли бесплатная пробная версия Aspose.BarCode для .NET?**  
О: Да, её можно скачать бесплатно [здесь](https://releases.aspose.com/).

**В: Где найти полную документацию по Aspose.BarCode для .NET?**  
О: Полный справочник API доступен [здесь](https://reference.aspose.com/barcode/net/).

**В: Как получить временную лицензию для Aspose.BarCode для .NET?**  
О: Временную лицензию можно запросить по [этой ссылке](https://purchase.aspose.com/temporary-license/).

## Заключение

В этом руководстве мы рассмотрели всё, что нужно знать для работы с **barcode generator aztec** в Aspose.BarCode для .NET: от настройки генератора до освоения каждого режима Symbol (Auto, FullRange, Compact, Rune). С этими примерами вы теперь можете быстро и надёжно внедрять универсальные штрих‑коды Aztec в любые .NET‑приложения.

Если у вас остались вопросы, присоединяйтесь к сообществу Aspose.BarCode на их [форуме поддержки](https://forum.aspose.com/c/barcode/13).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Последнее обновление:** 2026-01-02  
**Тестировано с:** Aspose.BarCode 24.10 для .NET  
**Автор:** Aspose