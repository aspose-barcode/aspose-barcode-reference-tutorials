---
date: 2025-11-30
description: Tìm hiểu cách đánh giá chất lượng đọc mã vạch trong Java với Aspose.Barcode.
  Hướng dẫn từng bước để lấy phần trăm chất lượng nhận dạng.
language: vi
linktitle: Getting Barcode Recognition Quality in Percent
second_title: Aspose.Barcode Java API
title: Aspose.Barcode Java – Đánh giá chất lượng nhận dạng mã vạch bằng phần trăm
url: /java/advanced-settings-and-optimization/getting-barcode-recognition-quality-percent/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Barcode Java – Lấy Chất Lượng Nhận Diện Mã Vạch Theo Phần Trăm

## Introduction

Nếu bạn cần **đánh giá chất lượng đọc mã vạch** trong một ứng dụng Java, **Aspose.Barcode Java** cung cấp một API đơn giản trả về chất lượng nhận dạng dưới dạng phần trăm. Trong hướng dẫn này, chúng tôi sẽ đi qua các bước chính xác để lấy phần trăm đó, giải thích tại sao chỉ số này quan trọng, và chỉ cho bạn cách tích hợp cuộc gọi này vào mã hiện có của bạn.

## Quick Answers
- **“reading quality” có nghĩa là gì?** Đó là điểm tin cậy (0‑100 %) mà thư viện gán cho mỗi mã vạch đã giải mã.  
- **Phiên bản thư viện nào được yêu cầu?** Bất kỳ bản phát hành Aspose.Barcode Java gần đây nào (ví dụ mẫu sử dụng series 24.x mới nhất).  
- **Tôi có cần giấy phép không?** Giấy phép tạm thời hoạt động cho mục đích thử nghiệm; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Tôi có thể đọc tất cả các loại mã vạch không?** Có – cờ `DecodeType.ALL_SUPPORTED_TYPES` bật mọi định dạng được Aspose.Barcode hỗ trợ.  
- **Giá trị chất lượng có đáng tin cậy với mã QR không?** Hoàn toàn – cùng một thuật toán tin cậy được áp dụng cho cả symbology 1‑D và 2‑D.

## What is Aspose.Barcode Java and How to Assess Barcode Reading Quality?

**Aspose.Barcode Java** là một thư viện được quản lý hoàn toàn cho phép các nhà phát triển tạo, đọc và phân tích mã vạch mà không cần phụ thuộc bên ngoài. Một trong những chẩn đoán hữu ích nhất của nó là chỉ số **reading quality**, cho bạn biết mức độ tự tin của engine khi giải mã một ký hiệu. Chỉ số này rất quan trọng khi bạn cần quyết định có chấp nhận một lần quét, yêu cầu chụp lại, hay kích hoạt logic xử lý lỗi.

## Why Use Aspose.Barcode Java for Barcode Reading Quality?

- **Điểm tin cậy nhất quán** trên mọi symbology được hỗ trợ.  
- **Không có DLL gốc** – thuần Java, nên hoạt động trên bất kỳ nền tảng tương thích JVM nào.  
- **Kiểm soát chi tiết**: bạn có thể lấy chất lượng cho từng mã vạch, không chỉ một kết quả toàn cục pass/fail.  
- **Engine đọc tối ưu hiệu năng** có thể mở rộng từ máy để bàn tới dịch vụ đám mây.

## Prerequisites

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

- **Môi trường phát triển Java** – JDK 8 hoặc mới hơn, cùng IDE yêu thích (IntelliJ, Eclipse, VS Code, v.v.).  
- **Thư viện Aspose.Barcode Java** – tải JAR mới nhất từ trang chính thức: [Aspose.Barcode for Java](https://releases.aspose.com/barcode/java/).  
- **Một hình ảnh mẫu mã vạch** – hướng dẫn này sử dụng `code39Extended.jpg` nằm trong thư mục `BarcodeReader/advanced_features/`.

Sau khi đã chuẩn bị, hãy bắt đầu với đoạn mã.

## Import Namespaces

Các import sau sẽ cho phép bạn truy cập vào các lớp reader và result cần thiết để trích xuất chất lượng.

```java
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
```

### Step 1: Set the Resource Directory Path

Xác định thư mục chứa hình ảnh mẫu. `Utils.getDataDir` là một helper trả về đường dẫn tuyệt đối cho dự án hiện tại.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GetBarCodeRecognitionQualityInPercent.class)
        + "BarcodeReader/advanced_features/";
