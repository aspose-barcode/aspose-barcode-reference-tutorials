---
category: general
date: 2026-08-12
description: Crie imagem de código de barras em C# usando BarCodeGenerator. Aprenda
  a gerar DataBar, controlar o tamanho da imagem do código de barras e criar múltiplos
  códigos de barras de forma eficiente.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- create multiple barcodes
- how to generate databar
- barcode image size
language: pt
lastmod: 2026-08-12
og_description: Crie imagem de código de barras em C# com BarCodeGenerator. Este tutorial
  mostra passo a passo como gerar códigos DataBar, ajustar o tamanho da imagem do
  código de barras e produzir múltiplos códigos de barras.
og_image_alt: Screenshot of a generated DataBar barcode image saved as PNG
og_title: Criar imagem de código de barras em C# – guia completo do BarCodeGenerator
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  headline: Create barcode image in C# with BarCodeGenerator
  type: TechArticle
- description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  name: Create barcode image in C# with BarCodeGenerator
  steps:
  - name: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
    text: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
  - name: Adjusting **barcode image size** by changing X‑dimension and bar height.
    text: Adjusting **barcode image size** by changing X‑dimension and bar height.
  - name: Using a loop to **create multiple barcodes** with different heights.
    text: Using a loop to **create multiple barcodes** with different heights.
  - name: Saving the images as PNG files and verifying the output.
    text: Saving the images as PNG files and verifying the output.
  type: HowTo
tags:
- barcode
- csharp
- barcodegenerator
- databar
- image-processing
title: Criar imagem de código de barras em C# com BarCodeGenerator
url: /pt/python-java/general/create-barcode-image-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar imagem de código de barras em C# com BarCodeGenerator

Se você precisa **criar imagem de código de barras** em uma aplicação .NET, este guia mostra exatamente como fazer isso com a classe `BarCodeGenerator`. Seja construindo um sistema POS de varejo ou uma ferramenta de rastreamento de inventário, você aprenderá a gerar símbolos DataBar, controlar o tamanho da imagem do código de barras e produzir vários códigos de barras em uma única execução.

Você também descobrirá como a API **barcode generator c#** permite ajustar dimensões, mudar formatos de saída e lidar com casos extremos, como strings de dados inválidas. Ao final do tutorial, você poderá **criar múltiplos códigos de barras** com confiança, sem escrever código repetitivo.

## Pré-requisitos

- .NET 6.0 ou posterior instalado  
- Um ambiente de desenvolvimento (Visual Studio, Rider ou VS Code)  
- O pacote NuGet Aspose.BarCode for .NET (ou qualquer biblioteca compatível que forneça `BarCodeGenerator`)  

Você pode adicionar o pacote com:

```bash
dotnet add package Aspose.BarCode
```

## O que este tutorial cobre

1. Configurar uma instância **barcode generator c#** para codificação DataBar Omni‑directional.  
2. Ajustar o **tamanho da imagem do código de barras** alterando a X‑dimension e a altura das barras.  
3. Usar um loop para **criar múltiplos códigos de barras** com alturas diferentes.  
4. Salvar as imagens como arquivos PNG e verificar a saída.  

Todos os trechos de código estão completos e prontos para copiar‑colar em um novo projeto de console.

![Create barcode image example](barcode-example.png){alt="Exemplo de criação de imagem de código de barras"}

## Etapa 1: Inicializar o gerador – fundamentos da criação de imagem de código de barras

O primeiro passo é instanciar `BarCodeGenerator` com a simbologia desejada. Para um símbolo DataBar Omni‑directional, você usa `EncodeTypes.DatabarOmniDirectional`.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for DataBar Omni‑directional.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarCodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // The rest of the steps are performed below.
        }
    }
}
```

**Por que isso importa:** Instanciar o gerador define as regras de codificação e a carga de dados. Se você omitir o valor correto de `EncodeTypes`, a biblioteca produzirá um código de barras não suportado ou lançará uma exceção.

## Etapa 2: Configurar X‑dimension e altura da barra – controlar o tamanho da imagem do código de barras

O tamanho visual de um código de barras é determinado por dois parâmetros:

| Parâmetro | O que controla | Faixa típica |
|-----------|----------------|--------------|
| `x_dimension.pixels` | Largura do menor módulo (o “ponto”) | 1 – 4 px |
| `bar_height.pixels`  | Altura das barras verticais | 30 – 150 px |

```csharp
// Set the module width to 2 px for a crisp, readable image.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set an initial bar height of 30 px.
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**Dica profissional:** Uma X‑dimension menor gera uma imagem de maior resolução, mas pode ser mais difícil de escanear em impressoras de baixa qualidade. Ajuste o valor com base no equipamento de leitura alvo.

## Etapa 3: Salvar o primeiro código de barras – criar imagem de código de barras com altura de 30 px

