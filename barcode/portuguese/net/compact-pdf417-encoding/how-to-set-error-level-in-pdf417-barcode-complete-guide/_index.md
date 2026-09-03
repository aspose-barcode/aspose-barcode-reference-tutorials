---
category: general
date: 2026-07-18
description: como definir o nível de erro no código de barras PDF417 usando Aspose.BarCode.
  Aprenda a gerar código de barras PDF417 com texto personalizado e ajustar a correção
  de erros em minutos.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set error
- generate pdf417 barcode
- how to generate pdf417
- barcode with custom text
language: pt
lastmod: 2026-07-18
og_description: Como definir rapidamente o nível de erro em um código de barras PDF417.
  Este tutorial orienta você a gerar um código de barras PDF417 com texto personalizado
  e diferentes níveis de correção de erro.
og_image_alt: how to set error level in PDF417 barcode example
og_title: Como definir o nível de erro no código de barras PDF417 – Guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  headline: How to Set Error Level in PDF417 Barcode – Complete Guide
  type: TechArticle
- description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  name: How to Set Error Level in PDF417 Barcode – Complete Guide
  steps:
  - name: What if my text contains line breaks?
    text: 'PDF417 automatically encodes line‑feed (`

      `) characters. Just include them in the string:'
  - name: Can I use a different image format?
    text: Absolutely. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Svg`
      depending on your downstream workflow.
  - name: Does changing the X‑dimension affect error correction?
    text: Indirectly, yes. A larger X‑dimension yields bigger modules, which can improve
      scanning reliability but does **not** alter the logical error‑correction level.
      Adjust both parameters independently for best results.
  - name: How to generate PDF417 barcode in a web API?
    text: Wrap the same code in an ASP.NET Core controller and stream the PNG back
      as a `FileResult`. The core logic stays unchanged, which means **how to generate
      PDF417** remains consistent across desktop and web environments.
  type: HowTo
tags:
- PDF417
- barcode
- error correction
title: Como Definir o Nível de Erro no Código de Barras PDF417 – Guia Completo
url: /pt/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Definir o Nível de Erro no Código de Barras PDF417 – Guia Completo

Já se perguntou **como definir erro** ao gerar um código de barras PDF417? Você não está sozinho — a maioria dos desenvolvedores encontra esse obstáculo quando precisa de um código de barras mais robusto para leitura em ambientes adversos. A boa notícia? Ajustar o nível de correção de erro é muito fácil com Aspose.BarCode, e você também aprenderá **como gerar PDF417** com seu próprio texto personalizado enquanto isso.

Neste tutorial, percorreremos cada passo, desde a criação de um gerador de código de barras com caracteres especiais até a gravação de dois arquivos PNG que demonstram diferentes níveis de correção de erro. Ao final, você estará confortável com **gerar código de barras PDF417**, ajustar sua dimensão X, contagem de colunas e, mais importante, **definir erro** nos níveis que atendam ao seu caso de uso.

## Pré‑requisitos

- .NET 6.0 ou superior (o código também funciona com .NET Framework)
- Aspose.BarCode para .NET instalado (`Install-Package Aspose.BarCode` via NuGet)
- Uma pasta no disco onde as imagens possam ser gravadas (substitua `YOUR_DIRECTORY/` no exemplo)
- Conhecimento básico de C# — se você já escreveu um `Console.WriteLine`, está pronto para prosseguir

> **Dica de especialista:** Se você está mirando em leitura móvel, opte por um nível de erro mais alto (Nível 5) para sobreviver a sujeira, arranhões ou condições de baixa iluminação.

## Etapa 1: Criar um Gerador de Código de Barras com Texto Personalizado

A primeira coisa que você precisa é uma instância de `BarcodeGenerator` que saiba que deve produzir um **código de barras PDF417** e que carregue o texto exato que você deseja codificar. Observe o uso de caracteres acentuados e o símbolo de copyright — isso comprova que o gerador pode lidar com Unicode nativamente.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

*Por que isso importa:* O sinalizador `EncodeTypes.Pdf417` informa ao Aspose que você está lidando com um código de barras 2‑D empilhado, enquanto o argumento string se torna a carga de dados. Se você pular esta etapa, acabará com um código de barras Code128 padrão em vez do PDF417 de alta capacidade que você precisa.

## Etapa 2: Ajustar Parâmetros Visuais

Um código de barras PDF417 não é apenas dados; é também um padrão visual. Ajustar a **dimensão X** (a largura da barra mais fina) e o número de **colunas** permite controlar o tamanho físico e a legibilidade do código.

```csharp
// Step 2: Adjust visual parameters – set the X‑dimension and number of columns
generator.Parameters.Barcode.XDimension.Pixels = 2;   // each module is 2 pixels wide
generator.Parameters.Barcode.Pdf417.Columns = 3;    // three columns across the page
```

