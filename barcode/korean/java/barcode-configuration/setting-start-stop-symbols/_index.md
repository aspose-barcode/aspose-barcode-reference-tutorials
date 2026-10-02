---
date: 2026-08-28
description: Aspose Barcode Java를 사용하여 Java에서 바코드 이미지를 생성하고, CODABAR 시작 및 종료 기호를 설정하며,
  워터마크 없이 PNG 파일을 생성하는 방법을 배웁니다.
keywords:
- create barcode image java
- barcode generation without watermark
- codabar start stop symbols
lastmod: 2026-08-28
linktitle: 시작 및 종료 기호 설정
og_description: Aspose Barcode Java를 사용하여 Java에서 바코드 이미지를 생성합니다. 이 가이드는 CODABAR 시작/종료
  기호를 설정하고 워터마크 없이 PNG를 내보내는 방법을 보여줍니다.
og_image_alt: 'Aspose Barcode Java tutorial: create barcode image with start/stop
  symbols'
og_title: 바코드 이미지 Java 생성 – 시작/종료 기호 가이드
schemas:
- author: Aspose
  dateModified: '2026-08-28'
  description: Learn how to create barcode image java with Aspose Barcode Java, set
    CODABAR start and stop symbols, and generate PNG files without watermarks.
  headline: Aspose Barcode Java – Create barcode image with start/stop symbols
  type: TechArticle
- questions:
  - answer: Aspose.BarCode for Java.
    question: What library creates barcode images in Java?
  - answer: Yes, using `setCodabarStartSymbol` and `setCodabarStopSymbol`.
    question: Can I customize start/stop symbols?
  - answer: CODABAR.
    question: Which barcode type is used in this example?
  - answer: A commercial license is required for non‑trial use.
    question: Do I need a license for production?
  - answer: PNG image saved to disk.
    question: What output format is generated?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- barcode generation
- Aspose.BarCode
- Java barcode tutorial
title: Aspose Barcode Java – 시작/종료 기호가 있는 바코드 이미지 생성
url: /ko/java/barcode-configuration/setting-start-stop-symbols/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Barcode Java – 시작/정지 기호가 있는 바코드 이미지 생성

## 소개

이 포괄적인 튜토리얼에서는 Aspose Barcode Java를 사용하여 **create barcode image java** 파일을 만들고 CODABAR 바코드의 **how to set start and stop symbols** 를 배우게 됩니다. 포스(Point‑of‑Sale) 단말기, 창고 관리 시스템 또는 신뢰할 수 있는 바코드 생성이 필요한 모든 애플리케이션을 구축하든, 이러한 기호를 사용자 정의하면 레거시 사양을 충족하면서 코드를 깔끔하고 유지 보수하기 쉽게 만들 수 있습니다. 각 단계를 차근차근 살펴보고, 각 설정이 왜 중요한지 설명하며, 워터마크가 없는 PNG 이미지를 생성하는 방법을 보여드립니다.

## 빠른 답변
- **What library creates barcode images in Java?** Aspose.BarCode for Java.  
- **Can I customize start/stop symbols?** Yes, using `setCodabarStartSymbol` and `setCodabarStopSymbol`.  
- **Which barcode type is used in this example?** CODABAR.  
- **Do I need a license for production?** A commercial license is required for non‑trial use.  
- **What output format is generated?** PNG image saved to disk.

## Aspose Barcode Java란?

Aspose Barcode Java는 **의존성 없이 70개 이상의 바코드 심볼리지를 생성**하는 Java 라이브러리로, CODABAR와 같은 클래식 1D 코드부터 QR 및 DataMatrix와 같은 최신 2D 코드까지 지원합니다. 저수준 인코딩을 모두 처리하므로 비즈니스 로직에 집중하면서 산업 표준 준수를 보장할 수 있습니다.

## 워터마크 없이 바코드 생성을 위해 Aspose Barcode Java를 사용하는 이유

