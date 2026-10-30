---
category: general
date: 2026-10-28
description: Gere código de barras postal em C# usando o formato Planet. Este exemplo
  de código de barras Planet mostra como definir a largura do código de barras e salvar
  tanto as barras preenchidas quanto as vazias.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- set barcode width
- planet barcode example
language: pt
lastmod: 2026-10-28
og_description: Gere código de barras postal em C# com um exemplo completo de código
  de barras planetário. Aprenda a definir a largura do código de barras, produzir
  barras preenchidas e criar imagens de barras vazias.
og_image_alt: Screenshot of a generated Planet postal barcode saved as PNG
og_title: Gerar código de barras postal em C# – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  headline: How to generate postal barcode in C# – planet example
  type: TechArticle
- description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  name: How to generate postal barcode in C# – planet example
  steps:
  - name: Build the project (`dotnet build`).
    text: Build the project (`dotnet build`).
  - name: Run the executable (`dotnet run`).
    text: Run the executable (`dotnet run`).
  - name: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
    text: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
  - name: Open each image; you should see a series of vertical bars representing the
      numeric string
    text: Open each image; you should see a series of vertical bars representing the
      numeric string
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Como gerar código de barras postal em C# – exemplo planet
url: /pt/python-java/general/how-to-generate-postal-barcode-in-c-planet-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar código de barras postal em C# – exemplo planet

Se você precisa gerar código de barras postal em C#, este guia o conduz por uma solução completa. Você verá um exemplo prático de código de barras planet que codifica uma string numérica, permite definir a largura do código de barras e salva imagens de barras preenchidas e vazias.

Criar um código de barras postal não requer um pipeline de build complexo. Ao final deste tutorial você poderá integrar a geração de códigos de barras em qualquer aplicação .NET, personalizar a X‑dimension e escolher se as barras aparecerão preenchidas ou vazias.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou posterior instalado  
* Um ambiente de desenvolvimento C# (Visual Studio, VS Code ou Rider)  
* O pacote **Aspose.BarCode for .NET** NuGet (versão 23.10 ou mais recente)  

Você pode adicionar o pacote com o seguinte comando:

```bash
dotnet add package Aspose.BarCode
```

Os trechos de código abaixo assumem que você adicionou `using Aspose.BarCode.Generation;` no topo do seu arquivo.

## Gerar código de barras postal com a simbologia Planet

O primeiro passo é criar uma instância de `BarcodeGenerator` que use a simbologia Planet. Planet é um formato de código de barras postal usado por vários serviços postais nacionais.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a Planet barcode generator with the data to encode
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Additional configuration will be applied here (see next steps)

        // Save the filled‑bars image
        barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // Switch to empty bars and save the second image
        barcodeGenerator.Parameters.Barcode.FilledBars = false;
        barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**Por que isso importa:**  
`EncodeTypes.Planet` indica à biblioteca que deve usar o padrão de código de barras Planet, que codifica dados numéricos em uma série de barras e espaços. O construtor recebe a string de dados (`"123456"` neste caso) que você deseja codificar.

Executar o programa gera dois arquivos PNG no diretório de trabalho do executável:

* **PostalPlanetFilledBars.png** – as barras são renderizadas como retângulos pretos sólidos.  
* **PostalPlanetEmptyBars.png** – as barras são renderizadas como retângulos brancos com contorno preto, útil para impressão em fundos escuros.

## Definir a largura do código de barras (X‑dimension) em pixels

O tamanho visual de um código de barras é controlado pela X‑dimension, que define a largura de uma única barra. Ajustar esse valor garante que o código de barras seja lido corretamente na resolução de impressão pretendida.

