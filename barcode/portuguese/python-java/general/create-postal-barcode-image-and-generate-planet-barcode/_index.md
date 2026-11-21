---
category: general
date: 2026-11-20
description: Crie imagem de código de barras postal em C# rapidamente. Aprenda como
  gerar códigos de barras Planet e RM4SCC com estilos de barra personalizáveis.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- postal barcode C#
- Aspose.BarCode example
- barcode image generation
language: pt
lastmod: 2026-11-20
og_description: Crie imagem de código de barras postal em C# com Aspose.BarCode. Este
  tutorial mostra como gerar código de barras Planet, personalizar estilos de barras
  e produzir imagens RM4SCC.
og_image_alt: Create postal barcode image example showing filled and empty bars
og_title: Criar imagem de código de barras postal em C# – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create postal barcode image in C# quickly. Learn how to generate planet
    barcode and RM4SCC barcodes with customizable bar styles.
  headline: Create postal barcode image and generate planet barcode
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Criar imagem de código de barras postal e gerar código de barras planetário
url: /pt/python-java/general/create-postal-barcode-image-and-generate-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar imagem de código de barras postal e gerar código de barras planet

Crie uma imagem de código de barras postal em C# usando a biblioteca Aspose.BarCode. Se você precisar gerar códigos de barras planet ou RM4SCC para aplicações de correspondência, este tutorial fornece uma solução completa e pronta‑para‑executar.

Gerar códigos de barras para serviços postais frequentemente requer dimensões precisas e a opção de alternar entre estilos de barra preenchida e vazia. Este guia orienta você a configurar a pasta de saída, criar códigos de barras Planet preenchidos e vazios, e produzir um código de barras RM4SCC com as mesmas configurações visuais. Ao final, você terá quatro arquivos PNG que podem ser usados diretamente no seu fluxo de trabalho de envio.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 ou posterior instalado  
* Visual Studio 2022 (ou qualquer IDE C# que você prefira)  
* O pacote NuGet **Aspose.BarCode** (`Install-Package Aspose.BarCode`)  

Nenhuma configuração adicional é necessária; o código usa apenas a fonte padrão e o codificador PNG.

## Criar imagem de código de barras postal – visão geral

O núcleo do processo é a classe `BarcodeGenerator`. Ela aceita um valor `EncodeTypes` que determina a simbologia do código de barras (por exemplo, `EncodeTypes.Planet` para um código de barras Planet). Após configurar o gerador, você chama `Save` para gravar o arquivo de imagem.

![Create postal barcode image example](/images/postal_barcode_example.png)

*Alt text: Exemplo de criação de imagem de código de barras postal mostrando barras preenchidas e vazias.*

## Etapa 1: Configurar a pasta de saída

Primeiro defina uma pasta onde os arquivos PNG serão salvos. Usar um caminho absoluto ou relativo funciona da mesma forma; apenas garanta que a pasta exista ou deixe o código criá‑la.

```csharp
using System.IO;
using Aspose.BarCode.Generation;

// Define the output folder (change to your own path)
string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

Criar a pasta programaticamente evita `DirectoryNotFoundException` quando o tutorial é executado em uma máquina nova.

## Etapa 2: Gerar código de barras planet com barras preenchidas

Um código de barras Planet de barra preenchida é o estilo visual padrão. O código a seguir cria o código de barras, define a X‑dimension para 4 pixels (um tamanho comum para aplicações postais) e salva a imagem.

```csharp
// Step 2: Generate a Planet barcode with filled bars
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG
string planetFilledPath = Path.Combine(outputFolder, "PostalPlanetFilledBars.png");
planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
```

**Por que isso funciona:**  
* `EncodeTypes.Planet` indica ao gerador que use a simbologia Planet, que é exigida por muitos serviços postais.  
* `XDimension.Pixels` controla a largura de cada barra; 4 px produz uma imagem clara e escaneável sem tamanho de arquivo excessivo.  
* O método `Save` seleciona automaticamente o codificador PNG com base no enum `BarCodeImageFormat`.

## Etapa 3: Gerar código de barras planet com barras vazias

Algumas especificações postais preferem barras vazias (brancas) sobre um fundo escuro. Você pode conseguir isso definindo `FilledBars` como `false`.

```csharp
// Step 3: Generate a Planet barcode with empty bars
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for consistency
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars – the bars become transparent (empty)
planetEmpty.Parameters.Barcode.FilledBars = false;

// Save the result
string planetEmptyPath = Path.Combine(outputFolder, "PostalPlanetEmptyBars.png");
planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
```

**Dica:** Quando `FilledBars` está `false`, o gerador pinta as barras na cor de fundo (branco por padrão) e os espaços na cor de primeiro plano (preto). Se precisar de um esquema de cores diferente, ajuste `Parameters.Barcode.ForeColor` e `BackColor`.

## Etapa 4: Gerar código de barras RM4SCC com barras preenchidas

RM4SCC é outra simbologia postal usada no Reino Unido. As etapas de criação espelham o exemplo Planet; apenas o valor `EncodeTypes` muda.

```csharp
// Step 4: Generate an RM4SCC barcode with filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Reuse the same X‑dimension for a uniform look
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save the PNG file
string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png");
rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
```

**O que esperar:** O PNG resultante exibe um código de barras RM4SCC compacto que cumpre as diretrizes postais do Reino Unido. O tamanho da imagem será semelhante ao dos códigos de barras Planet porque a X‑dimension é idêntica.

## Etapa 5: Verificar as imagens geradas

Depois de executar o programa, abra os quatro arquivos na pasta `Barcodes`. Você deverá ver:

* `PostalPlanetFilledBars.png` – barras escuras sobre fundo claro  
* `PostalPlanetEmptyBars.png` – barras claras sobre fundo escuro (inverso)  
* `PostalRM4SCCFilledBars.png` – padrão padrão RM4SCC  

Se alguma imagem parecer distorcida, verifique o seguinte:

* **X‑dimension** – muito pequena (< 2 px) pode causar borrão; muito grande (> 10 px) pode exceder os limites de tamanho da etiqueta.  
* **Data string** – o valor `"123456"` deve atender aos requisitos de comprimento da simbologia escolhida (Planet espera 6 dígitos, RM4SCC também espera 6 dígitos).  
* **Folder permissions** – garanta que a aplicação tenha acesso de gravação ao diretório de saída.

## Variações comuns e casos de borda

| Scenario | Adjustment |
|----------|------------|
| **Different barcode data** | Substitua `"123456"` por qualquer string numérica válida. Para Planet, o comprimento deve ser exatamente 6 dígitos; RM4SCC também requer 6 dígitos. |
| **Custom colors** | Defina `planetFilled.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;` e `BackColor = System.Drawing.Color.LightYellow;`. |
| **Higher resolution** | Aumente `XDimension.Pixels` para 6 ou 8 para impressões maiores. |
| **Other image formats** | Use `BarCodeImageFormat.Jpeg` ou `BarCodeImageFormat.Bmp` na chamada `Save`. |
| **Batch generation** | Percorra uma coleção de strings e chame a mesma lógica do gerador dentro do loop, reutilizando o caminho `outputFolder`. |

## Exemplo completo e executável

Copie o código abaixo para um novo projeto de console C#. Ele compila com .NET 6.0 e produz automaticamente as quatro imagens de código de barras.



## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [How to create postal barcode image with custom heights in C#](/barcode/english/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/)
- [How to create RM4SCC barcode and generate planet barcode in C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [Create postal barcode image in C# – step‑by‑step guide](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}