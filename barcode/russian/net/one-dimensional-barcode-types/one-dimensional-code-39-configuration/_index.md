---
date: 2026-02-25
description: Узнайте, как генерировать изображения штрихкодов с помощью Aspose.BarCode
  для .NET. Это пошаговое руководство показывает, как создавать штрихкоды Code 39
  с контрольной суммой и без неё.
linktitle: One-Dimensional Code 39 Configuration
second_title: Aspose.BarCode .NET API
title: Как создать штрих‑код – настройка Code 39 с Aspose.BarCode
url: /ru/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Одномерная конфигурация Code 39

## Введение

В этом руководстве вы узнаете **как генерировать barcode** изображения, конкретно одно‑мерные штрих‑коды Code 39, используя Aspose.BarCode for .NET. Штрих‑коды играют решающую роль в современных бизнесах, от отслеживания запасов до обеспечения быстрого и точного получения данных. Aspose.BarCode for .NET — мощная библиотека, упрощающая генерацию и настройку штрих‑кодов в приложениях .NET. Это пошаговое руководство разбивает процесс на легко усваиваемые части, гарантируя, что даже разработчики, новые в генерации штрих‑кодов, смогут следовать.

## Быстрые ответы
- **Какова основная библиотека?** Aspose.BarCode for .NET  
- **Могу ли я создать barcode с контрольной суммой?** Yes – set `IsChecksumEnabled = EnableChecksum.Yes`  
- **Обязательна ли контрольная сумма?** No – you can generate a barcode without checksum by disabling it  
- **Какой формат изображения используется в примерах?** PNG (`BarCodeImageFormat.Png`)  
- **Нужна ли лицензия для разработки?** A temporary license is available for evaluation  

## Что такое генерация barcode с помощью Aspose.BarCode?
Генерация barcode — это процесс преобразования текста или числовых данных в машинно‑читаемый визуальный шаблон. Aspose.BarCode for .NET поддерживает десятки символогий, включая Code 39, и позволяет управлять всем, от размера и цвета до расчёта контрольной суммы.

## Почему использовать Code 39 и варианты контрольной суммы?
Code 39 широко используется в логистике и производстве, поскольку он кодирует буквенно‑цифровые данные без специальных символов. Добавление контрольной суммы (или её отсутствие) позволяет сбалансировать обнаружение ошибок и простоту — идеально для биркок инвентаря, транспортных этикеток или простых POS‑систем.

## Требования

Прежде чем мы начнём, убедитесь, что у вас есть следующее:

