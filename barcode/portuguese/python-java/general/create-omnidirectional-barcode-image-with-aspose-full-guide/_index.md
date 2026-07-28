---
category: general
date: 2026-07-27
description: Crie imagem de código de barras omnidirecional usando Aspose.BarCode.
  Aprenda como gerar código de barras com Aspose, ajustar a proporção da imagem e
  salvar arquivos PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional barcode image
- generate barcode with aspose
language: pt
lastmod: 2026-07-27
og_description: Crie imagem de código de barras omnidirecional usando Aspose. Siga
  este guia para gerar código de barras com Aspose, ajustar proporções e exportar
  PNGs.
og_image_alt: Screenshot of two omnidirectional barcode images with different aspect
  ratios
og_title: Crie Imagem de Código de Barras Omnidirecional com Aspose – Passo a Passo
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  headline: Create Omnidirectional Barcode Image with Aspose – Full Guide
  type: TechArticle
- description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  name: Create Omnidirectional Barcode Image with Aspose – Full Guide
  steps:
  - name: 1. Different Image Formats
    text: 'Aspose supports BMP, JPEG, TIFF, and SVG in addition to PNG. Swap the enum
      value:'
  - name: 2. Customizing Colors
    text: 'You might need a white barcode on a dark background. Set `ForeColor` and
      `BackColor`:'
  - name: 3. Handling Invalid Aspect Ratios
    text: 'Aspose validates the range (usually 5‑50). If you pass an out‑of‑range
      value, an `ArgumentException` is thrown. Wrap the save call in a try‑catch to
      give a friendly message:'
  - name: 4. Batch Generation
    text: When you have a list of GTINs, loop over them, update `CodeText`, and save
      each file with a unique name. The generator object can be reused, keeping memory
      usage low.
  type: HowTo
tags:
- barcode
- Aspose
- C#
- image-generation
title: Criar imagem de código de barras omnidirecional com Aspose – Guia completo
url: /pt/python-java/general/create-omnidirectional-barcode-image-with-aspose-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Imagem de Código de Barras Omnidirecional com Aspose – Guia Completo

Já precisou **criar imagem de código de barras omnidirecional** mas não tinha certeza de qual biblioteca escolher? Você não está sozinho. Em muitos projetos de logística e varejo, o formato DataBar Stacked Omnidirectional é o ingrediente secreto para codificação compacta e de alta densidade.

A boa notícia? Com **Aspose.BarCode** você pode gerar esse código de barras em poucas linhas, ajustar sua proporção e gravar o PNG diretamente no disco. A seguir, você verá exatamente como **gerar código de barras com Aspose**, por que cada configuração importa e o que observar ao mudar a proporção.

---

## O que este tutorial cobre

Vamos percorrer todo o ciclo de vida:

1. Configurar a pasta de saída.
2. Instanciar um gerador DataBar Stacked Omnidirectional.
3. Configurar dimensões de pixels e proporções.
4. Salvar o código de barras como arquivos PNG.
5. Estender o exemplo para outros formatos e casos de borda.

Ao final, você terá um aplicativo de console C# pronto‑para‑executar que gera duas imagens de código de barras distintas. Sem ferramentas externas, apenas código puro da Aspose.

**Pré-requisitos**

- .NET 6.0 SDK ou posterior (o código também funciona no .NET Framework 4.7.2).
- Pacote NuGet Aspose.BarCode para .NET (`Install-Package Aspose.BarCode`).
- Uma pasta no disco onde as imagens podem ser gravadas.

Se você já tem isso, vamos mergulhar.

---

## Etapa 1: Preparar a Pasta de Saída

Primeiro, diga ao programa onde gravar os arquivos PNG. Codificar um caminho fixo funciona para uma demonstração, mas em produção você provavelmente lerá isso de uma configuração.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Define the folder where the images will be saved
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);   // ensures the folder exists
```

*Por que isso importa:* `Directory.CreateDirectory` é idempotente; não lançará exceção se a pasta já existir, poupando você de um bloco try‑catch.

---

## Etapa 2: Criar um Gerador DataBar Stacked Omnidirectional

Agora inicializamos o gerador com o tipo de codificação específico e dados de exemplo. A string `"(01)12345678901231"` segue a sintaxe do Identificador de Aplicação GS1 para um GTIN de 14 dígitos.

```csharp
        // Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

*Explicação:* `EncodeTypes.DatabarStackedOmniDirectional` indica à Aspose para usar a variante omnidirecional, que pode ser lida de qualquer direção — perfeito para rótulos pequenos que podem ser girados.

---

## Etapa 3: Definir Parâmetros Comuns do Código de Barras

Antes de renderizar qualquer coisa, definimos o menor tamanho de elemento (X‑Dimension). Um valor de **2 pixels** produz uma imagem nítida sem inflar o tamanho do arquivo.

