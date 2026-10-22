---
category: general
date: 2026-10-21
description: Aprenda a criar imagens de códigos de barras postais em C# com Aspose.BarCode
  – gere códigos de barras Planet e RM4SCC, controle as barras preenchidas e salve
  arquivos PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- generate planet barcode
- how to generate barcode c#
language: pt
lastmod: 2026-10-21
og_description: Crie imagens de códigos de barras postais em C# com Aspose.BarCode.
  Este tutorial mostra como gerar códigos de barras Planet e RM4SCC, alternar barras
  preenchidas e salvar arquivos PNG.
og_image_alt: Screenshot of a generated Planet postal barcode with filled bars
og_title: Crie imagens de códigos de barras postais em C# – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to create postal barcode images in C# with Aspose.BarCode
    – generate Planet and RM4SCC barcodes, control filled bars, and save PNG files.
  headline: How to create postal barcode images in C# using Aspose.BarCode
  type: TechArticle
- description: Learn how to create postal barcode images in C# with Aspose.BarCode
    – generate Planet and RM4SCC barcodes, control filled bars, and save PNG files.
  name: How to create postal barcode images in C# using Aspose.BarCode
  steps:
  - name: 1. Prepare the output folder
    text: The barcode images need a writable directory. The code creates the folder
      if it does not exist, preventing a runtime `DirectoryNotFoundException`.
  - name: 2. Generate a Planet barcode with filled bars
    text: Planet barcodes are used by many postal services for domestic mail. The
      default `FilledBars` setting renders solid bars, which is the most common visual
      style.
  - name: 3. Generate a Planet barcode with empty bars
    text: Some postal specifications require **empty** (hollow) bars. You can toggle
      this behavior via the `FilledBars` property.
  - name: 4. Generate an RM4SCC barcode with filled bars
    text: RM4SCC (Royal Mail 4‑State Customer Code) is the UK postal barcode. Like
      Planet, the default appearance uses solid bars.
  - name: Full source code in one block
    text: Copy the following snippet into a new C# console project. It compiles with
      .NET 6.0 and produces three PNG files in the `Barcodes` subfolder.
  - name: Next steps
    text: '* **Generate other postal barcodes** – try `EncodeTypes.Postnet` or `EncodeTypes.USPSIntelligentMail`.
      * **Customize appearance** – experiment with `BarHeight`, `ForeColor`, and `BackColor`
      to match your branding. * **Integrate into a web service** – expose the generation
      logic via ASP.NET Core endp'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Como criar imagens de código de barras postal em C# usando Aspose.BarCode
url: /pt/python-java/general/how-to-create-postal-barcode-images-in-c-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar imagens de código de barras postal em C# usando Aspose.BarCode

Se você precisa **criar imagens de código de barras postal** em um projeto .NET, este guia mostra uma solução completa, pronta‑para‑executar. Você verá como gerar códigos de barras Planet e RM4SCC, alternar entre barras preenchidas e vazias, e armazenar os resultados como arquivos PNG — tudo com algumas linhas de código C#.

Gerar códigos de barras postais confiáveis é essencial para automação de correspondência, impressão em massa de etiquetas e integração com plataformas logísticas. Ao final deste tutorial você terá um trecho de código reutilizável que pode ser copiado para qualquer aplicação console ou web em C#.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou posterior instalado  
* Visual Studio 2022 (ou qualquer IDE que suporte .NET)  
* Um pacote NuGet **Aspose.BarCode** ativo (`Install-Package Aspose.BarCode`)  

Essas ferramentas são suficientes para compilar e executar o exemplo sem dependências adicionais.

## Guia passo a passo para **criar código de barras postal** imagens

O processo consiste em quatro etapas lógicas:

1. Preparar a pasta de saída.  
2. Gerar um código de barras Planet com barras preenchidas (aparência padrão).  
3. Gerar um código de barras Planet com barras vazias.  
4. Gerar um código de barras RM4SCC com barras preenchidas.

Cada etapa é explicada abaixo, e o código‑fonte completo aparece após as explicações.

### 1. Preparar a pasta de saída

As imagens de código de barras precisam de um diretório gravável. O código cria a pasta caso ela não exista, evitando uma `DirectoryNotFoundException` em tempo de execução.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Define the output folder (adjust the path to your environment)
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

        // Ensure the folder exists
        Directory.CreateDirectory(outputFolder);
```

*Por que isso importa*: Um diretório ausente interrompe o programa antes que qualquer código de barras seja gerado. Usar `Directory.CreateDirectory` é seguro porque não faz nada se a pasta já existir.

### 2. Gerar um código de barras Planet com barras preenchidas

Códigos de barras Planet são usados por muitos serviços postais para correspondência doméstica. A configuração padrão `FilledBars` renderiza barras sólidas, que é o estilo visual mais comum.

```csharp
        // Step 2: Generate a Planet barcode with filled bars (default)
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        // XDimension controls the width of a single bar; 4 pixels works well for screen display
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
        planetFilled.Save(Path.Combine(outputFolder, "PostalPlanetFilledBars.png"),
                          BarCodeImageFormat.Png);
