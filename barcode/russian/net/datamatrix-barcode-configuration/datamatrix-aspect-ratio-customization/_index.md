---
date: 2026-01-12
description: Узнайте, как создать PNG‑изображение штрих‑кода с пользовательским соотношением
  сторон DataMatrix, используя Aspose.BarCode для .NET. Пошаговое руководство по генерации
  штрих‑кода и настройке его размера.
linktitle: DataMatrix Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
title: Создать PNG штрихкода – соотношение сторон DataMatrix – Aspose.BarCode
url: /ru/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание PNG‑штрихкода – соотношение сторон DataMatrix – Aspose.BarCode

Генерация **barcode PNG** с пользовательским соотношением сторон DataMatrix часто требуется, когда необходимо, чтобы штрихкод вписался в определённые ограничения макета. В этом руководстве мы пошагово покажем, как **create barcode PNG** файлы с помощью Aspose.BarCode для .NET, объясним, почему может потребоваться изменить соотношение сторон, и продемонстрируем, как точно настроить вывод для вашего приложения.

## Быстрые ответы
- **Что контролирует «соотношение сторон»?** Оно определяет пропорцию ширины к высоте модулей DataMatrix.  
- **Могу ли я выводить PNG, JPEG или SVG?** Да — метод `Save` поддерживает PNG, JPEG, BMP, GIF и другие форматы.  
- **Нужна ли лицензия для этой функции?** Бесплатная пробная версия подходит для разработки; для продакшна требуется полная лицензия.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **Сколько значений соотношения сторон допустимо?** Любое положительное число с плавающей точкой; типичные значения от 0.5 – 2.0.

## Что такое штрихкод DataMatrix и почему стоит регулировать его соотношение сторон?
DataMatrix — это двумерный матричный штрихкод, который хранит большие объёмы данных в небольшом пространстве. Регулирование **aspect ratio** позволяет растягивать или сжимать модули по горизонтали, что может быть полезно для размещения штрихкода в узких колонках или широких этикетках без потери читаемости.

## Предварительные требования

Перед тем как начать настраивать соотношения сторон DataMatrix, убедитесь, что у вас есть следующее:

1. **Visual Studio** — подойдет любая современная версия.  
2. **Aspose.BarCode for .NET** — скачайте его [здесь](https://releases.aspose.com/barcode/net/).  
3. **.NET Framework / .NET Core** — ваш проект должен быть на поддерживаемой версии.

## Импорт пространств имён

Сначала необходимо импортировать нужное пространство имён в ваш C#‑проект:

```csharp
using Aspose.BarCode.Generation;
```

> **Pro tip:** Оставляйте эту инструкцию `using` в начале файла, чтобы класс `BarcodeGenerator` всегда был доступен.

## Пошаговое руководство

### Шаг 1: Настройте проект
Создайте новый консольный или Windows Forms проект в Visual Studio и добавьте ссылку на библиотеку Aspose.BarCode DLL.

### Шаг 2: Инициализируйте генератор штрихкода
Создайте объект `BarcodeGenerator` с типом DataMatrix и данными, которые нужно закодировать:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> Эта строка создаёт генератор, готовый произвести штрихкод DataMatrix, содержащий пример текста.

### Шаг 3: Настройте соотношение сторон и сохраните PNG‑файлы
Теперь можно изменить **aspect ratio** и сохранить каждую версию как PNG‑изображение:

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- Первый вызов создаёт квадратное соотношение штрихкода (`AspectRatio = 1`).  
- Второй вызов сжимает штрихкод по горизонтали (`AspectRatio = 0.5`), получая более широкую форму.

У вас теперь есть два **barcode PNG** файла с разными соотношениями сторон, готовые к использованию в отчётах, этикетках или UI‑элементах.

## Распространённые проблемы и решения
| Проблема | Решение |
|----------|---------|
| **Сгенерированное изображение размыто** | Увеличьте параметр `Resolution` перед сохранением (`gen.Parameters.ImageResolution = 300`). |
| **Штрихкод не считывается** | Убедитесь, что соотношение сторон находится в диапазоне 0.5 – 2.0 и оставьте достаточную зону тишины (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **Ошибки пути к файлу** | Используйте `Path.Combine` для построения пути вывода и проверьте, что папка существует. |

## Часто задаваемые вопросы

**Q: Могу ли я настроить соотношение сторон других типов штрихкодов с помощью Aspose.BarCode for .NET?**  
A: Да, многие 2‑D штрихкоды (например, QR, PDF417) поддерживают регулировку соотношения сторон через их специфические объекты параметров.

**Q: Есть ли бесплатная пробная версия Aspose.BarCode for .NET?**  
A: Да, вы можете получить бесплатную пробную версию Aspose.BarCode for .NET [здесь](https://releases.aspose.com/).

**Q: Где можно приобрести лицензию на Aspose.BarCode for .NET?**  
A: Лицензию можно купить на сайте Aspose [здесь](https://purchase.aspose.com/buy).

**Q: Совместим ли Aspose.BarCode for .NET с разными версиями .NET Framework?**  
A: Да, он работает с .NET Framework 4.x, .NET Core 3.1+ и последними версиями .NET.

**Q: Могу ли я генерировать штрихкоды в разных форматах с помощью Aspose.BarCode for .NET?**  
A: Абсолютно — PNG, JPEG, BMP, GIF, TIFF, SVG и PDF поддерживаются из коробки.

## Заключение

Настройка **aspect ratio** штрихкода DataMatrix и **создание barcode PNG** файлов проста с Aspose.BarCode для .NET. Следуя приведённым шагам, вы сможете генерировать штрихкоды нужного размера, полностью соответствующие требованиям вашего макета. Исследуйте дополнительные параметры, такие как `Resolution`, `Margin` и `Color`, чтобы ещё точнее настроить вывод.

Для более глубокого изучения обратитесь к официальной [documentation](https://reference.aspose.com/barcode/net/) или присоединитесь к сообществу на форуме [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13).

---

**Last Updated:** 2026-01-12  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}