```csharp
// Define the width of each bar (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

**Por que você deve configurá‑la:**  
Uma X‑dimension maior facilita a leitura do código de barras por scanners de baixa resolução, enquanto um valor menor reduz o tamanho geral da imagem para impressão de alta densidade. A largura padrão é 2 pixels; 4 pixels é um compromisso comum para a maioria das impressoras de mesa.

Você pode experimentar diferentes valores:

| Pixels | Caso de uso típico |
|--------|--------------------|
| 2      | Etiquetas de alta densidade |
| 4      | Impressão padrão de escritório |
| 6‑8    | Sinalização de grande formato |

**Dica:** Sempre teste o código de barras gerado com seu scanner alvo após alterar a X‑dimension.

## Exemplo de código de barras Planet – barras preenchidas vs vazias

Um código de barras Planet pode ser renderizado com barras sólidas (preenchidas) ou com contorno (vazias). A propriedade `FilledBars` alterna esse comportamento.

```csharp
// Save the barcode with the default filled bars
barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// Configure the generator to produce empty (unfilled) bars
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the barcode with empty bars
barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Por que você pode escolher barras vazias:**  
Barras vazias melhoram o contraste em embalagens de tom escuro, pois o interior branco de cada barra se destaca contra um fundo escuro. Barras preenchidas são o padrão e funcionam bem em mídias de cor clara.

**Saída esperada:**  

*Ambas as imagens exibem os mesmos dados codificados (`123456`).* A única diferença visual está no estilo das barras. Abaixo está uma descrição textual do que você verá:

* **Imagem de barras preenchidas:** Barras verticais pretas sólidas sobre fundo branco.  
* **Imagem de barras vazias:** Contornos pretos formando o mesmo padrão, com interiores brancos.

Você pode abrir os arquivos PNG em qualquer visualizador de imagens para verificar se o padrão corresponde à especificação Planet.

## Personalizar propriedades adicionais do código de barras (opcional)

Embora as etapas principais acima cubram a maioria dos cenários, você pode querer ajustar outras configurações:

| Propriedade | Descrição | Valor típico |
|-------------|-----------|--------------|
| `Barcode.Color` | Cor de primeiro plano das barras | `System.Drawing.Color.Black` |
| `Barcode.BackgroundColor` | Cor de preenchimento do fundo | `System.Drawing.Color.White` |
| `Barcode.CodeText` | Texto legível exibido abaixo do código de barras | Mesmo que os dados codificados ou um rótulo personalizado |
| `Barcode.ImageFormat` | Formato de saída (PNG, JPEG, BMP, etc.) | `BarCodeImageFormat.Png` |

Exemplo de definição de uma cor de primeiro plano personalizada:

```csharp
barcodeGenerator.Parameters.Barcode.Color = System.Drawing.Color.DarkBlue;
```

Esses ajustes opcionais ajudam a alinhar a identidade visual da empresa ou atender a requisitos específicos de impressão.

## Armadilhas comuns e como evitá‑las

| Problema | Causa | Solução |
|----------|-------|---------|
| Código de barras ilegível | X‑dimension muito pequena para o DPI da impressora | Aumente `XDimension.Pixels` para 4 ou mais |
| Arquivo de imagem corrompido | Permissões de gravação ausentes na pasta de destino | Use um caminho absoluto ou garanta que o diretório exista |
| Simbolologia errada usada | Passando `EncodeTypes.Code128` em vez de `EncodeTypes.Planet` | Verifique se o argumento `EncodeTypes` corresponde ao formato postal |

**Dica profissional:** Sempre gere um código de barras de teste e escaneie‑o com o hardware pretendido antes de implantar em produção.

## Exemplo completo e executável

Abaixo está um aplicativo de console autocontido que incorpora todas as etapas discutidas. Copie o código para um novo projeto de console .NET e execute‑o para ver os dois arquivos PNG aparecerem na pasta de saída.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a Planet barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the width of each bar (X‑dimension) to 4 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode with the default filled bars
            generator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved filled‑bars barcode as PostalPlanetFilledBars.png");

            // 4️⃣ Configure the generator to produce empty (unfilled) bars
            generator.Parameters.Barcode.FilledBars = false;

            // 5️⃣ Save the barcode with empty bars
            generator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved empty‑bars barcode as PostalPlanetEmptyBars.png");
        }
    }
}
```

**Etapas de verificação:**  

1. Compile o projeto (`dotnet build`).  
2. Execute o binário (`dotnet run`).  
3. Localize `PostalPlanetFilledBars.png` e `PostalPlanetEmptyBars.png` na pasta `bin/Debug/net6.0`.  
4. Abra cada imagem; você deverá ver uma série de barras verticais representando a string numérica


## O que você deve aprender a seguir?


Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como criar código de barras planet com barras preenchidas e vazias](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [Como definir a largura e gerar um código de barras Planet em C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Criar código de barras postal em C# – exemplo completo de gerador](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}