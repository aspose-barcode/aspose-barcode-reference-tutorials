---
date: 2026-02-25
description: 學習如何使用 Aspose.BarCode for .NET 產生條碼圖像。本分步指南說明如何產生帶或不帶校驗碼的 Code 39 條碼。
linktitle: One-Dimensional Code 39 Configuration
second_title: Aspose.BarCode .NET API
title: 如何使用 Aspose.BarCode 產生條碼 – Code 39 設定
url: /zh-hant/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 單維 Code 39 設定

## 介紹

在本教學中，您將學習 **如何產生條碼** 圖片，特別是一維 Code 39 條碼，使用 Aspose.BarCode for .NET。條碼在現代企業中扮演關鍵角色，從庫存追蹤到快速且精確的資料檢索皆離不開它。Aspose.BarCode for .NET 是一套功能強大的函式庫，可簡化 .NET 應用程式中條碼的產生與客製化。本步驟說明將整個流程切分為易於理解的段落，確保即使是首次接觸條碼產生的開發者也能跟上。

## 快速答覆
- **主要使用的函式庫是什麼？** Aspose.BarCode for .NET  
- **可以產生帶檢查碼的條碼嗎？** 可以 – 設定 `IsChecksumEnabled = EnableChecksum.Yes`  
- **檢查碼是必須的嗎？** 不必 – 只要將其停用即可產生不含檢查碼的條碼  
- **範例使用的影像格式為何？** PNG (`BarCodeImageFormat.Png`)  
- **開發時需要授權嗎？** 可取得臨時授權以進行評估  

## 什麼是使用 Aspose.BarCode 產生條碼？
條碼產生是將文字或數字資料轉換為機器可讀的視覺圖樣的過程。Aspose.BarCode for .NET 支援數十種條碼規格，包括 Code 39，且讓您從尺寸、顏色到檢查碼計算皆可自行控制。

## 為何選擇 Code 39 以及檢查碼選項？
Code 39 在物流與製造業廣受採用，因為它能編碼字母與數字且不需特殊字元。加入檢查碼（或不加入）可在錯誤偵測與簡易性之間取得平衡，非常適合庫存標籤、運送標籤或簡易 POS 系統。

## 前置條件

在開始之前，請先確認您具備以下條件：

1. **.NET 開發環境** – 具備 .NET 框架的基本知識，並使用 Visual Studio 等 IDE。若您是 .NET 初學者，請先參考官方文件：[Microsoft .NET Documentation](https://docs.microsoft.com/en-us/dotnet/)。  
2. **Aspose.BarCode for .NET** – 下載並安裝此函式庫。相關文件與下載連結如下：[Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/) 以及 [Download Aspose.BarCode for .NET](https://releases.aspose.com/barcode/net/)。

完成前置條件後，讓我們進入產生單維 Code 39 條碼的主要步驟。

## 如何產生條碼：匯入命名空間
要開始使用 Aspose.BarCode for .NET，請在專案中匯入必要的命名空間。加入以下 `using` 陳述式即可取得條碼產生類別的存取權。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## 如何產生 Code 39 條碼（含與不含檢查碼）

以下示範會建立兩個條碼：一個 **不含檢查碼**，另一個 **含檢查碼**。程式碼唯一的差異在於 `IsChecksumEnabled` 旗標。

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

**程式碼說明**

1. **實例化** `BarcodeGenerator`，使用 `EncodeTypes.Code39Extended` 與資料字串 `"CODE"`。  
2. **切換** `IsChecksumEnabled` 以決定是否在條碼末端加入檢查碼。  
3. **儲存** 每個條碼為 PNG 檔案至指定資料夾。

現在您已擁有兩張可直接使用的條碼圖片：`OneCSCode39WithoutChecksum.png` 與 `OneCSCode39WithChecksum.png`。

## 常見問題與解決方式
| 問題 | 為何會發生 | 解決方式 |
|------|------------|----------|
| **找不到檔案路徑** | `path` 變數指向不存在的資料夾。 | 確認目錄已建立，或使用 `Directory.CreateDirectory(path)`。 |
| **資料中有無效字元** | Code 39 只支援英數字與少數特殊符號。 | 使用擴充的 Code 39 (`Code39Extended`) 以支援完整 ASCII 集，如上例所示。 |
| **檢查碼錯誤** | 未在需要時設定 `IsChecksumEnabled`。 | 依需求明確設定旗標為 `EnableChecksum.Yes` 或 `No`。 |

## 常見問答 (FAQs)

### Q: 可以在其他程式語言中使用 Aspose.BarCode for .NET 嗎？
A: Aspose.BarCode 主要設計給 .NET 使用，但 Aspose 亦提供其他平台的條碼函式庫。

### Q: Aspose.BarCode for .NET 有哪些授權方案？
A: 有，您可以在 Aspose 官網上探索授權選項，並申請臨時授權：[Aspose.BarCode Licensing](https://purchase.aspose.com/temporary-license/)。

### Q: Aspose.BarCode for .NET 適合用於 Web 應用程式嗎？
A: 適合，Aspose.BarCode for .NET 可在 Web 應用程式中使用，適用於各種開發專案。

### Q: 我可以自訂產生條碼的外觀嗎？
A: 當然可以，您可以自訂條碼的尺寸、顏色、字型等多項屬性。

### Q: 我該向哪裡取得支援或提問關於 Aspose.BarCode for .NET 的問題？
A: 您可前往 Aspose.BarCode 論壇取得答案與支援：[Aspose.BarCode Forum](https://forum.aspose.com/c/barcode/13)。

## 其他常見問答

**Q: 含檢查碼的條碼與不含檢查碼的條碼有何差異？**  
A: 檢查碼會多出一位數字，用於偵測抄寫錯誤。當資料完整性很重要時建議使用。

**Q: 產生的 PNG 檔案大小上限是多少？**  
A: 大小由 `gen.Parameters.ImageWidth/Height` 控制。於呼叫 `Save` 前調整這些屬性即可。

**Q: 可以產生其他影像格式的條碼嗎？**  
A: 可以，Aspose.BarCode 支援 JPEG、BMP、GIF、TIFF 等，只要更改 `BarCodeImageFormat` 列舉即可。

**Q: 有沒有辦法在 Web 應用程式中直接產生條碼而不寫入磁碟？**  
A: 可以將條碼儲存至 `MemoryStream`，再將位元組陣列直接回傳給客戶端。

## 結論
依照上述簡易步驟，您即可在 .NET 中 **產生條碼** 圖片，並完整掌控檢查碼、影像格式與視覺樣式。無論是管理庫存、處理訂單，或建置條碼功能的 Web 入口，Aspose.BarCode for .NET 都提供可靠且友善開發者的解決方案。

---

**最後更新日期：** 2026-02-25  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}