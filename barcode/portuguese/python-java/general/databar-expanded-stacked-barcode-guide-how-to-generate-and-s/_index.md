---
category: general
date: 2026-07-27
description: Guia de código de barras empilhado expandido Databar – aprenda como gerar
  código de barras, definir dimensões, criar código de barras Databar e configurar
  o tamanho do código de barras em poucos passos.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- how to generate barcode
- how to set dimensions
- create databar barcode
- configure barcode size
language: pt
lastmod: 2026-07-27
og_description: O tutorial de código de barras empilhado expandido da Databar mostra
  como gerar o código de barras, definir dimensões e configurar o tamanho do código
  de barras com exemplos de código claros.
og_image_alt: Screenshot of a Databar Expanded Stacked barcode with custom column
  and row settings
og_title: Código de barras Databar Expanded Stacked – tutorial rápido de C#
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: databar expanded stacked barcode guide – learn how to generate barcode,
    set dimensions, create databar barcode, and configure barcode size in a few steps.
  headline: databar expanded stacked barcode guide – how to generate and size it in
    C#
  type: TechArticle
- description: databar expanded stacked barcode guide – learn how to generate barcode,
    set dimensions, create databar barcode, and configure barcode size in a few steps.
  name: databar expanded stacked barcode guide – how to generate and size it in C#
  steps:
  - name: Why we re‑instantiate the generator
    text: You might wonder why we create a new `BarcodeGenerator` before setting rows.
      The **columns** and **rows** properties belong to the same `DataBar` object,
      but they each have a default that the other side respects. By starting with
      a fresh instance we guarantee that the column setting doesn’t inadvert
  - name: What does “column” mean for a **databar expanded stacked** symbol?
    text: '- **Columns** split the stacked barcode horizontally. More columns mean
      the symbol becomes wider, which can be useful when you have limited vertical
      space. - **Rows** stack the columns vertically. Adding rows makes the barcode
      taller, helpful for narrow label widths.'
  - name: When should you adjust these dimensions?
    text: '| Scenario | Recommended tweak | |----------|-------------------| | Thin
      label printer (e.g., receipt printers) | Reduce columns, increase rows. | |
      Wide shelf label (e.g., price tags) | Increase columns, keep rows low. | | High‑resolution
      print (e.g., packaging) | Use default layout but boost DPI v'
  - name: 1️⃣ *What if my data string exceeds the maximum length?*
    text: The **databar expanded stacked** format can encode up to 74 numeric characters
      or 41 alphanumeric characters. If you exceed that, the generator throws a `BarcodeException`.
      Trim or hash the data, or switch to a different barcode type (e.g., `Pdf417`).
  - name: 2️⃣ *Can I output SVG instead of PNG?*
    text: Absolutely. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Svg`.
      SVG is vector‑based and scales without loss—great for web apps.
  - name: 3️⃣ *Do I need to worry about background color?*
    text: 'By default the background is white. To make it transparent, set:'
  - name: 4️⃣ *Is there a way to add a caption beneath the barcode?*
    text: Yes. Use `generator.Parameters.Barcode.BarcodeImageFormat = BarCodeImageFormat.Png;`
      and then combine the barcode with a `Graphics` object to draw text. That’s a
      bit more involved, but the Aspose API provides a `BarcodeGenerator.Save` overload
      that accepts a `Stream`—you can post‑process the image a
  type: HowTo
tags:
- barcode
- databar
- csharp
title: Guia de código de barras Databar Expanded Stacked – como gerar e dimensionar
  em C#
url: /pt/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# databar expanded stacked barcode – Tutorial Completo em C#

Já se perguntou como gerar um **databar expanded stacked** barcode sem precisar vasculhar intermináveis documentos de API? Você não está sozinho. Seja construindo um sistema de checkout de varejo ou uma impressora de etiquetas logísticas, dominar esse tipo de código de barras pode economizar horas de tentativa‑e‑erro.

Neste guia vamos percorrer todo o processo: da instalação da biblioteca, à criação do código de barras, a **como definir dimensões** para colunas e linhas, e finalmente **configurar o tamanho do código de barras** para suas necessidades de impressão exatas. Ao final você terá um projeto C# pronto‑para‑executar que produz duas imagens PNG—uma com colunas personalizadas, outra com linhas personalizadas.

---

## O que você aprenderá

- **Como gerar imagens de código de barras** usando a biblioteca Aspose.BarCode para .NET.  
- A diferença entre **colunas** e **linhas** em um símbolo **databar expanded stacked**.  
- Passos práticos para **criar código de barras databar** com um layout específico.  
- Dicas sobre **configurar o tamanho do código de barras**, DPI e formato de imagem.  
- Tratamento de casos extremos quando a string de dados é muito longa ou quando você precisa de um fundo transparente.

Nenhuma experiência prévia com Aspose é necessária; basta uma configuração básica de C# e curiosidade sobre códigos de barras.

---

## Pré‑requisitos

| Requisito | Por que é importante |
|-----------|----------------------|
| .NET 6.0 SDK ou posterior | Fornece os recursos mais recentes da linguagem e desempenho de tempo de execução. |
| Visual Studio 2022 (ou VS Code) | Facilita o gerenciamento de pacotes NuGet e a execução do exemplo. |
| Acesso à internet para baixar o pacote NuGet **Aspose.BarCode** | A biblioteca contém a classe `BarcodeGenerator` que usaremos. |
| Uma pasta onde você possa gravar (ex.: `C:\Barcodes\`) | Onde os arquivos PNG serão salvos. |

Se você não tem algum desses itens, obtenha‑os agora—caso contrário você encontrará um erro de “referência ausente” mais tarde e isso será perda de tempo.

---

## Step 1: Install Aspose.BarCode via NuGet

Abra a pasta do seu projeto em um terminal e execute:

```bash
dotnet new console -n DatabarDemo
cd DatabarDemo
dotnet add package Aspose.BarCode
```

> **Dica:** A edição comunitária gratuita funciona na maioria dos cenários de desenvolvimento, mas se precisar de suporte comercial, adquira uma licença da Aspose e chame `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` no início do `Main`.

O pacote `Aspose.BarCode` inclui tudo que você precisa para **como gerar código de barras** imagens, incluindo o valor enum `EncodeTypes.DatabarExpandedStacked`.

---

## Step 2: Write the Core Code – Create the Barcode Generator

Crie um arquivo chamado `Program.cs` (ou substitua o padrão) e cole o código a seguir. Este bloco mostra a etapa **criar código de barras databar** e também nos prepara para **configurar o tamanho do código de barras** mais adiante.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace DatabarDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Define the output folder – change this to your own path
            string outputFolder = @"C:\Barcodes\";

            // -----------------------------------------------------------------
            // 1️⃣  Create a barcode generator for Databar Expanded Stacked
            // -----------------------------------------------------------------
            // The second argument is the data you want to encode.
            // For Databar Expanded Stacked the string can be fairly long.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // -----------------------------------------------------------------
            // 2️⃣  Set a custom column count (default rows are used)
            // -----------------------------------------------------------------
            generator.Parameters.Barcode.DataBar.Columns = 4;   // ← how to set dimensions
            generator.Save($"{outputFolder}DatabarCols4.png", BarCodeImageFormat.Png);

            // -----------------------------------------------------------------
            // 3️⃣  Re‑initialize the generator for the same data
            // -----------------------------------------------------------------
            // This demonstrates that column and row settings are independent.
            generator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // -----------------------------------------------------------------
            // 4️⃣  Set a custom row count (default columns are used)
            // -----------------------------------------------------------------
            generator.Parameters.Barcode.DataBar.Rows = 3;      // ← how to set dimensions
            generator.Save($"{outputFolder}DatabarRows3.png", BarCodeImageFormat.Png);

            // -----------------------------------------------------------------
            // 5️⃣  Optional: tweak overall image size and resolution
            // -----------------------------------------------------------------
            // If you need a larger barcode for printing, adjust the X/Y DPI.
            generator.Parameters.Image.XResolution = 300; // DPI
            generator.Parameters.Image.YResolution = 300;
            generator.Parameters.Image.Width = 400;       // pixels
            generator.Parameters.Image.Height = 200;      // pixels
            generator.Save($"{outputFolder}DatabarLarge.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully!");
        }
    }
}
```