*Por que isso importa:* Uma dimensão X menor gera uma imagem mais compacta, mas pode ficar ilegível em scanners de baixa resolução. Três colunas proporcionam uma proporção equilibrada para a maioria dos tamanhos de etiqueta.

## Etapa 3: Definir Nível de Correção de Erro para 2 e Salvar

A correção de erro é o coração de **como definir erro** para PDF417. O enum `Pdf417ErrorLevel` varia de `Level0` (sem dados extras) até `Level5` (máxima redundância). Aqui começamos com **Nível 2**, que adiciona uma quantidade moderada de resiliência sem inflar demais a imagem.

```csharp
// Define the output folder (replace with your actual path)
string outputFolder = "YOUR_DIRECTORY/";

// Step 3: Set error correction level to 2 and save the image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level2;
generator.Save($"{outputFolder}Pdf417ErrorLevel2.png", BarCodeImageFormat.Png);
```

Depois de executar este trecho, você encontrará `Pdf417ErrorLevel2.png` na sua pasta. Abra-o e você verá um código de barras de três colunas limpo que ainda contém uma quantidade razoável de redundância.

## Etapa 4: Aumentar a Correção de Erro para o Nível 5 e Salvar Novamente

Às vezes, você precisa que o código de barras sobreviva a danos mais agressivos — pense em um piso de armazém onde as etiquetas são riscadas. Trocar para **Nível 5** maximiza a correção de erro ao custo de uma imagem ligeiramente maior.

```csharp
// Step 4: Change error correction level to 5 and save the second image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level5;
generator.Save($"{outputFolder}Pdf417ErrorLevel5.png", BarCodeImageFormat.Png);
```

Agora você tem dois arquivos PNG lado a lado: um com correção de erro moderada, outro com o máximo. Compare-os; a versão de Nível 5 terá mais módulos escuros, que é exatamente o que o algoritmo adiciona para proteger os dados.

![exemplo de como definir nível de erro em código de barras PDF417](image.png)

*Descrição da imagem (texto alternativo): exemplo de como definir nível de erro em código de barras PDF417 – mostra dois arquivos PNG com diferentes níveis de correção de erro.*

## Saída Esperada

| Nome do arquivo                | Nível de erro | Dimensões aproximadas (px) |
|--------------------------------|---------------|----------------------------|
| `Pdf417ErrorLevel2.png`        | Nível 2       | 150 × 80                   |
| `Pdf417ErrorLevel5.png`        | Nível 5       | 180 × 95                   |

Ambas as imagens codificam a string **“Åspóse.Barcóde©”** e podem ser lidas com qualquer leitor padrão de PDF417 (por exemplo, ZXing, Scandit). A imagem de Nível 5 tolera até ~30 % de dano, enquanto a de Nível 2 tolera cerca de ~15 %.

## Perguntas Frequentes & Casos de Borda

### E se meu texto contiver quebras de linha?
PDF417 codifica automaticamente caracteres de avanço de linha (`\n`). Basta incluí‑los na string:

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "Line1\nLine2\nLine3");
```

### Posso usar um formato de imagem diferente?
Com certeza. Substitua `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` ou `Svg` conforme o fluxo de trabalho downstream.

### Alterar a dimensão X afeta a correção de erro?
Indiretamente, sim. Uma dimensão X maior gera módulos maiores, o que pode melhorar a confiabilidade da leitura, mas **não** altera o nível lógico de correção de erro. Ajuste ambos os parâmetros independentemente para obter os melhores resultados.

### Como gerar código de barras PDF417 em uma API web?
Envolva o mesmo código em um controlador ASP.NET Core e envie o PNG como um `FileResult`. A lógica central permanece inalterada, o que significa que **como gerar PDF417** permanece consistente entre ambientes desktop e web.

## Recapitulação

Cobremos **como definir erro** para um código de barras PDF417, demonstramos **como gerar PDF417** com texto Unicode personalizado e mostramos como ajustar configurações visuais como dimensão X e contagem de colunas. Ao trocar `Pdf417ErrorLevel.Level2` por `Level5` você controla o trade‑off entre tamanho da imagem e resiliência.

## Próximos Passos

- Experimente **código de barras com texto personalizado** que inclua URLs ou IDs de produto.
- Teste diferentes contagens de colunas (`generator.Parameters.Barcode.Pdf417.Columns = 5`) para ver como a forma muda.
- Combine PDF417 com outros tipos de código de barras no mesmo documento para soluções de leitura multimodal.
- Mergulhe na [documentação oficial da Aspose](https://docs.aspose.com/barcode/net/) para recursos avançados como macro PDF417 ou modo compacto.

Sinta‑se à vontade para deixar um comentário se encontrar algum obstáculo, ou compartilhar seus próprios resultados escaneados. Feliz criação de códigos de barras!

## O Que Você Deve Aprender a Seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como Criar Código de Barras – PDF417 Compacto com Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Como criar código de barras Aztec com correção de erro em .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)
- [Como Gerar Códigos de Barras DataMatrix (ECC 200) com Aspose.BarCode para .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}