```csharp
        // Step 3: Set common barcode parameters (pixel size of the smallest element)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Dica:* Se precisar de resolução maior para impressão, aumente para 3 ou 4. Apenas lembre-se de que X‑Dimensions maiores aumentam largura e altura proporcionalmente.

---

## Etapa 4: Gerar e Salvar com Proporção 15

A família DataBar permite ajustar a **proporção**, que controla a relação altura‑largura. Uma proporção de **15** é um padrão comum para códigos de barras omnidirecionais.

```csharp
        // Step 4: Generate a barcode with an aspect ratio of 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
```

*O que você verá:* Um código de barras relativamente alto que ainda cabe confortavelmente em um rótulo de 2 × 1 cm. O formato PNG preserva qualidade sem perdas, ideal para processamento adicional ou impressão.

---

## Etapa 5: Alterar a Proporção para 30 e Salvar Novamente

Quer um código de barras mais achatado? Basta ajustar a propriedade `AspectRatio` e chamar `Save` novamente. Não há necessidade de recriar o gerador.

```csharp
        // Step 5: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
    }
}
```

*Por que reutilizar o mesmo gerador?* Os objetos Aspose são leves; mudar uma propriedade e salvar novamente é mais rápido do que construir uma nova instância, e garante que as mesmas configurações de codificação (por exemplo, X‑Dimension) permaneçam consistentes.

---

## Exemplo Completo em Funcionamento

Juntando tudo, aqui está o programa completo e autônomo que você pode copiar e colar em um novo projeto de console.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Initialize generator with omnidirectional DataBar
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Common settings
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // First image – aspect ratio 15
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio15.png");

        // Second image – aspect ratio 30
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio30.png");
    }
}
```

**Saída esperada**

Executar o programa cria uma sub‑pasta `Barcodes` contendo:

- `DatabarAspectRatio15.png` – aparência mais alta, clássica.
- `DatabarAspectRatio30.png` – mais achatada, melhor para rótulos largos.

Ambas as imagens renderizam o mesmo dado GTIN; apenas as proporções visuais diferem.

---

## Estendendo o Exemplo (Casos de Borda & Variações)

### 1. Diferentes Formatos de Imagem

Aspose suporta BMP, JPEG, TIFF e SVG além de PNG. Troque o valor do enum:

```csharp
barcodeGenerator.Save(Path.Combine(outputFolder, "Databar.svg"),
                      BarCodeImageFormat.Svg);
```

SVG é baseado em vetor, o que significa que você pode escalá-lo sem perder nitidez — útil para aplicativos web responsivos.

### 2. Personalizando Cores

Você pode precisar de um código de barras branco sobre fundo escuro. Defina `ForeColor` e `BackColor`:

```csharp
barcodeGenerator.Parameters.Barcode.ForeColor = System.Drawing.Color.White;
barcodeGenerator.Parameters.Barcode.BackColor = System.Drawing.Color.Black;
```

### 3. Lidando com Proporções Inválidas

Aspose valida o intervalo (geralmente 5‑50). Se você passar um valor fora do intervalo, uma `ArgumentException` é lançada. Envolva a chamada de salvar em um try‑catch para fornecer uma mensagem amigável:

```csharp
try
{
    barcodeGenerator.Save(...);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid aspect ratio: {ex.Message}");
}
```

### 4. Geração em Lote

Quando você tem uma lista de GTINs, itere sobre eles, atualize `CodeText` e salve cada arquivo com um nome único. O objeto gerador pode ser reutilizado, mantendo o uso de memória baixo.

---

## Armadilhas Comuns & Dicas Profissionais

- **Nunca esqueça de definir `XDimension`** antes de salvar; o padrão (0,33 mm) pode gerar imagens borradas em telas de baixa resolução.
- **A proporção é altura‑largura**, não o contrário. Um número maior torna o código de barras *mais curto* verticalmente.
- **Caminhos de arquivo:** Use `Path.Combine` para evitar problemas com separadores específicos da plataforma — especialmente se seu código for executado em contêineres Linux.
- **Licenciamento:** Aspose.BarCode é comercial. No modo de avaliação, uma marca d'água aparece na imagem. Registre uma licença cedo para evitar surpresas na produção.

---

## Conclusão

Agora você sabe como **criar imagem de código de barras omnidirecional** usando Aspose, ajustar a proporção e exportar arquivos PNG — tudo em menos de 30 linhas de C#. Este tutorial mostrou o processo passo a passo, explicou por que cada configuração importa e abordou extensões como formatos diferentes, cores e processamento em lote.

Pronto para o próximo desafio? Tente gerar códigos QR, incorporar o código de barras em um PDF ou integrar a saída em uma API ASP.NET Core. Os mesmos princípios de **gerar código de barras com Aspose** se aplicam a todos os tipos de códigos de barras, então você pode reutilizar o que aprendeu hoje.

Tem perguntas ou quer compartilhar suas próprias adaptações? Deixe um comentário abaixo — feliz codificação!

## O que Você Deve Aprender a Seguir?

Os tutoriais a seguir cobrem tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar código de barras Aztec com proporção personalizada usando Aspose.BarCode para .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Como Criar Código de Barras Aspose Java - Ajustar Qualidade da Imagem](/barcode/english/java/image-manipulation/adjusting-image-quality-barcode/)
- [Como Gerar Imagem de Código de Barras em Java com Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}