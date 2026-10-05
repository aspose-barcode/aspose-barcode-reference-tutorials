---
category: general
date: 2026-09-07
description: Gerar código de barras PDF417 em C# e aprender como definir as dimensões
  do código de barras para controle preciso. Siga este guia passo a passo para criar
  uma imagem PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- how to set barcode dimensions
language: pt
lastmod: 2026-09-07
og_description: Gere código de barras PDF417 em C# e aprenda como definir as dimensões
  do código de barras. Este tutorial mostra um exemplo completo e executável.
og_image_alt: Generated PDF417 barcode image with custom dimensions
og_title: Gerar código de barras PDF417 em C# – guia completo com dimensões
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  headline: How to generate PDF417 barcode in C# with custom dimensions
  type: TechArticle
- description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  name: How to generate PDF417 barcode in C# with custom dimensions
  steps:
  - name: Expected output
    text: '- **File:** `Pdf417Layout.png` (PNG, lossless) - **Dimensions:** Determined
      by `XDimension` (2 px) × (columns × rows) matrix - **Content:** A scannable
      PDF417 barcode encoding the Unicode string `Åspóse.Barcóde©`'
  - name: What if I need a larger image for printing?
    text: Increase `XDimension.Pixels` to 4 or 5. Larger values produce a higher‑resolution
      barcode but also increase file size.
  - name: Can I encode more data than the example string?
    text: Yes. PDF417 can hold up to 1,850 characters. Just replace the text argument
      in the `BarcodeGenerator` constructor. If the data exceeds the matrix capacity,
      the library automatically adds extra rows.
  - name: How does error correction work?
    text: 'PDF417 includes built‑in error correction. You can adjust its level via:'
  - name: What if the barcode appears blurry on screen?
    text: 'Make sure the output image’s DPI matches the display environment. You can
      set DPI when saving:'
  - name: Next steps
    text: '- Explore **how to generate PDF417 barcode** with different image formats
      (JPEG, BMP). - Learn **how to set barcode dimensions** dynamically based on
      user input or device DPI. - Integrate the barcode generation into an ASP.NET
      Core API to serve barcodes on demand.'
  type: HowTo
tags:
- barcode generation
- PDF417
- C#
title: Como gerar código de barras PDF417 em C# com dimensões personalizadas
url: /pt/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar código de barras PDF417 em C# com dimensões personalizadas

Se você precisa **gerar código de barras PDF417** em uma aplicação .NET, este guia mostra exatamente como fazer isso. Você verá um exemplo completo e executável que cria uma imagem PNG enquanto permite controlar as dimensões do código de barras.

Gerar um código de barras PDF417 é uma necessidade comum para sistemas de inventário, cartões de embarque e documentos seguros. Neste tutorial você também aprenderá **como definir as dimensões do código de barras** para que a saída corresponda às necessidades do seu layout.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

