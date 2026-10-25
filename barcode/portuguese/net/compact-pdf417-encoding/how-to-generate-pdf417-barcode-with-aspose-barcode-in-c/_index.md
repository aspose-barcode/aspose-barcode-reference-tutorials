---
category: general
date: 2026-10-24
description: Aprenda como gerar código de barras PDF417 usando Aspose.BarCode em C#
  com configurações compactas e controle da XDimension do código de barras.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode
- compact PDF417
- barcode XDimension
- PDF417 columns
language: pt
lastmod: 2026-10-24
og_description: Gere código de barras PDF417 em C# com Aspose.BarCode. Siga este guia
  completo para criar imagens PDF417 compactas, controlar XDimension e definir colunas.
og_image_alt: Screenshot of generated PDF417 barcode using Aspose.BarCode
og_title: Gerar código de barras PDF417 com Aspose.BarCode – passo a passo em C#
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  headline: How to generate PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  name: How to generate PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: 1. Changing the image format
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 2. Encoding large amounts of data
    text: 'PDF417 can store up to ~1.1 KB of text. When the payload exceeds the capacity
      of three columns, the library automatically adds rows. To keep the barcode compact,
      you can:'
  - name: 3. Using a license to remove the trial watermark
    text: '```csharp Aspose.BarCode.License license = new Aspose.BarCode.License();
      license.SetLicense("Aspose.BarCode.lic"); ```'
  - name: 4. Handling exceptions
    text: '```csharp try { generator.Save(outputPath, BarCodeImageFormat.Png); } catch
      (Exception ex) { Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
      } ```'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- PDF417
- C#
title: Como gerar código de barras PDF417 com Aspose.BarCode em C#
url: /pt/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar código de barras PDF417 com Aspose.BarCode em C#

Se você precisa **gerar código de barras PDF417** em uma aplicação .NET, este guia mostra uma solução completa, pronta‑para‑executar. Você verá como o Aspose.BarCode torna o processo simples ao mesmo tempo que oferece controle detalhado sobre **compact PDF417**, **barcode XDimension** e **PDF417 columns**.

Criar um código de barras é uma necessidade comum para sistemas de inventário, plataformas de bilhetagem e fluxos de trabalho de documentos. Ao final deste tutorial você terá um programa C# autônomo que produz uma imagem PNG nítida de um código de barras PDF417, pronta para ser incorporada em qualquer interface ou impressa em um rótulo.

## O que você precisará

- .NET 6.0 SDK ou posterior (o código também funciona com .NET Framework 4.6+)
- Visual Studio 2022 ou qualquer editor C# de sua preferência
- Uma licença válida do Aspose.BarCode para .NET (o trial gratuito funciona para desenvolvimento)
- Familiaridade básica com a sintaxe C#

> **Dica profissional:** Se você está avaliando o Aspose.BarCode, faça o download do trial no site oficial e adicione o pacote NuGet `Aspose.BarCode` ao seu projeto. O trial adiciona uma pequena marca d'água à imagem gerada, que desaparece ao aplicar a licença.

## Etapa 1: Instalar o pacote NuGet Aspose.BarCode

Abra um terminal na pasta da sua solução e execute:

```bash
dotnet add package Aspose.BarCode
```

O comando obtém a versão estável mais recente (em outubro 2026, versão 23.12). Adicionar o pacote restaura o namespace `Aspose.BarCode.Generation` que você usará para **gerar código de barras PDF417** em imagens.

## Etapa 2: Criar um projeto de console C# básico

Se ainda não tem um projeto, crie um:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Abra `Program.cs`. O esqueleto já contém um método `Main` onde colocaremos o código de geração do código de barras.

## Etapa 3: Inicializar o gerador de código de barras

Primeiro, importe o namespace necessário:

```csharp
using Aspose.BarCode.Generation;
```

Em seguida, dentro de `Main`, instancie `BarcodeGenerator` com a simbologia PDF417 e os dados que você deseja codificar:

```csharp
// Step 3: Initialize the generator for a PDF417 barcode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

A string inclui caracteres Unicode para demonstrar que o Aspose.BarCode lida corretamente com entrada não‑ASCII. Se você precisar apenas de ASCII, substitua o texto por qualquer string simples.

## Etapa 4: Ajustar o barcode XDimension (tamanho do módulo)

O **barcode XDimension** determina a largura da barra mais fina (o módulo). Definir isso em pixels oferece controle pixel‑perfect sobre o tamanho final da imagem:

