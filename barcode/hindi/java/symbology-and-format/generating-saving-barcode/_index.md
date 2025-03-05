---
title: जावा में बारकोड बनाना और सहेजना
linktitle: बारकोड बनाना और सहेजना
second_title: Aspose.BarCode जावा एपीआई
description: Aspose.BarCode के साथ जावा में आसानी से बारकोड बनाएं और सहेजें। निर्बाध रूप से एकीकृत करें, उपस्थिति को अनुकूलित करें और व्यापक बारकोड समर्थन का आनंद लें।
type: docs
weight: 12
url: /hi/java/symbology-and-format/generating-saving-barcode/
---

## परिचय

क्या आप बारकोड जेनरेशन को अपने जावा एप्लिकेशन में निर्बाध रूप से एकीकृत करना चाहते हैं? आगे कोई तलाश नहीं करें! इस चरण-दर-चरण मार्गदर्शिका में, हम आपको बारकोड को कुशलतापूर्वक उत्पन्न करने और सहेजने के लिए जावा के लिए Aspose.BarCode का उपयोग करने की प्रक्रिया के बारे में बताएंगे। Aspose.BarCode एक शक्तिशाली जावा लाइब्रेरी है जो बारकोड निर्माण और हेरफेर को सरल बनाती है, जो आपको बारकोड कार्यक्षमता के साथ आपके एप्लिकेशन को बढ़ाने के लिए आवश्यक उपकरण प्रदान करती है।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

- जावा विकास वातावरण: सुनिश्चित करें कि आपकी मशीन पर जावा विकास वातावरण स्थापित है।

- Aspose.BarCode लाइब्रेरी: Aspose.BarCode लाइब्रेरी डाउनलोड और इंस्टॉल करें। आप डाउनलोड लिंक पा सकते हैं[यहाँ](https://releases.aspose.com/barcode/java/).

- MySQL डेटाबेस: एक MySQL डेटाबेस सेट करें जहाँ आप बारकोड से संबंधित जानकारी संग्रहीत करना चाहते हैं।

- डेटाबेस कनेक्टिविटी: सुनिश्चित करें कि आपके पास MySQL डेटाबेस के साथ इंटरैक्ट करने के लिए आवश्यक क्रेडेंशियल और कनेक्टिविटी है।

## पैकेज आयात करें

अपने जावा प्रोजेक्ट में, Aspose.BarCode और MySQL कनेक्टिविटी के लिए आवश्यक पैकेज आयात करें।

```java
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generation.BarcodeGenerator;

import java.io.File;
import java.io.FileInputStream;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
```

## चरण 1: बारकोड जनरेट करें और सहेजें

```java
// चरण 1 - बारकोड जेनरेट करें और एक फ़ाइल में अस्थायी रूप से सहेजें
String strBarCodeImage = "c:\\temp\\code39.jpg";
String strCodeText = "NOK-E71";

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText(strCodeText);
generator.save(strBarCodeImage);
```

स्पष्टीकरण: इस चरण में Aspose.BarCode के साथ एक बारकोड बनाना, कोड टेक्स्ट सेट करना और बारकोड छवि को एक निर्दिष्ट स्थान पर सहेजना शामिल है।

## चरण 2: MySQL डेटाबेस में रिकॉर्ड डालें

```java
// चरण 2 - MySQL DB में एक नया रिकॉर्ड डालें
Connection con = null;

// कनेक्शन खोलें
Class.forName("com.mysql.jdbc.Driver").newInstance();
con = DriverManager.getConnection(Common.HOST_URI, Common.USERNAME, Common.PASSWORD);

// वक्तव्य तैयार करें
PreparedStatement pre = con.prepareCall(
        "Insert INTO Product (ProductNumber, ProductName, BarCodeImage) " + "VALUES (?, ?, ?) ");

// उत्पाद संख्या और उत्पाद का नाम सेट करें
pre.setString(1, "NOK-E71");
pre.setString(2, "Nokia E Series - E71");

// तीसरा कॉलम बारकोड छवि के लिए है। DB प्रकार BLOB है
// छवि को सहेजने के लिए, हमें छवि फ़ाइल से एक स्ट्रीम बनाने की आवश्यकता है
File imgFile = new File(strBarCodeImage);
FileInputStream fin = new FileInputStream(imgFile);
pre.setBinaryStream(3, fin, (int) imgFile.length());

// कथन निष्पादित करें
pre.executeUpdate();
System.out.println("Insertion successful.");

// निकट संबंध
pre.close();
con.close();
```

स्पष्टीकरण: इस चरण में MySQL डेटाबेस से कनेक्ट करना और उत्पाद जानकारी और संबंधित बारकोड छवि के साथ एक नया रिकॉर्ड सम्मिलित करना शामिल है।

## निष्कर्ष

बधाई हो! आपने बारकोड बनाने और सहेजने के लिए जावा के लिए Aspose.BarCode को अपने एप्लिकेशन में सफलतापूर्वक एकीकृत कर लिया है। यह शक्तिशाली लाइब्रेरी प्रक्रिया को सरल बनाती है, जिससे बारकोड कार्यान्वयन आसान हो जाता है।

## अक्सर पूछे जाने वाले प्रश्नों

### प्रश्न: क्या Aspose.BarCode विभिन्न बारकोड प्रकारों के साथ संगत है?
उत्तर: हाँ, Aspose.BarCode विभिन्न बारकोड प्रकारों का समर्थन करता है, जिनमें Code_39_STANDARD, CODE_128, QR, और बहुत कुछ शामिल हैं।

### प्रश्न: क्या मैं जेनरेट किए गए बारकोड के स्वरूप को अनुकूलित कर सकता हूं?
उत्तर: बिल्कुल! Aspose.BarCode बारकोड उपस्थिति के लिए व्यापक अनुकूलन विकल्प प्रदान करता है, जिससे आप इसे अपनी विशिष्ट आवश्यकताओं के अनुरूप बना सकते हैं।

### प्रश्न: क्या Aspose.BarCode के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 उत्तर: हाँ, आप निःशुल्क परीक्षण का उपयोग कर सकते हैं[यहाँ](https://releases.aspose.com/).

### प्रश्न: मुझे Aspose.BarCode के लिए विस्तृत दस्तावेज़ कहां मिल सकते हैं?
 उत्तर: दस्तावेज़ देखें[यहाँ](https://reference.aspose.com/barcode/java/).

### प्रश्न: मुझे Aspose.BarCode के लिए समर्थन कैसे मिलेगा?
 उत्तर: सहायता मंच पर जाएँ[यहाँ](https://forum.aspose.com/c/barcode/13) किसी भी सहायता या प्रश्न के लिए।