```

### Step 2: Initialize the BarCodeReader Object

Tạo một thể hiện `BarCodeReader`, chỉ tới file ảnh và yêu cầu nó thử **tất cả các loại mã vạch được hỗ trợ**.

```java
// Initialize the BarCodeReader object
BarCodeReader reader = new BarCodeReader(dataDir + "code39Extended.jpg",
        com.aspose.barcode.barcoderecognition.DecodeType.ALL_SUPPORTED_TYPES);
```

### Step 3: Read the Barcodes and Retrieve the Quality Percentage

Duyệt qua mỗi mã vạch được phát hiện, in ra văn bản, loại và phần trăm **reading quality** được trả về bởi `getReadingQuality()`.

```java
// Call the read method
for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println(result.getCodeText() + " Type: " + result.getCodeType());
    double percent = result.getReadingQuality();
    System.out.println("Percent: " + percent);
}
```

**What’s happening here?**  
- `readBarCodes()` trả về một collection các đối tượng `BarCodeResult`, mỗi đối tượng tương ứng với một mã vạch được tìm thấy.  
- `getReadingQuality()` trả về một `double` trong khoảng `0` đến `100`, biểu thị mức độ tin cậy.  
- Bạn có thể sử dụng giá trị này để quyết định liệu lần quét có chấp nhận được hay cần yêu cầu người dùng thực hiện lại.

## Common Issues and Solutions

| Issue | Cause | Fix |
|-------|-------|-----|
| **Quality always 0** | Hình ảnh có độ phân giải thấp hoặc bị mờ mạnh. | Sử dụng nguồn ảnh có độ phân giải cao hơn hoặc áp dụng tiền xử lý ảnh (ví dụ: làm nét). |
| **No barcodes detected** | Cờ `DecodeType` không đúng. | Đảm bảo bạn sử dụng `DecodeType.ALL_SUPPORTED_TYPES` hoặc chỉ định đúng loại bạn mong đợi. |
| **Exception on `Utils.getDataDir`** | Cấu trúc dự án khác với mẫu. | Thay thế lời gọi helper bằng đường dẫn tuyệt đối cố định hoặc đường dẫn tương đối phù hợp với bố cục của bạn. |

## Frequently Asked Questions

### Q1: Aspose.Barcode có tương thích với tất cả các loại mã vạch không?

A1: Aspose.Barcode hỗ trợ một loạt rộng các symbology, bao gồm 1‑D (Code‑39, Code‑128, UPC) và 2‑D (QR, DataMatrix, PDF417).

### Q2: Tôi có thể sử dụng Aspose.Barcode cho mục đích thương mại không?

A2: Có, bạn có thể dùng Aspose.Barcode trong cả dự án cá nhân và thương mại. Thông tin giấy phép có sẵn [tại đây](https://purchase.aspose.com/buy).

### Q3: Làm sao để lấy giấy phép tạm thời cho mục đích thử nghiệm?

A3: Nhận giấy phép tạm thời từ cổng thông tin Aspose [tại đây](https://purchase.aspose.com/temporary-license/).

### Q4: Tôi có thể tìm hỗ trợ và thảo luận cộng đồng ở đâu?

A4: Truy cập [diễn đàn Aspose.Barcode](https://forum.aspose.com/c/barcode/13) để nhận hỗ trợ từ cộng đồng và đội ngũ chính thức.

### Q5: Có tài liệu mẫu code nào trong tài liệu không?

A5: Có, các mẫu code chi tiết được cung cấp trong tài liệu chính thức [tại đây](https://reference.aspose.com/barcode/java/).

## Conclusion

Bằng cách tận dụng **Aspose.Barcode Java**, bạn có thể dễ dàng lấy **phần trăm chất lượng đọc mã vạch** cho bất kỳ ký hiệu nào được quét. Chỉ số này giúp bạn xây dựng logic xác thực thông minh hơn, cải thiện trải nghiệm người dùng và duy trì độ tin cậy dữ liệu cao trong các ứng dụng Java của mình.

---

**Last Updated:** 2025-11-30  
**Tested With:** Aspose.Barcode Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}