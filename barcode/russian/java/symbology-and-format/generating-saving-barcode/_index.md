---
title: Создание и сохранение штрих-кода в Java
linktitle: Создание и сохранение штрих-кода
second_title: API Aspose.BarCode Java
description: Легко создавайте и сохраняйте штрих-коды на Java с помощью Aspose.BarCode. Беспрепятственная интеграция, настройка внешнего вида и обширная поддержка штрих-кодов.
weight: 12
url: /ru/java/symbology-and-format/generating-saving-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание и сохранение штрих-кода в Java


## Введение

Вы хотите легко интегрировать генерацию штрих-кода в свое Java-приложение? Не смотрите дальше! В этом пошаговом руководстве мы покажем вам процесс использования Aspose.BarCode для Java для эффективного создания и сохранения штрих-кодов. Aspose.BarCode — это мощная библиотека Java, которая упрощает создание и манипулирование штрих-кодами, предоставляя вам инструменты, необходимые для улучшения ваших приложений с помощью функций штрих-кода.

## Предварительные условия

Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:

- Среда разработки Java. Убедитесь, что на вашем компьютере установлена среда разработки Java.

- Библиотека Aspose.BarCode: Загрузите и установите библиотеку Aspose.BarCode. Вы можете найти ссылку для скачивания[здесь](https://releases.aspose.com/barcode/java/).

- База данных MySQL: настройте базу данных MySQL, в которой вы собираетесь хранить информацию, связанную со штрих-кодом.

- Подключение к базе данных: убедитесь, что у вас есть необходимые учетные данные и возможности подключения для взаимодействия с базой данных MySQL.

## Импортировать пакеты

В свой проект Java импортируйте необходимые пакеты для подключения Aspose.BarCode и MySQL.

```java
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generation.BarcodeGenerator;

import java.io.File;
import java.io.FileInputStream;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
```

## Шаг 1. Создайте и сохраните штрих-код

```java
// Шаг 1. Создайте штрих-код и временно сохраните его в файле.
String strBarCodeImage = "c:\\temp\\code39.jpg";
String strCodeText = "NOK-E71";

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText(strCodeText);
generator.save(strBarCodeImage);
```

Объяснение: Этот шаг включает в себя создание штрих-кода с помощью Aspose.BarCode, настройку текста кода и сохранение изображения штрих-кода в указанном месте.

## Шаг 2. Вставьте запись в базу данных MySQL

```java
// Шаг 2. Вставьте новую запись в базу данных MySQL.
Connection con = null;

// Открытое соединение
Class.forName("com.mysql.jdbc.Driver").newInstance();
con = DriverManager.getConnection(Common.HOST_URI, Common.USERNAME, Common.PASSWORD);

// Подготовить заявление
PreparedStatement pre = con.prepareCall(
        "Insert INTO Product (ProductNumber, ProductName, BarCodeImage) " + "VALUES (?, ?, ?) ");

// Установите номер продукта и название продукта
pre.setString(1, "NOK-E71");
pre.setString(2, "Nokia E Series - E71");

// Третий столбец предназначен для изображения штрих-кода. Тип БД — BLOB
// Для сохранения изображения нам нужно создать поток из файла изображения.
File imgFile = new File(strBarCodeImage);
FileInputStream fin = new FileInputStream(imgFile);
pre.setBinaryStream(3, fin, (int) imgFile.length());

// Выполните заявление
pre.executeUpdate();
System.out.println("Insertion successful.");

// Закрыть соединение
pre.close();
con.close();
```

Объяснение: Этот шаг включает подключение к базе данных MySQL и вставку новой записи с информацией о продукте и соответствующим изображением штрих-кода.

## Заключение

Поздравляем! Вы успешно интегрировали Aspose.BarCode для Java в свое приложение для создания и сохранения штрих-кодов. Эта мощная библиотека упрощает процесс, упрощая внедрение штрих-кода.

## Часто задаваемые вопросы

### Вопрос: Совместим ли Aspose.BarCode с различными типами штрих-кодов?
О: Да, Aspose.BarCode поддерживает различные типы штрих-кодов, включая CODE_39_STANDARD, CODE_128, QR и другие.

### Вопрос: Могу ли я настроить внешний вид сгенерированных штрих-кодов?
А: Абсолютно! Aspose.BarCode предоставляет широкие возможности настройки внешнего вида штрих-кода, что позволяет адаптировать его к вашим конкретным потребностям.

### Вопрос: Существует ли бесплатная пробная версия Aspose.BarCode?
 О: Да, вы можете получить доступ к бесплатной пробной версии.[здесь](https://releases.aspose.com/).

### Вопрос: Где я могу найти подробную документацию по Aspose.BarCode?
 О: обратитесь к документации.[здесь](https://reference.aspose.com/barcode/java/).

### Вопрос: Как мне получить поддержку Aspose.BarCode?
 О: Посетите форум поддержки.[здесь](https://forum.aspose.com/c/barcode/13) для любой помощи или вопросов.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