먼저 라이선스를 로드하면 라이브러리는 깨끗한 이미지를 생성합니다—“Aspose Evaluation” 오버레이가 없습니다. 또한 **세밀한 제어**(시작/정지 기호, 색상, 크기)와 **크로스‑플랫폼 호환성**(Android 포함 모든 Java 런타임)도 제공합니다. **50개 이상의 출력 포맷**을 지원하고 이미지를 HTTP 응답으로 직접 스트리밍할 수 있어 고처리량, 프로덕션 급 바코드 생성에 최적의 선택입니다.

## 전제 조건

시작하기 전에 다음을 준비하세요:

1. **Java Development Kit (JDK)** – 최신 JDK를 [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html)에서 설치합니다.  
2. **Aspose.BarCode for Java library** – [download link](https://releases.aspose.com/barcode/java/)에서 다운로드합니다.

이러한 준비가 완료되면 **create barcode image java** 를 누락된 구성 요소 없이 만들 수 있습니다.

## 패키지 가져오기

바코드 생성을 위해 필요한 핵심 클래스를 사용할 수 있도록 다음 import를 추가합니다:

`CodabarSymbol` 열거형은 CODABAR 바코드에 허용되는 시작/정지 문자들을 정의합니다.  

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.CodabarSymbol;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## 단계별 가이드

### 바코드 이미지의 출력 폴더를 어떻게 정의합니까?

PNG 파일이 기록될 폴더를 지정합니다. `Paths.get`을 사용하면 Windows, macOS, Linux 모두에서 코드가 이식성을 유지합니다.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### CODABAR용 바코드 생성기를 어떻게 만들나요?

`BarcodeGenerator` 클래스는 지정된 심볼리티와 데이터를 사용해 바코드 이미지를 생성합니다.  

CODABAR 심볼리티와 인코딩하려는 데이터 문자열을 사용해 `BarcodeGenerator`를 인스턴스화합니다.

```java
// Create instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "12345678");
```

### CODABAR 시작 기호를 어떻게 설정합니까?

`setCodabarStartSymbol`은 CODABAR 바코드의 시작을 표시하는 문자를 설정합니다.  

지원되는 문자(`A`, `B`, `C`, `D`) 중 하나를 전달하여 `setCodabarStartSymbol`을 호출합니다. 이 예에서는 `A`를 사용합니다.

```java
// Set the Codabar start symbol to A
generator.getParameters().getBarcode().getCodabar().setCodabarStartSymbol(CodabarSymbol.A);
```

### CODABAR 종료 기호를 어떻게 설정합니까?

`setCodabarStopSymbol`은 CODABAR 바코드의 끝을 표시하는 문자를 설정합니다.  

여기서는 일치하는 종료 문자 `D`를 사용하여 `setCodabarStopSymbol`을 호출합니다.

```java
// Set the Codabar stop symbol to D
generator.getParameters().getBarcode().getCodabar().setCodabarStopSymbol(CodabarSymbol.D);
```

### 생성된 바코드를 PNG 파일로 저장하려면 어떻게 합니까?

`SaveFormat` 열거형은 바코드 이미지를 저장할 파일 포맷을 지정합니다.  

전체 파일 이름과 `SaveFormat.Png` 열거값을 제공하여 `save` 메서드를 호출합니다. 유효한 라이선스가 적용된 경우 이미지에 워터마크가 포함되지 않습니다.

```java
// Save the image to disk in PNG format
generator.save(dataDir + "startAndStopSymbols.png");
```

## 일반적인 함정 및 팁

`License` 클래스는 전체 기능 모드를 활성화하기 위해 Aspose 라이선스 파일을 로드합니다.

- **Incorrect directory path** – `dataDir`이 적절한 파일 구분자로 끝나는지 확인하거나 `Paths.get`으로 경로를 구성하세요.  
- **Unsupported start/stop characters** – CODABAR는 `A`, `B`, `C`, `D`만 허용합니다. 다른 값을 제공하면 `IllegalArgumentException`이 발생합니다.  
- **License not applied** – 평가판 모드에서는 출력에 워터마크가 포함됩니다. 생성기를 만들기 전에 `License license = new License(); license.setLicense("Aspose.Total.Java.lic");` 로 라이선스 파일을 로드하여 이를 방지하세요.  
- **Large‑scale generation** – 수천 개의 바코드를 생성할 때는 단일 `BarcodeGenerator` 인스턴스를 재사용하고 코드 텍스트만 변경하여 객체 생성 오버헤드를 줄이세요.

## 자주 묻는 질문

### 상업 프로젝트에서 Aspose.BarCode for Java를 사용할 수 있나요?

예. 평가 워터마크를 제거하고 전체 기술 지원을 받으려면 [purchase a commercial license](https://purchase.aspose.com/buy) 를 구매하세요.

### 무료 체험판이 있나요?

물론입니다. 모든 기능을 평가하려면 [download the trial version](https://releases.aspose.com/) 를 다운로드하세요.

### Aspose.BarCode for Java에 대한 지원을 어떻게 받을 수 있나요?

커뮤니티 도움을 위해 Aspose.BarCode 포럼 [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) 을 방문하거나 Aspose 계정 포털을 통해 지원 티켓을 열 수 있습니다.

### 테스트용 임시 라이선스를 어떻게 얻나요?

30일 임시 라이선스를 요청하려면 [request a temporary 30‑day license](https://purchase.aspose.com/temporary-license/) 를 이용하세요. 이를 통해 전체 구매 없이도 프로덕션과 유사한 테스트를 수행할 수 있습니다.

### Aspose.BarCode가 지원하는 다른 바코드 심볼은 무엇인가요?

이 라이브러리는 Code128, EAN‑13, QR, DataMatrix, PDF417 등을 포함해 **70개 이상의 심볼리지를** 지원합니다. 전체 목록은 공식 문서를 참고하세요.

## 추가 Q&A (AI 친화적)

**Q:** PNG 외에 어떤 이미지 포맷으로 내보낼 수 있나요?  
**A:** Aspose.BarCode는 PNG, JPEG, BMP, GIF, TIFF를 지원합니다. `save` 호출 시 `SaveFormat` 열거값을 변경하여 원하는 포맷을 선택하세요.

**Q:** 디스크에 쓰지 않고 메모리에서 바코드 이미지를 생성할 수 있나요?  
**A:** 예. `generator.save(OutputStream)`을 호출하면 스트림으로 직접 기록할 수 있어, 이미지를 HTTP 응답으로 반환하는 웹 API에 이상적입니다.

**Q:** 라이브러리가 Android에서 작동하나요?  
**A:** Java 버전은 Android에서도 실행되지만, 필요한 종속성을 수동으로 포함해야 합니다(Maven Central에는 Android용이 없음). 핵심 API는 동일합니다.

## 결론

이제 Aspose Barcode Java를 사용해 **create barcode image java** 를 만들고 CODABAR 바코드의 시작/정지 기호를 정확히 **set start/stop symbols** 하는 방법을 배웠습니다. 이 접근 방식은 레거시 사양을 충족하면서 코드베이스를 깔끔하고 유지 보수 가능하게 합니다. 색상 변경, 인간이 읽을 수 있는 텍스트 추가, 다른 심볼리티로 전환 등 추가 커스터마이징은 공식 API 레퍼런스 [documentation](https://reference.aspose.com/barcode/java/) 를 참고하세요.

---

**Last Updated:** 2026-08-28  
**Tested With:** Aspose.BarCode for Java 24.12  
**Author:** Aspose

## 관련 튜토리얼

- [Validate Checksum and Create Codabar Barcode in Java with Aspose.BarCode](/barcode/java/checksum-and-validation/)
- [Create Barcode with Aspose - Set X & Y Dimensions in Java](/barcode/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [How to generate barcode java: Create an Exact Barcode Image](/barcode/java/barcode-basics/creating-image-exact-barcode/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}