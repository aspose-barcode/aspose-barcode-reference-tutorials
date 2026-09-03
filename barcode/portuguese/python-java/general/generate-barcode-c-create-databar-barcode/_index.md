---
category: general
date: 2026-07-21
description: Gere código de barras C# rapidamente com Aspose.BarCode. Aprenda a criar
  código de barras DataBar, personalizar o tamanho do código de barras e exportar
  a imagem do código de barras em apenas alguns passos.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode c#
- create databar barcode
- customize barcode size
- change barcode dimensions
- export barcode image
language: pt
lastmod: 2026-07-21
og_description: Gere código de barras em C# usando Aspose.BarCode. Crie um código
  de barras DataBar, personalize seu tamanho e exporte a imagem instantaneamente.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode saved as PNG
og_title: Gerar código de barras C# – Criar códigos de barras DataBar com tamanho
  personalizado
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Generate barcode C# quickly with Aspose.BarCode. Learn to create DataBar
    barcode, customize barcode size, and export barcode image in just a few steps.
  headline: Generate barcode C# – Create DataBar barcode
  type: TechArticle
- questions:
  - answer: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, `Gif`, or `Svg`.
      The API handles the conversion automatically.
    question: What if I need a different image format?
  - answer: Technically you can set both, but Aspose will prioritize the last property
      you modify. It's safer to set *one* dimension and let the library compute the
      other for a valid DataBar.
    question: Can I change both rows and columns simultaneously?
  - answer: 'Use `barcodeGen.Parameters.Barcode.ForegroundColor` and `BackgroundColor`.
      Example:'
    question: How do I apply a foreground/background color?
  - answer: DataBar Expanded Stacked supports up to 74 numeric characters (or 30 alphanumeric).
      Exceeding that throws an exception.
    question: Is there a size limit for the encoded data?
  type: FAQPage
tags:
- barcode
- csharp
- databar
- image-export
- aspnet
title: Gerar código de barras C# – Criar código de barras DataBar
url: /pt/python-java/general/generate-barcode-c-create-databar-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerar código de barras C# – Criar código de barras DataBar

Quer **gerar código de barras C#** sem ter que percorrer uma infinidade de documentos? Você está no lugar certo. Neste guia vamos percorrer a criação de um **código de barras DataBar**, ajustar suas dimensões e, finalmente, **exportar a imagem do código de barras**—tudo com apenas algumas linhas de C#.

Imagine que você precise de um rótulo de produto compacto que caiba em uma etiqueta de prateleira pequena. Uma simbologia DataBar Expanded Stacked resolve isso, e com o Aspose.BarCode você pode controlar exatamente quantas colunas ou linhas são usadas. Pronto? Vamos mergulhar.

## O que você vai conseguir

- **Criar um código de barras DataBar** (a variante “expanded stacked”) do zero.  
- **Personalizar o tamanho do código de barras** definindo colunas ou linhas diretamente.  
- **Alterar as dimensões do código de barras** em tempo de execução sem recriar o gerador.  
- **Exportar a imagem do código de barras** para PNG (ou qualquer formato suportado pelo Aspose).  

Sem serviços externos, sem configurações complicadas—apenas código C# limpo e executável.

## Pré‑requisitos

- .NET 6.0 ou superior (o código também funciona no .NET Framework 4.7+).  
- Uma licença válida do Aspose.BarCode for .NET (ou você pode usar o modo de avaliação).  
- Uma IDE de sua escolha—Visual Studio, Rider ou VS Code servem.  

Se ainda não instalou o pacote NuGet, execute:

```bash
dotnet add package Aspose.BarCode
```

É só isso—nenhuma outra dependência.

## Etapa 1: Configurar o gerador de código de barras (Como **gerar código de barras C#**)

Primeiro, precisamos de uma instância `BarcodeGenerator` apontando para a simbologia **DataBar Expanded Stacked**. Esse objeto é o motor que cria a imagem posteriormente.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Initialize the generator with the desired symbology and data
BarcodeGenerator barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // Symbology
    "Databar Expanded Stacked long");    // Human‑readable text (optional)
```

*Por que isso importa*: O enum `EncodeTypes.DatabarExpandedStacked` indica ao Aspose que queremos a versão empilhada, ideal para espaços estreitos. O texto que passamos torna‑se o valor codificado; você pode substituí‑lo por qualquer cadeia numérica que sua aplicação exija.

## Etapa 2: **Personalizar o tamanho do código de barras** – definir colunas

Os códigos DataBar permitem influenciar a densidade visual especificando ou o número de **colunas** *ou* **linhas**. Comecemos pelas colunas. A contagem de linhas será calculada automaticamente para manter o código válido.

```csharp
// Set the number of columns; rows are computed automatically
barcodeGen.Parameters.Barcode.DataBar.Columns = 4;
```

*Dica de especialista*: As colunas afetam a largura do código de barras. Mais colunas → código mais largo, o que pode melhorar a confiabilidade da leitura em impressoras de baixa resolução.

## Etapa 3: **Exportar a imagem do código de barras** com a configuração de colunas

Agora gravamos a imagem no disco. Você pode escolher PNG, JPEG, BMP ou até SVG. Aqui usamos PNG para saída nítida e sem perdas.

```csharp
// Save the barcode image using the current column configuration
barcodeGen.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

