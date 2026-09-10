---
date: 2026-05-04
description: Узнайте, как на Java генерировать изображение штрих‑кода и сохранять
  его с помощью Aspose.BarCode for Java. Пошаговое руководство с хранением в MySQL,
  советами по настройке и полным кодом.
keywords:
- java generate barcode image
- how to generate barcode java
- how to save barcode image
linktitle: Создание и сохранение штрих‑кода
second_title: Aspose.BarCode Java API
title: 'Java: генерация изображения штрихкода и сохранение в базу данных'
url: /ru/java/symbology-and-format/generating-saving-barcode/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# java генерировать изображение штрихкода

## Введение

Если вам нужно **java generate barcode image** быстро и сохранить его вместе с данными о продукте, этот учебник для вас. Мы пройдемся по использованию Aspose.BarCode for Java для создания штрихкода CODE‑39, сохраним изображение на диск и затем вставим его в базу данных MySQL как BLOB. В конце у вас будет переиспользуемый шаблон, который можно адаптировать к любому типу штрихкода или требованию к хранению.

## Быстрые ответы
- **Какая библиотека создает штрихкоды в Java?** Aspose.BarCode for Java.  
- **Могу ли я сохранить штрихкод в файл?** Да — используйте `generator.save("path")`.  
- **Как сохранить изображение в MySQL?** Прочитайте файл в `FileInputStream` и установите его как бинарный поток в `PreparedStatement`.  
- **Какие типы штрихкодов поддерживаются?** CODE_39, CODE_128, QR, DataMatrix и многие другие.  
- **Нужна ли лицензия для продакшн?** Требуется коммерческая лицензия; доступна бесплатная пробная версия.

## Что такое java generate barcode image?
Создание изображения штрихкода в Java означает преобразование обычного текста (например, номера продукта) в визуальное представление, которое могут считывать сканеры. Aspose.BarCode абстрагирует детали низкоуровневого кодирования, позволяя сосредоточиться на логике вашего приложения.

## Почему использовать Aspose.BarCode для этой задачи?
- **Полнофункциональный**: Поддерживает более 50 символогий.  
- **Простой API**: Однострочный код для создания и сохранения изображения.  
- **Высокое качество**: Генерирует PNG, JPEG, BMP и PDF.  
- **Готовый для предприятий**: Работает на всех основных версиях Java и легко интегрируется с базами данных.

## Требования

- **Среда разработки Java** – установлен JDK 8+ и IDE по вашему выбору.  
- **Библиотека Aspose.BarCode** – Скачайте и установите библиотеку Aspose.BarCode. Ссылка для загрузки доступна [здесь](https://releases.aspose.com/barcode/java/).  
- **База данных MySQL** – Рабочий экземпляр MySQL, где вы будете хранить информацию о продуктах.  
- **Подключение к базе данных** – JDBC‑драйвер и действительные учетные данные (`HOST_URI`, `USERNAME`, `PASSWORD`).

## Импорт пакетов

В вашем Java‑проекте импортируйте необходимые пакеты для Aspose.BarCode и подключения к MySQL.

```java
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generation.BarcodeGenerator;

import java.io.File;
import java.io.FileInputStream;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
```

## Как сгенерировать штрихкод java

### Шаг 1: Сгенерировать и сохранить штрихкод

```java
// Step 1 - Generate barcode and save temporarily in a file
String strBarCodeImage = "c:\\temp\\code39.jpg";
String strCodeText = "NOK-E71";

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText(strCodeText);
generator.save(strBarCodeImage);
```

*Объяснение*: Мы создаем `BarcodeGenerator` для стандарта CODE‑39, задаем код продукта (`NOK-E71`) и сохраняем изображение в `c:\temp\code39.jpg`. Этот файл позже будет передан в базу данных.

## Как сохранить изображение штрихкода

### Шаг 2: Вставить запись в базу данных MySQL

```java
// Step 2 - Insert a new record in MySQL DB
Connection con = null;

// Open connection
Class.forName("com.mysql.jdbc.Driver").newInstance();
con = DriverManager.getConnection(Common.HOST_URI, Common.USERNAME, Common.PASSWORD);

// Prepare statement
PreparedStatement pre = con.prepareCall(
        "Insert INTO Product (ProductNumber, ProductName, BarCodeImage) " + "VALUES (?, ?, ?) ");

// Set product number and product name
pre.setString(1, "NOK-E71");
pre.setString(2, "Nokia E Series - E71");

// 3rd column is for barcode image. DB type is BLOB
// For saving the image, we need to create a stream from the image file
File imgFile = new File(strBarCodeImage);
FileInputStream fin = new FileInputStream(imgFile);
pre.setBinaryStream(3, fin, (int) imgFile.length());

// Execute the statement
pre.executeUpdate();
System.out.println("Insertion successful.");

// Close connection
pre.close();
con.close();
```

*Объяснение*: После установления JDBC‑соединения мы подготавливаем оператор `INSERT`, который включает столбец BLOB для изображения штрихкода. Файл изображения читается в `FileInputStream` и сохраняется как бинарные данные.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|---------|----------|
| **FileNotFoundException** при сохранении штрихкода | Папка назначения не существует или нет прав на запись | Создайте папку (`c:\temp`) или выберите путь с правом записи |
| **SQLIntegrityConstraintViolationException** при вставке | Дублирующийся первичный ключ `ProductNumber` | Убедитесь, что номер продукта уникален, или используйте `ON DUPLICATE KEY UPDATE` |
| **ClassNotFoundException: com.mysql.jdbc.Driver** | JDBC‑драйвер MySQL отсутствует в classpath | Добавьте JAR MySQL Connector/J в зависимости проекта |

## Часто задаваемые вопросы

**Q: Совместим ли Aspose.BarCode с различными типами штрихкодов?**  
A: Да, Aspose.BarCode поддерживает различные типы штрихкодов, включая CODE_39_STANDARD, CODE_128, QR и другие.

**Q: Могу ли я настроить внешний вид сгенерированных штрихкодов?**  
A: Абсолютно! Aspose.BarCode предоставляет обширные возможности настройки внешнего вида штрихкода, позволяя адаптировать его под ваши конкретные потребности.

**Q: Доступна ли бесплатная пробная версия Aspose.BarCode?**  
A: Да, вы можете получить бесплатную пробную версию [здесь](https://releases.aspose.com/).

**Q: Где можно найти подробную документацию по Aspose.BarCode?**  
A: Обратитесь к документации [здесь](https://reference.aspose.com/barcode/java/).

**Q: Как получить поддержку по Aspose.BarCode?**  
A: Посетите форум поддержки [здесь](https://forum.aspose.com/c/barcode/13) для получения помощи или вопросов.

## Заключение

Поздравляем! Вы успешно изучили **how to generate barcode java** и **how to save barcode image** с помощью Aspose.BarCode, а затем сохранили изображение в базе данных MySQL. Этот подход можно расширить на другие символогии, механизмы хранения (например, Azure Blob, AWS S3) или интегрировать в более крупные корпоративные системы.

---

**Последнее обновление:** 2026-05-04  
**Тестировано с:** Aspose.BarCode for Java 24.10  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}