- .NET 6.0 SDK ou posterior instalado  
- Visual Studio 2022 (ou qualquer IDE compatível com C#)  
- O pacote NuGet **Aspose.BarCode for .NET** (ou qualquer biblioteca compatível que suporte PDF417)  

Você pode adicionar o pacote com o seguinte comando:

```bash
dotnet add package Aspose.BarCode
```

## Etapa 1: Criar um gerador de código de barras PDF417

O primeiro passo é instanciar um `BarcodeGenerator` com o tipo `EncodeTypes.Pdf417` e o texto que você deseja codificar. O objeto gerador contém todas as configurações do código de barras.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");
```

**Por que isso importa:** O enum `EncodeTypes.Pdf417` indica à biblioteca que deve usar a simbologia PDF417, que suporta grandes volumes de dados e correção de erros. A string de texto pode conter caracteres Unicode, permitindo codificar símbolos internacionais sem trabalho extra.

## Etapa 2: Como definir as dimensões do código de barras

Controlar o tamanho de cada módulo (o menor quadrado preto/branco) determina a resolução geral da imagem. A propriedade `XDimension.Pixels` define a largura em pixels de um módulo.

```csharp
        // Step 2: Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Por que isso importa:** Um `XDimension` maior gera uma imagem de alta resolução, útil para impressão ou leitura à distância. Por outro lado, um valor menor reduz o tamanho do arquivo para uso na web.

## Etapa 3: Definir o layout PDF417 (colunas e linhas)

O PDF417 permite influenciar a forma da matriz especificando o número de colunas e linhas. Isso pode afetar a legibilidade e o tamanho físico do código de barras.

```csharp
        // Step 3: Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

**Por que isso importa:** Ajustar colunas e linhas permite encaixar o código de barras em um espaço específico ou atender aos requisitos de proporção de um scanner. A biblioteca adiciona automaticamente preenchimento se os dados não preencherem a matriz completamente.

## Etapa 4: Salvar o código de barras como imagem PNG

Por fim, grave o código de barras gerado em um arquivo. PNG preserva qualidade sem perdas, tornando‑o ideal para processamento posterior.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

Ao executar o programa, `Pdf417Layout.png` aparecerá na pasta de saída do projeto. A imagem se parece com isto:

![Generated PDF417 barcode image with custom dimensions](og_image_placeholder.png)

*Texto alternativo da imagem: Imagem de código de barras PDF417 gerado com dimensões personalizadas*  

**Por que isso importa:** Salvar como PNG garante que as dimensões exatas dos módulos que você definiu sejam mantidas, o que é crucial para aplicações de leitura subsequentes.

## Exemplo completo em um bloco

Abaixo está o programa completo que você pode copiar, colar e executar sem modificações (exceto o caminho de saída, se desejar).

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

### Saída esperada

- **Arquivo:** `Pdf417Layout.png` (PNG, sem perdas)  
- **Dimensões:** Determinadas por `XDimension` (2 px) × matriz (colunas × linhas)  
- **Conteúdo:** Um código de barras PDF417 legível que codifica a string Unicode `Åspóse.Barcóde©`

## Perguntas comuns e casos de borda

### E se eu precisar de uma imagem maior para impressão?

Aumente `XDimension.Pixels` para 4 ou 5. Valores maiores produzem um código de barras de alta resolução, mas também aumentam o tamanho do arquivo.

### Posso codificar mais dados do que a string do exemplo?

Sim. PDF417 pode armazenar até 1.850 caracteres. Basta substituir o argumento de texto no construtor `BarcodeGenerator`. Se os dados excederem a capacidade da matriz, a biblioteca adiciona automaticamente linhas extras.

### Como funciona a correção de erros?

PDF417 inclui correção de erros embutida. Você pode ajustar seu nível via:

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // 0‑8, higher = more correction
```

Níveis mais altos aumentam a robustez ao custo de códigos de barras maiores.

### E se o código de barras aparecer borrado na tela?

Certifique‑se de que o DPI da imagem de saída corresponda ao ambiente de exibição. Você pode definir o DPI ao salvar:

```csharp
barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png, 300);
```

## Dicas profissionais

- **Dica pro:** Sempre teste o código de barras gerado com o scanner real que você pretende usar. Dispositivos diferentes têm tolerâncias variadas para tamanho de módulo e zonas silenciosas.  
- **Cuidado com:** Valores muito pequenos de `XDimension` (< 1 px) podem ser renderizados como linhas invisíveis em telas de alta DPI.  
- **Dica para apps web:** Sirva o PNG com `Cache-Control: public, max-age=86400` para reduzir a sobrecarga de geração repetida.

## Conclusão

Agora você sabe como **gerar código de barras PDF417** em C# e definir **precisamente as dimensões do código de barras** para atender a qualquer requisito. O exemplo completo e executável demonstra a criação de uma imagem PNG com layout de colunas/linhas e tamanho de módulo personalizados, pronta para impressão ou distribuição digital.

### Próximos passos

- Explore **como gerar código de barras PDF417** com diferentes formatos de imagem (JPEG, BMP).  
- Aprenda **como definir dimensões do código de barras** dinamicamente com base na entrada do usuário ou DPI do dispositivo.  
- Integre a geração de códigos de barras em uma API ASP.NET Core para servir códigos sob demanda.

Sinta‑se à vontade para experimentar outras configurações do PDF417, como correção de erros, margens e cor. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui código completo e funcional com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Generate PDF417 Barcode in C# – Complete Guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}