> **Resultado esperado** – Abra `DatabarCols4.png` e você verá um DataBar empilhado com quatro colunas. Ele se parece com uma pilha densa de barras verticais, perfeito para um rótulo pequeno.

## Etapa 4: **Alterar as dimensões do código de barras** – definir linhas

Às vezes você precisa de um código de barras mais alto ao invés de mais largo. Troque para controle por linhas; o Aspose recalculará as colunas automaticamente.

```csharp
// Switch to row control – columns will be derived automatically
barcodeGen.Parameters.Barcode.DataBar.Rows = 3;
```

*Por que mudar?* As linhas afetam a altura do código de barras. Mais linhas tornam o símbolo mais alto, o que pode ser útil quando há espaço vertical, mas largura limitada.

## Etapa 5: **Exportar a imagem do código de barras** com a configuração de linhas

Salve a segunda variação. Observe que o nome do arquivo reflete a mudança; você também pode manter ambas as imagens para comparação.

```csharp
// Save the barcode image using the new row configuration
barcodeGen.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

> **Resultado** – `DatabarRows3.png` agora exibe uma versão mais alta dos mesmos dados, ainda perfeitamente legível.

## Exemplo completo em funcionamento

Juntando tudo, aqui está um aplicativo de console autônomo que você pode copiar‑colar e executar imediatamente:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator for DataBar Expanded Stacked
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Customize size – set columns (width)
        barcodeGen.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Export image with column setting
        string colPath = @"C:\Barcodes\DatabarCols4.png";
        barcodeGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column‑based barcode to {colPath}");

        // 4️⃣ Change dimensions – set rows (height)
        barcodeGen.Parameters.Barcode.DataBar.Rows = 3;

        // 5️⃣ Export image with row setting
        string rowPath = @"C:\Barcodes\DatabarRows3.png";
        barcodeGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row‑based barcode to {rowPath}");
    }
}
```

Execute o programa e, em seguida, abra os dois arquivos PNG. Você acabou de **gerar código de barras C#**, **personalizar o tamanho do código de barras**, **alterar as dimensões do código de barras** e **exportar a imagem do código de barras**—tudo em menos de um minuto.

## Perguntas frequentes & casos especiais

- **E se eu precisar de um formato de imagem diferente?**  
  Substitua `BarCodeImageFormat.Png` por `Jpeg`, `Bmp`, `Gif` ou `Svg`. A API cuida da conversão automaticamente.

- **Posso mudar linhas e colunas simultaneamente?**  
  Tecnicamente você pode definir ambos, mas o Aspose prioriza a última propriedade alterada. É mais seguro definir *uma* dimensão e deixar a biblioteca calcular a outra para um DataBar válido.

- **Como aplicar cor de primeiro plano/fundo?**  
  Use `barcodeGen.Parameters.Barcode.ForegroundColor` e `BackgroundColor`. Exemplo:  
  ```csharp
  barcodeGen.Parameters.Barcode.ForegroundColor = Color.DarkBlue;
  barcodeGen.Parameters.Barcode.BackgroundColor = Color.White;
  ```

- **Existe um limite de tamanho para os dados codificados?**  
  DataBar Expanded Stacked suporta até 74 caracteres numéricos (ou 30 alfanuméricos). Exceder esse limite gera uma exceção.

## Próximos passos

Agora que você dominou os fundamentos de **criar código de barras databar**, considere:

- Adicionar **anotações de texto** abaixo do código de barras (`barcodeGen.Parameters.CaptionAbove.Text`).  
- Incorporar o PNG diretamente em um PDF usando Aspose.PDF.  
- Gerar códigos de barras em lote percorrendo um CSV de IDs de produto.

Cada um desses tópicos se baseia no mesmo objeto `BarcodeGenerator`, então você não precisará começar do zero.

---

**Em resumo**: agora você sabe como **gerar código de barras C#**, **personalizar o tamanho do código de barras**, **alterar as dimensões do código de barras** e **exportar a imagem do código de barras** com o Aspose.BarCode. Brinque com os valores de coluna/linha, troque os formatos de imagem e integre o código ao seu sistema de inventário ou POS. Boa codificação!


## O que você deve aprender a seguir?


Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}