```csharp
// Step 4: Set the module size – XDimension in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Um valor de `2` pixels gera uma imagem compacta sem sacrificar a confiabilidade da leitura. Aumente o valor para códigos maiores ou diminua para layouts muito densos.

## Etapa 5: Configurar opções compactas do PDF417

Duas configurações específicas do PDF417 afetam drasticamente a pegada visual:

| Configuração | Significado | Valor típico para saída compacta |
|--------------|-------------|----------------------------------|
| `Columns` | Número de colunas de dados | `3` |
| `Truncate` (compact mode) | Omitir a zona silenciosa à direita e reduzir o número de linhas | `true` |

Aplique-as da seguinte forma:

```csharp
// Step 5: Use a small number of columns and enable compact mode
generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417
```

Usar **PDF417 columns** definido como `3` junto com `Truncate = true` cria um *compact PDF417* que cabe perfeitamente em um rótulo padrão e ainda é legível pela maioria dos scanners.

## Etapa 6: Salvar a imagem do código de barras

Por fim, grave o código de barras no disco. O exemplo salva um PNG, mas o Aspose.BarCode também suporta BMP, JPEG, GIF, TIFF e SVG:

```csharp
// Step 6: Save the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

A constante `BarCodeImageFormat.Png` indica à biblioteca que deve produzir um PNG sem perdas, ideal para processamento adicional ou impressão.

## Código-fonte completo e executável

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator for PDF417 with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size – barcode XDimension in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Configure compact PDF417 options
        generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
        generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417

        // 4️⃣ Save as PNG
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "CompactPdf417.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

Executar o programa gera `CompactPdf417.png` na pasta raiz do projeto. Abra o arquivo com qualquer visualizador de imagens; você verá um código de barras PDF417 densamente empacotado que codifica a string *Åspóse.Barcóde©*.

![Captura de tela do código de barras PDF417 gerado usando Aspose.BarCode](placeholder-image.png "Código de barras PDF417 gerado")

*Texto alternativo da imagem: Captura de tela do código de barras PDF417 gerado usando Aspose.BarCode* – este texto alternativo contém a palavra‑chave principal para acessibilidade e SEO.

## Verificando o resultado

1. Abra o arquivo PNG. O código de barras deve consistir em três colunas de dados verticais com um layout compacto (sem zonas silenciosas extras no lado direito).  
2. Escaneie a imagem com um scanner de código de barras de smartphone que suporte PDF417. O texto decodificado deve corresponder à string de entrada original.  
3. Se o scanner falhar, tente aumentar `XDimension.Pixels` para `3` ou `4`. Módulos maiores melhoram a legibilidade em dispositivos de baixa resolução.

## Variações comuns e casos de borda

### 1. Alterando o formato da imagem

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

SVG é baseado em vetor, o que mantém o código de barras nítido em qualquer nível de zoom — útil para páginas web.

### 2. Codificando grandes quantidades de dados

PDF417 pode armazenar até ~1,1 KB de texto. Quando a carga excede a capacidade de três colunas, a biblioteca adiciona linhas automaticamente. Para manter o código de barras compacto, você pode:

- Reduzir o comprimento dos dados (por exemplo, usar um identificador ao invés de uma mensagem completa)  
- Aumentar o número de **PDF417 columns** (por exemplo, `generator.Parameters.Barcode.Pdf417.Columns = 5;`)

### 3. Usando uma licença para remover a marca d'água do trial

```csharp
Aspose.BarCode.License license = new Aspose.BarCode.License();
license.SetLicense("Aspose.BarCode.lic");
```

Coloque o arquivo de licença ao lado do executável. Após a licenciamento, a imagem gerada não contém marca d'água.

### 4. Tratamento de exceções

```csharp
try
{
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

Falhas típicas incluem permissões de gravação insuficientes ou um formato de imagem não suportado.

## Por que as configurações são importantes

- **barcode XDimension** – Controla o peso visual de cada barra. Muito pequeno torna o código de barras ilegível; muito grande desperdiça espaço.  
- **PDF417 columns** – Menos colunas produzem um código de barras mais estreito, mas aumentam o número de linhas.

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como gerar código de barras PDF417 com Aspose – Guia completo](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Gerar código de barras PDF417 com configurações compactas em C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-with-compact-settings-in-c/)
- [Como salvar código de barras e gerar PDF417 com Aspose em C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}