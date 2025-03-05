---
title: Aspose.BarCode를 사용하여 Java의 단일 이미지에 여러 바코드 생성
linktitle: 단일 이미지에 여러 바코드 생성
second_title: Aspose.BarCode 자바 API
description: Java용 Aspose.BarCode를 사용하여 단일 이미지에 여러 바코드를 손쉽게 생성하세요. 원활한 통합을 위한 단계별 가이드를 따르세요.
type: docs
weight: 19
url: /ko/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
---
## 소개

Java 프로그래밍의 역동적인 세계에서 바코드를 효율적으로 생성하고 관리하는 것은 다양한 애플리케이션에 매우 중요합니다. Java용 Aspose.BarCode는 이 프로세스를 단순화하여 개발자가 단일 이미지에 여러 바코드를 원활하게 생성할 수 있도록 합니다. 이 튜토리얼은 Java 환경에서 Aspose.BarCode를 사용하여 이를 달성하는 단계를 안내합니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.

- Java 프로그래밍에 대한 기본 이해.
- 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
- Java 라이브러리용 Aspose.BarCode를 다운로드하고 설정했습니다. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/barcode/java/).
- Eclipse 또는 IntelliJ IDEA와 같은 통합 개발 환경(IDE).

## 네임스페이스 가져오기

Java 프로젝트에서 Aspose.BarCode 기능에 액세스하는 데 필요한 네임스페이스를 가져옵니다. Java 클래스 시작 부분에 다음 가져오기 문을 추가합니다.

```java
import java.awt.Color;
import java.awt.Graphics;
import java.awt.image.BufferedImage;
import java.io.File;
import java.util.ArrayList;
import java.util.HashMap;

import javax.imageio.ImageIO;

import com.aspose.barcode.BaseEncodeType;
import com.aspose.barcode.EncodeTypes;


import com.aspose.barcode.generation.BarcodeGenerator;
```

## 1단계: 리소스 디렉터리 설정

생성된 바코드가 저장될 리소스 디렉터리의 경로를 정의합니다. 이 디렉토리는 바코드 이미지를 구성하고 관리하는 데 중요합니다.

```java
// 리소스 디렉터리의 경로입니다.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## 2단계: 바코드 컬렉션 생성

바코드 데이터를 저장하기 위해 HashMap을 초기화합니다. 컬렉션의 각 항목은 해당 인코딩 유형이 포함된 바코드를 나타냅니다.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## 3단계: 바코드 이미지 생성

Aspose.BarCode 라이브러리를 사용하여 컬렉션을 반복하고 바코드 이미지를 생성합니다. 추가 처리를 위해 이미지를 ArrayList에 저장합니다.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## 4단계: 결합된 이미지 생성

바코드 이미지의 최대 너비와 전체 높이를 결정합니다. 개별 바코드 이미지를 단일 출력 이미지로 결합하려면 BufferedImage를 만듭니다.

```java
int maxWidth = 0;
int sumHeight = 0;
for (BufferedImage bmp : images) {
    sumHeight += bmp.getHeight();
    if (maxWidth < bmp.getWidth())
        maxWidth = bmp.getWidth();
}

int offset = 10;
BufferedImage resultBitmap = new BufferedImage(maxWidth + offset * 2, sumHeight + offset * images.size(),
        BufferedImage.TYPE_INT_ARGB);
Graphics g = resultBitmap.getGraphics();
g.setColor(Color.white);
g.fillRect(0, 0, resultBitmap.getWidth(), resultBitmap.getHeight());

int yPosition = offset;
for (int i = 0; i < images.size(); ++i) {
    BufferedImage currentBitmap = images.get(i);
    g.drawImage(currentBitmap, offset, yPosition, null);
    yPosition += currentBitmap.getHeight() + offset;
}
```
## 5단계: 결과 저장

최종 결합된 이미지를 지정된 파일 위치에 저장합니다.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## 결론

축하해요! Java용 Aspose.BarCode를 사용하여 단일 이미지에 여러 바코드를 성공적으로 생성했습니다. 이 강력한 라이브러리는 바코드 처리를 단순화하여 Java 개발자에게 귀중한 도구입니다.

## FAQ

### Q1: 생성된 이미지에서 개별 바코드의 모양을 사용자 정의할 수 있습니까?

A1: 예, Aspose.BarCode는 바코드 모양에 대한 광범위한 사용자 정의 옵션을 제공하므로 각 바코드의 스타일을 원하는 대로 조정할 수 있습니다.

### Q2: Aspose.BarCode는 다른 바코드 기호와 호환됩니까?

A2: 물론이죠! Aspose.BarCode는 이 튜토리얼에서 설명한 대로 CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 및 AZTEC를 포함한 광범위한 기호를 지원합니다.

### Q3: Aspose.BarCode를 Java 프로젝트에 어떻게 통합할 수 있나요?

 A3: 다음에서 Java 라이브러리용 Aspose.BarCode를 다운로드하기만 하면 됩니다.[여기](https://releases.aspose.com/barcode/java/) 설명서에 제공된 설치 지침을 따르세요.

### Q4: Aspose.BarCode를 상업용 애플리케이션에 사용할 수 있습니까?

 A4: 예, 다음에서 라이센스를 얻을 수 있습니다.[여기](https://purchase.aspose.com/buy) Aspose.BarCode를 상업적 목적으로 사용합니다.

### Q5: Aspose.BarCode에 사용할 수 있는 평가판 옵션이 있습니까?

 A5: 물론이죠! 무료 평가판 라이선스를 획득하여 Aspose.BarCode의 기능을 탐색할 수 있습니다.[여기](https://releases.aspose.com/).