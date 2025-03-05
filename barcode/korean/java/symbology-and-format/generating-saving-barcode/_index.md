---
title: Java에서 바코드 생성 및 저장
linktitle: 바코드 생성 및 저장
second_title: Aspose.BarCode 자바 API
description: Aspose.BarCode를 사용하여 Java에서 손쉽게 바코드를 생성하고 저장하세요. 원활하게 통합하고, 모양을 사용자 정의하고, 광범위한 바코드 지원을 누려보세요.
type: docs
weight: 12
url: /ko/java/symbology-and-format/generating-saving-barcode/
---

## 소개

바코드 생성을 Java 애플리케이션에 원활하게 통합하고 싶으십니까? 더 이상 보지 마세요! 이 단계별 가이드에서는 Aspose.BarCode for Java를 사용하여 바코드를 효율적으로 생성하고 저장하는 과정을 안내합니다. Aspose.BarCode는 바코드 생성 및 조작을 단순화하는 강력한 Java 라이브러리로, 바코드 기능으로 애플리케이션을 향상시키는 데 필요한 도구를 제공합니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- Java 개발 환경: 컴퓨터에 Java 개발 환경이 설정되어 있는지 확인하십시오.

- Aspose.BarCode 라이브러리: Aspose.BarCode 라이브러리를 다운로드하여 설치합니다. 다운로드 링크를 찾을 수 있습니다[여기](https://releases.aspose.com/barcode/java/).

- MySQL 데이터베이스: 바코드 관련 정보를 저장할 MySQL 데이터베이스를 설정합니다.

- 데이터베이스 연결: MySQL 데이터베이스와 상호 작용하는 데 필요한 자격 증명과 연결이 있는지 확인하세요.

## 패키지 가져오기

Java 프로젝트에서 Aspose.BarCode 및 MySQL 연결에 필요한 패키지를 가져옵니다.

```java
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generation.BarcodeGenerator;

import java.io.File;
import java.io.FileInputStream;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
```

## 1단계: 바코드 생성 및 저장

```java
// 1단계 - 바코드를 생성하고 파일에 임시 저장
String strBarCodeImage = "c:\\temp\\code39.jpg";
String strCodeText = "NOK-E71";

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText(strCodeText);
generator.save(strBarCodeImage);
```

설명: 이 단계에는 Aspose.BarCode를 사용하여 바코드를 생성하고, 코드 텍스트를 설정하고, 바코드 이미지를 지정된 위치에 저장하는 작업이 포함됩니다.

## 2단계: MySQL 데이터베이스에 레코드 삽입

```java
// 2단계 - MySQL DB에 새 레코드 삽입
Connection con = null;

// 연결 열기
Class.forName("com.mysql.jdbc.Driver").newInstance();
con = DriverManager.getConnection(Common.HOST_URI, Common.USERNAME, Common.PASSWORD);

// 명세서 준비
PreparedStatement pre = con.prepareCall(
        "Insert INTO Product (ProductNumber, ProductName, BarCodeImage) " + "VALUES (?, ?, ?) ");

// 제품번호 및 제품명 설정
pre.setString(1, "NOK-E71");
pre.setString(2, "Nokia E Series - E71");

// 세 번째 열은 바코드 이미지입니다. DB 유형은 BLOB입니다.
// 이미지를 저장하려면 이미지 파일에서 스트림을 생성해야 합니다.
File imgFile = new File(strBarCodeImage);
FileInputStream fin = new FileInputStream(imgFile);
pre.setBinaryStream(3, fin, (int) imgFile.length());

// 문을 실행
pre.executeUpdate();
System.out.println("Insertion successful.");

// 연결 닫기
pre.close();
con.close();
```

설명: 이 단계에는 MySQL 데이터베이스에 연결하고 제품 정보 및 관련 바코드 이미지가 포함된 새 레코드를 삽입하는 작업이 포함됩니다.

## 결론

축하해요! 바코드를 생성하고 저장하기 위해 Java용 Aspose.BarCode를 애플리케이션에 성공적으로 통합했습니다. 이 강력한 라이브러리는 프로세스를 단순화하여 바코드 구현을 쉽게 만듭니다.

## 자주 묻는 질문

### Q: Aspose.BarCode는 다른 바코드 유형과 호환됩니까?
A: 예, Aspose.BarCode는 CODE_39_STANDARD, CODE_128, QR 등을 포함한 다양한 바코드 유형을 지원합니다.

### Q: 생성된 바코드의 모양을 사용자 정의할 수 있습니까?
답: 물론이죠! Aspose.BarCode는 바코드 모양에 대한 광범위한 사용자 정의 옵션을 제공하므로 특정 요구 사항에 맞게 조정할 수 있습니다.

### Q: Aspose.BarCode에 대한 무료 평가판이 있습니까?
 A: 예, 무료 평가판에 액세스할 수 있습니다.[여기](https://releases.aspose.com/).

### Q: Aspose.BarCode에 대한 자세한 문서는 어디서 찾을 수 있나요?
 답: 문서를 참고하세요[여기](https://reference.aspose.com/barcode/java/).

### Q: Aspose.BarCode에 대한 지원을 받으려면 어떻게 해야 합니까?
 A: 지원 포럼을 방문하세요.[여기](https://forum.aspose.com/c/barcode/13) 도움이나 문의사항이 있으면