### Por que reinstanciamos o gerador

Você pode se perguntar por que criamos um novo `BarcodeGenerator` antes de definir linhas. As propriedades **colunas** e **linhas** pertencem ao mesmo objeto `DataBar`, mas cada uma tem um padrão que a outra respeita. Ao iniciar com uma instância nova garantimos que a configuração de coluna não afete inadvertidamente a contagem de linhas, o que é uma armadilha comum ao **configurar o tamanho do código de barras**.

---

## Step 3: Run the Project and Verify the Output

Do terminal, execute:

```bash
dotnet run
```

Se tudo estiver conectado corretamente, você verá:

```
Barcodes generated successfully!
```

Navegue até `C:\Barcodes\` (ou a pasta que você escolheu). Você deverá encontrar três arquivos PNG:

| Arquivo | O que mostra |
|---------|--------------|
| `DatabarCols4.png` | Um código de barras **databar expanded stacked** com **4 colunas** (linhas padrão). |
| `DatabarRows3.png` | Mesmos dados, mas agora com **3 linhas** (colunas padrão). |
| `DatabarLarge.png` | Uma versão maior onde **configuramos o tamanho do código de barras** via DPI e dimensões em pixels. |

Abra qualquer um deles em um visualizador de imagens—sim, o código de barras parece exatamente como o que você veria em uma prateleira de supermercado, apenas com um layout personalizado.

---

## Step 4: Deep Dive – Understanding Columns vs. Rows

### O que significa “coluna” para um símbolo **databar expanded stacked**?

- **Colunas** dividem o código de barras empilhado horizontalmente. Mais colunas tornam o símbolo mais largo, o que pode ser útil quando há espaço vertical limitado.  
- **Linhas** empilham as colunas verticalmente. Adicionar linhas torna o código de barras mais alto, útil para larguras de etiqueta estreitas.

Ambas as propriedades aceitam valores de 2 a 8 (dependendo do comprimento dos dados). Se você tentar definir um valor fora desse intervalo, a Aspose lança uma `ArgumentException`. Por isso mantivemos os números modestos (4 colunas, 3 linhas) na demonstração.

### Quando você deve ajustar essas dimensões?

| Cenário | Ajuste recomendado |
|---------|--------------------|
| Impressora de etiquetas finas (ex.: impressoras de recibos) | Reduzir colunas, aumentar linhas. |
| Etiqueta de prateleira larga (ex.: etiquetas de preço) | Aumentar colunas, manter linhas baixas. |
| Impressão de alta resolução (ex.: embalagens) | Usar layout padrão, mas aumentar DPI via `XResolution`/`YResolution`. |

---

## Step 5: Advanced – Fine‑tuning the Barcode Size

Se você precisar de um **configurar o tamanho do código de barras** além dos 200 × 100 px padrão, tem duas alavancas:

1. **Resolução da imagem (DPI)** – Um DPI maior fornece mais detalhes, essencial para scanners que exigem bordas nítidas.  
2. **Dimensões explícitas em pixels** – Substitui o tamanho calculado automaticamente com `Parameters.Image.Width` e `Height`.

Aqui está um trecho rápido que força uma imagem de 600 × 300 px a 600 DPI:

```csharp
generator.Parameters.Image.XResolution = 600;
generator.Parameters.Image.YResolution = 600;
generator.Parameters.Image.Width = 600;   // pixels
generator.Parameters.Image.Height = 300;  // pixels
generator.Save($"{outputFolder}DatabarHighRes.png", BarCodeImageFormat.Png);
```

> **Atenção:** Definir uma largura/altura muito pequena para a contagem de colunas/linhas escolhida truncará o código de barras, causando falhas na leitura. Sempre teste com um scanner real após mudar as dimensões.

---

## Perguntas Frequentes & Casos de Borda

### 1️⃣ *E se a minha string de dados exceder o comprimento máximo?*  
O formato **databar expanded stacked** pode codificar até 74 caracteres numéricos ou 41 alfanuméricos. Se você ultrapassar isso, o gerador lança uma `BarcodeException`. Trunque ou hash os dados, ou troque para outro tipo de código de barras (ex.: `Pdf417`).

### 2️⃣ *Posso gerar SVG em vez de PNG?*  
Claro. Substitua `BarCodeImageFormat.Png` por `BarCodeImageFormat.Svg`. SVG é baseado em vetor e escala sem perda—ideal para aplicativos web.

### 3️⃣ *Preciso me preocupar com a cor de fundo?*  
Por padrão o fundo é branco. Para torná‑lo transparente, defina:

```csharp
generator.Parameters.Image.BackgroundColor = System.Drawing.Color.Transparent;
```

### 4️⃣ *Existe uma forma de adicionar uma legenda abaixo do código de barras?*  
Sim. Use `generator.Parameters.Barcode.BarcodeImageFormat = BarCodeImageFormat.Png;` e então combine o código de barras com um objeto `Graphics` para desenhar texto. É um pouco mais complexo, mas a API Aspose oferece uma sobrecarga `BarcodeGenerator.Save` que aceita um `Stream`—você pode pós‑processar a imagem depois.

---

## Step‑by‑Step Recap (Quick Reference)

| Etapa | Ação | Trecho de código |
|------|------|-------------------|
| 1️⃣ | Instalar Aspose.BarCode | `dotnet add package Aspose.BarCode` |
| 2️⃣ | Criar gerador para **databar expanded stacked** | `new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "your` |

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [How to Generate Barcode Java – Complete Configuration Guide](/barcode/english/java/barcode-configuration/)
- [Create Barcode with Aspose - Set X & Y Dimensions in Java](/barcode/english/java/barcode-configuration/managing-x-y-dimension-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}