1. **.NET Development Environment** – знание .NET framework и IDE, такой как Visual Studio. Если вы новичок в .NET, начните с официальной документации: [Microsoft .NET Documentation](https://docs.microsoft.com/en-us/dotnet/).  
2. **Aspose.BarCode for .NET** – скачайте и установите библиотеку. Документация и загрузки доступны здесь: [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/) и [Download Aspose.BarCode for .NET](https://releases.aspose.com/barcode/net/).

Теперь, когда мы рассмотрели требования, перейдём к основным шагам создания одно‑мерных штрих‑кодов Code 39.

## Как генерировать Barcode: импорт пространств имён

Чтобы начать работу с Aspose.BarCode for .NET, импортируйте необходимые пространства имён в ваш проект. Добавление этих операторов `using` даёт доступ к классам генерации barcode.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Как генерировать Code 39 Barcode (с контрольной суммой и без неё)

Ниже мы создадим два штрих‑кода: один **без контрольной суммы** и один **с контрольной суммой**. Код идентичен, за исключением флага `IsChecksumEnabled`.

```csharp
// The path to the documents directory.
string path = "Your Directory Path";
System.Console.WriteLine("OneCSCode39:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code39Extended, "CODE");

// Example 1: Create a Code 39 barcode without checksum
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.No;
gen.Save($"{path}OneCSCode39WithoutChecksum.png", BarCodeImageFormat.Png);

// Example 2: Create a Code 39 barcode with checksum
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Save($"{path}OneCSCode39WithChecksum.png", BarCodeImageFormat.Png);
```

**Что делает код**

1. **Создать экземпляр** `BarcodeGenerator` с `EncodeTypes.Code39Extended` и строкой данных `"CODE"`.  
2. **Переключить** `IsChecksumEnabled`, чтобы контролировать, будет ли добавлена цифра контрольной суммы.  
3. **Сохранить** каждый штрих‑код как PNG‑файл в указанную папку.

Теперь у вас есть два готовых к использованию изображения штрих‑кода: `OneCSCode39WithoutChecksum.png` и `OneCSCode39WithChecksum.png`.

## Распространённые проблемы и решения

| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| **Путь к файлу не найден** | Переменная `path` указывает на несуществующую папку. | Убедитесь, что каталог существует, или используйте `Directory.CreateDirectory(path)`. |
| **Недопустимые символы в данных** | Code 39 поддерживает только буквенно‑цифровые символы и несколько специальных знаков. | Используйте расширенный Code 39 (`Code39Extended`), который поддерживает полный набор ASCII, как показано выше. |
| **Ошибка контрольной суммы** | Забыли установить `IsChecksumEnabled`, когда это требуется. | Явно установите флаг в `EnableChecksum.Yes` или `No` в зависимости от вашего сценария. |

## Часто задаваемые вопросы (FAQ):

### Q: Могу ли я использовать Aspose.BarCode for .NET с другими языками программирования?
A: Aspose.BarCode в основном разработан для .NET, но Aspose также предлагает библиотеки штрих‑кодов для других платформ.

### Q: Есть ли варианты лицензирования для Aspose.BarCode for .NET?
A: Да, вы можете изучить варианты лицензирования и запросить временную лицензию на сайте Aspose: [Aspose.BarCode Licensing](https://purchase.aspose.com/temporary-license/).

### Q: Подходит ли Aspose.BarCode for .NET для веб‑приложений?
A: Да, Aspose.BarCode for .NET можно использовать в веб‑приложениях, что делает его подходящим для широкого спектра проектов.

### Q: Могу ли я настроить внешний вид генерируемых штрих‑кодов?
A: Конечно, вы можете настраивать различные аспекты штрих‑кода, включая размер, цвета и шрифты.

### Q: Где я могу получить поддержку или задать вопросы о Aspose.BarCode for .NET?
A: Вы можете найти ответы на свои вопросы и получить поддержку на форуме Aspose.BarCode: [Aspose.BarCode Forum](https://forum.aspose.com/c/barcode/13).

## Дополнительные часто задаваемые вопросы

**Q: В чём разница между штрих‑кодом с контрольной суммой и без неё?**  
A: Контрольная сумма добавляет дополнительную цифру, помогающую обнаруживать ошибки ввода. Используйте её, когда критична целостность данных.

**Q: Какой может быть размер сгенерированного PNG?**  
A: Размер контролируется через `gen.Parameters.ImageWidth/Height`. Настройте эти свойства перед вызовом `Save`.

**Q: Могу ли я генерировать штрих‑коды в других форматах изображений?**  
A: Да, Aspose.BarCode поддерживает JPEG, BMP, GIF, TIFF и другие форматы — просто измените перечисление `BarCodeImageFormat`.

**Q: Есть ли способ генерировать штрих‑коды в веб‑приложении без записи на диск?**  
A: Вы можете сохранять в `MemoryStream` и возвращать массив байтов напрямую клиенту.

## Заключение
Следуя этим простым шагам, вы сможете **генерировать barcode** изображения в .NET с полным контролем над обработкой контрольной суммы, форматом изображения и визуальным оформлением. Независимо от того, управляете ли вы инвентарём, обрабатываете заказы или создаёте веб‑портал с поддержкой штрих‑кодов, Aspose.BarCode for .NET предоставляет надёжное и удобное для разработчиков решение.

---

**Последнее обновление:** 2026-02-25  
**Тестировано с:** Aspose.BarCode 24.11 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}