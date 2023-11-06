---
title: One-Dimensional Databar GS1 Encoding
linktitle: One-Dimensional Databar GS1 Encoding
second_title: Aspose.BarCode .NET API
description: 
type: docs
weight: 18
url: /net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
---

## Complete Source Code
```csharp
//Copyright(c) 2001-2021 Aspose Pty Ltd.All rights reserved.
//https://github.com/aspose-barcode/Aspose.BarCode-for-.NET
using System;
using Aspose.BarCode.Generation;

namespace Aspose.BarCode.Examples.CSharp.BarcodeGeneration
{
    internal class OneDDatabarGS1Encoding : OneDBase
    {
        public static void Run()
        {
            string path = "Your Directory Path";
            System.Console.WriteLine("OneDDatabarGS1Encoding:");

            BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
            //right codetext with GS1Encoding check
            gen.CodeText = "(01)12345678901231";
            gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
            gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
            //variable codetext without GS1Encoding check
            gen.CodeText = "ASPOSE";
            gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
            gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
            //variable codetext with GS1Encoding check
            try
            {
                gen.CodeText = "ASPOSE";
                gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
                gen.GenerateBarCodeImage();
            }
            catch (Exception e)
            {
                Console.WriteLine(e.Message);
            }
        }
    }
}
```