Agora você pode gerar a imagem e gravá‑la no disco. O método `Save` aceita um caminho de arquivo e um enum de formato de imagem.

```csharp
// Save the 30 px high barcode as a PNG file.
string outputFolder = @"C:\Barcodes";
generator.Save($"{outputFolder}\\Databar30.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar30.png (30 px height)");
```

**Resultado esperado:** Um arquivo PNG chamado `Databar30.png` aparece em `C:\Barcodes`. Ao abrir o arquivo, você verá um símbolo DataBar Omni‑directional com um padrão claro e de alto contraste.

## Etapa 4: Alterar a altura e gerar imagens adicionais – criar múltiplos códigos de barras

Para **criar múltiplos códigos de barras** com dimensões diferentes, basta modificar a propriedade `BarHeight` e chamar `Save` novamente. Isso evita reinstanciar o gerador, economizando memória e tempo de CPU.

```csharp
// Increase the bar height to 60 px for a larger barcode.
generator.Parameters.Barcode.BarHeight.Pixels = 60;
generator.Save($"{outputFolder}\\Databar60.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar60.png (60 px height)");

// You can repeat the process for any height you need.
int[] heights = { 90, 120 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputFolder}\\Databar{h}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved Databar{h}.png ({h} px height)");
}
```

**Por que isso funciona:** O objeto `BarCodeGenerator` mantém todo o estado de configuração. Alterar uma única propriedade atualiza o motor de renderização para a próxima chamada de `Save`, permitindo que você **crie múltiplos códigos de barras** de forma eficiente.

## Etapa 5: Avançado – como gerar DataBar com dados personalizados

O exemplo acima usa uma carga estática GS1. Em cenários reais, você frequentemente precisa incorporar identificadores de produto variáveis. A biblioteca aceita qualquer string que corresponda à especificação DataBar.

```csharp
string[] gtins = { "01234567890123", "98765432109876", "12345678901234" };
foreach (var gtin in gtins)
{
    // GS1 Application Identifier (01) + GTIN
    generator.CodeText = $"(01){gtin}";
    generator.Parameters.Barcode.BarHeight.Pixels = 50; // uniform height
    generator.Save($"{outputFolder}\\Databar_{gtin}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode for GTIN {gtin}");
}
```

**Ponto chave:** Definir `generator.CodeText` atualiza os dados codificados sem recriar o objeto. Este é o padrão recomendado de **como gerar databar** ao lidar com grandes conjuntos de dados.

## Etapa 6: Verificar e solucionar problemas – garantindo o tamanho correto da imagem do código de barras

Depois de gerar as imagens, você pode querer confirmar programaticamente que as dimensões correspondem às suas expectativas. A classe `Image` de `System.Drawing` pode ler o arquivo e relatar seu tamanho.

```csharp
using System.Drawing;

// Verify image dimensions
string[] files = { "Databar30.png", "Databar60.png", "Databar90.png" };
foreach (var file in files)
{
    using var img = Image.FromFile($"{outputFolder}\\{file}");
    Console.WriteLine($"{file}: {img.Width}px × {img.Height}px");
}
```

Se a altura não refletir o valor que você definiu, verifique:

- **X‑dimension**: Um valor muito pequeno pode fazer o renderizador arredondar a altura.  
- **Formato da imagem**: Alguns formatos (por exemplo, JPEG) aplicam compressão que pode alterar as dimensões em pixels ao salvar. PNG preserva as dimensões exatas.

## Etapa 7: Melhores práticas para tamanho de imagem de código de barras e desempenho

| Recomendação | Razão |
|--------------|-------|
| Mantenha `x_dimension.pixels` entre 2 – 3 px para a maioria dos scanners. | Equilibra legibilidade e tamanho do arquivo. |
| Use PNG para saída sem perdas quando a imagem será impressa. | Garante dimensões exatas e bordas nítidas. |
| Reutilize uma única instância de `BarCodeGenerator` ao gerar muitos códigos de barras. | Reduz a sobrecarga de alocação de objetos. |
| Valide a string de entrada contra o padrão GS1 antes de atribuir a `CodeText`. | Previna exceções em tempo de execução e leituras inválidas. |
| Armazene as imagens geradas em uma pasta dedicada com uma convenção de nomenclatura clara (por exemplo, `Databar_{GTIN}.png`). | Simplifica o processamento posterior e trilhas de auditoria. |

## Exemplo completo em funcionamento

Abaixo está o programa completo que incorpora todas as etapas, da inicialização à verificação. Copie o código para um novo projeto de console e execute-o.



## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Gerar imagem de código de barras – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Criar imagem de código de barras DotCode – linhas & colunas (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Como criar zona silenciosa de código de barras para ITF-14 usando Aspose.BarCode para .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}