```

*Explicação*:  
* `EncodeTypes.Planet` indica ao Aspose.BarCode que use o padrão Planet.  
* A string de dados `"123456"` é uma carga útil Planet válida (6 caracteres numéricos).  
* `XDimension.Pixels = 4` produz uma largura de barra de 4 px, equilibrando legibilidade e tamanho do arquivo.  
* `Save` grava a imagem como PNG, um formato sem perdas adequado para processamento posterior.

### 3. Gerar um código de barras Planet com barras vazias

Algumas especificações postais exigem barras **vazias** (oclusas). Você pode alternar esse comportamento via a propriedade `FilledBars`.

```csharp
        // Step 3: Generate a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        // Setting FilledBars to false creates hollow bars
        planetEmpty.Parameters.Barcode.FilledBars = false;
        planetEmpty.Save(Path.Combine(outputFolder, "PostalPlanetEmptyBars.png"),
                         BarCodeImageFormat.Png);
```

*Dica*: Ao alternar entre barras preenchidas e vazias, mantenha o valor de `XDimension` inalterado para preservar o dimensionamento consistente entre as imagens.

### 4. Gerar um código de barras RM4SCC com barras preenchidas

RM4SCC (Royal Mail 4‑State Customer Code) é o código de barras postal do Reino Unido. Assim como o Planet, a aparência padrão usa barras sólidas.

```csharp
        // Step 4: Generate an RM4SCC barcode with filled bars (default)
        BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFilled.Save(Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png"),
                          BarCodeImageFormat.Png);
    }
}
```

*Por que RM4SCC*: O formato RM4SCC codifica uma string numérica de 6 dígitos mais um dígito verificador, tornando‑o ideal para serviços postais do Reino Unido.

### Código‑fonte completo em um bloco

Copie o trecho a seguir para um novo projeto console C#. Ele compila com .NET 6.0 e produz três arquivos PNG na subpasta `Barcodes`.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // -------------------------------------------------
        // 1. Prepare the output folder
        // -------------------------------------------------
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // -------------------------------------------------
        // 2. Planet barcode – filled bars (default)
        // -------------------------------------------------
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
        planetFilled.Save(Path.Combine(outputFolder, "PostalPlanetFilledBars.png"),
                          BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 3. Planet barcode – empty bars
        // -------------------------------------------------
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false;
        planetEmpty.Save(Path.Combine(outputFolder, "PostalPlanetEmptyBars.png"),
                         BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 4. RM4SCC barcode – filled bars (default)
        // -------------------------------------------------
        BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFilled.Save(Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png"),
                          BarCodeImageFormat.Png);

        Console.WriteLine("All barcode images have been saved to: " + outputFolder);
    }
}
```

#### Saída esperada

Ao executar o programa, uma linha de confirmação é exibida e três arquivos são criados:

* `PostalPlanetFilledBars.png` – código de barras Planet com barras sólidas  
* `PostalPlanetEmptyBars.png` – código de barras Planet com barras ocos  
* `PostalRM4SCCFilledBars.png` – código de barras RM4SCC com barras sólidas  

Cada imagem tem 4 px por barra, adequada para visualização em tela ou incorporação em PDF pronto para impressão.

## Perguntas frequentes e tratamento de casos limites

| Pergunta | Resposta |
|----------|----------|
| **E se a string de dados for inválida?** | Aspose.BarCode lança `ArgumentException`. Valide o comprimento da entrada (Planet = 6 numéricos, RM4SCC = 6 numéricos) antes de criar o gerador. |
| **Posso mudar o formato da imagem?** | Sim. Substitua `BarCodeImageFormat.Png` por `Jpeg`, `Gif`, `Bmp` ou `Tiff`, conforme necessário. |
| **Como ajusto a altura da barra?** | Use `planetFilled.Parameters.Barcode.BarHeight` (o padrão é 50 px). |
| **É seguro usar este código em uma API web?** | Absolutamente. O gerador é thread‑safe para operações somente leitura, mas instancie um novo `BarcodeGenerator` por requisição para evitar estado compartilhado. |
| **E quanto a outros padrões postais?** | Aspose.BarCode também suporta `EncodeTypes.Postnet`, `EncodeTypes.USPSIntelligentMail`, etc. O mesmo padrão se aplica — basta mudar o valor de `EncodeTypes`. |

## Conclusão

Agora você sabe como **criar imagens de código de barras postal** em C# com Aspose.BarCode, cobrindo os formatos Planet e RM4SCC e demonstrando como alternar entre barras preenchidas e vazias. O exemplo completo e executável pode ser inserido em qualquer projeto .NET, proporcionando saída visual imediata.

### Próximos passos

* **Gerar outros códigos de barras postais** – experimente `EncodeTypes.Postnet` ou `EncodeTypes.USPSIntelligentMail`.  
* **Personalizar a aparência** – experimente `BarHeight`, `ForeColor` e `BackColor` para combinar com sua identidade visual.  
* **Integrar a um serviço web** – exponha a lógica de geração via endpoints ASP.NET Core para criação de códigos de barras sob demanda.  

Ao dominar essas técnicas, você poderá **gerar imagens de código de barras planet** e responder a consultas como “**como gerar código de barras C#**” com confiança, seja construindo uma ferramenta de correspondência desktop ou uma API de envio baseada na nuvem. Feliz codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que expandem as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [How to create planet barcode with filled and empty bars](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [How to create RM4SCC barcode and generate planet barcode in C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}