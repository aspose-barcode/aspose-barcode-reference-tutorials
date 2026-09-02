---
category: general
date: 2026-07-18
description: Crie um código de barras PDF417 em C# usando o gerador de código de barras
  PDF417 para C#. Siga um tutorial passo a passo para construir o texto de código
  estendido, definir a aparência e salvar a imagem.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- c# pdf417 barcode generator
language: pt
lastmod: 2026-07-18
og_description: Crie código de barras PDF417 em C# instantaneamente. Este guia mostra
  como usar o gerador de código de barras PDF417 em C#, configurar o modo estendido
  e exportar um PNG.
og_image_alt: Generated PDF417 barcode image created with C# PDF417 barcode generator
og_title: Criar código de barras PDF417 em C# – Tutorial completo do gerador
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  headline: Create PDF417 Barcode in C# – Barcode Generator Guide
  type: TechArticle
- description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  name: Create PDF417 Barcode in C# – Barcode Generator Guide
  steps:
  - name: 1. Install the barcode library
    text: 'Open your terminal in the project folder and run:'
  - name: 2. Build the extended codetext
    text: 'PDF417 supports **extended encoding**, allowing you to mix different character
      sets in a single barcode. Below we create three segments:'
  - name: 3. Initialise the **C# PDF417 barcode generator**
    text: Now that we have a valid codetext string, we hand it to the generator. The
      `using` statement ensures the underlying resources are released automatically.
  - name: 4. Configure appearance and encoding mode
    text: 'The default settings give you a tiny barcode that might be hard to read.
      Let’s tweak a few parameters:'
  - name: 5. Save the barcode image
    text: Finally, write the image to disk. The library supports PNG, JPEG, BMP, and
      several vector formats—PNG is a safe default because it preserves crisp edges.
  - name: Handling Unicode and special characters
    text: When you feed Unicode symbols directly into a plain‑text barcode, the generator
      may fall back to a fallback encoding, resulting in garbled output. By using
      `AddECICodetext` you explicitly tell the encoder which character set to apply,
      eliminating guesswork. If you ever need to support **Arabic**, **
  - name: Adjusting error correction level
    text: 'PDF417 offers four error‑correction levels (0‑8). Higher levels increase
      resilience but also enlarge the barcode. Adjust it via:'
  - name: Scaling for print vs. screen
    text: 'For on‑screen display you might keep the default 96 dpi. For high‑resolution
      printing (300 dpi or more), set:'
  - name: Common pitfalls
    text: '- **Missing `using` directive** – Forgetting `using Aspose.BarCode.Encoding;`
      will cause `ECIEncodings` to be undefined. - **Directory not found** – The `Save`
      method won’t create intermediate folders; create them beforehand or use `Path.Combine`
      with `Environment.CurrentDirectory`. - **Wrong encode'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Criar código de barras PDF417 em C# – Guia do Gerador de Código de Barras
url: /pt/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-barcode-generator-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Código de Barras PDF417 em C# – Guia do Gerador de Código de Barras

Já precisou **criar código de barras PDF417** em uma aplicação C# mas não sabia por onde começar? Você não está sozinho—muitos desenvolvedores encontram o mesmo obstáculo ao lidar pela primeira vez com códigos de barras bidimensionais. A boa notícia? Com o **gerador de código de barras PDF417 para C#** embutido, você pode gerar um código de barras completo em apenas algumas linhas.

Neste tutorial, percorreremos todo o processo: construir um codetext estendido que mistura diferentes conjuntos de caracteres, configurar o gerador para o estilo visual adequado e, finalmente, salvar o código de barras como um arquivo PNG. Ao final, você terá um trecho pronto para uso que pode ser inserido em qualquer projeto .NET, além de dicas para lidar com casos extremos como caracteres Unicode ou larguras de módulo personalizadas.

---

## O que você precisará

Antes de mergulharmos, certifique‑se de que tem o seguinte na sua máquina:

- **.NET 6.0** ou superior (o exemplo também funciona com .NET Framework 4.6+)
- **Aspose.BarCode for .NET** (ou qualquer biblioteca compatível que exponha `BarcodeGenerator`, `EncodeTypes.Pdf417`, etc.)
- Um editor de código—Visual Studio, Rider ou até mesmo VS Code serve
- Uma pasta onde você possa gravar, pois o gerador salvará o PNG lá

É isso—nenhum pacote NuGet extra além da própria biblioteca de código de barras.

---

## Guia passo a passo para **criar código de barras PDF417**

### 1. Instalar a biblioteca de código de barras

Abra seu terminal na pasta do projeto e execute:

```bash
dotnet add package Aspose.BarCode
```

O pacote adiciona o namespace `Aspose.BarCode`, que contém a classe `BarcodeGenerator` que usaremos ao longo do tutorial.

### 2. Construir o codetext estendido

O PDF417 suporta **codificação estendida**, permitindo misturar diferentes conjuntos de caracteres em um único código de barras. A seguir, criamos três segmentos:

- Um segmento Windows‑1251 (Cirílico)
- Um segmento UTF‑8 contendo caracteres Unicode (os kanjis japoneses para “cachorro” e “direita”)
- Um segmento de texto simples

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

// Step 1: Build the extended codetext for the PDF417 barcode
Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();

// Add a Win1251‑encoded segment
builder.AddECICodetext(ECIEncodings.Win1251, "Will");

// Add a UTF‑8 segment with Unicode characters
builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");

// Add a plain‑text segment
builder.AddPlainCodetext("Plain text");

// Retrieve the combined codetext string
string extendedCodetext = builder.GetExtendedCodetext();
```

**Por que isso importa:**  
Se você usar apenas texto simples, ficará limitado ao subconjunto ASCII padrão. Ao declarar explicitamente segmentos ECI (Extended Channel Interpretation), você garante que os leitores interpretem cada parte corretamente, independentemente do idioma ou dos símbolos envolvidos.

### 3. Inicializar o **gerador de código de barras PDF417 para C#**

Agora que temos uma string de codetext válida, a passamos para o gerador. A instrução `using` garante que os recursos subjacentes sejam liberados automaticamente.

```csharp
// Step 2: Create a PDF417 barcode generator using the extended codetext
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
{
    // Configuration goes here (see next step)
}
```

### 4. Configurar aparência e modo de codificação

As configurações padrão geram um código de barras pequeno que pode ser difícil de ler. Vamos ajustar alguns parâmetros:

- **X‑Dimension** – controla a largura de cada módulo (tamanho em pixels)
- **EncodeMode** – indica ao motor que a entrada deve ser tratada como modo estendido
- **TwoDDisplayText** – texto legível opcional exibido abaixo do código de barras

```csharp
    // Step 3: Configure barcode appearance and encoding mode
    generator.Parameters.Barcode.XDimension.Pixels = 15; // Wider modules for better scannability
    generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended; // Activate extended encoding
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode"; // Display text under the symbol
```

**Dica profissional:** Se você estiver imprimindo o código de barras em uma impressora de etiquetas, aumente o `XDimension` para 20 px ou mais; a maioria dos leitores aprecia um pouco de espaço extra.

### 5. Salvar a imagem do código de barras

Por fim, grave a imagem no disco. A biblioteca suporta PNG, JPEG, BMP e vários formatos vetoriais—PNG é uma escolha segura porque preserva bordas nítidas.

```csharp
    // Step 4: Save the generated barcode image
    generator.Save("YOUR_DIRECTORY/Pdf417Extended.png", BarCodeImageFormat.Png);
}
```

Certifique‑se de que `YOUR_DIRECTORY` exista e seja gravável. Após executar o programa, você deverá ver um arquivo semelhante à captura de tela abaixo.

![Generated PDF417 barcode created with C# PDF417 barcode generator](https://example.com/images/pdf417-extended.png "Generated PDF417 barcode created with C# PDF417 barcode generator")

---

## Usando o **gerador de código de barras PDF417 para C#** – aprofundamento

### Manipulando Unicode e caracteres especiais

Quando você insere símbolos Unicode diretamente em um código de barras de texto simples, o gerador pode recorrer a uma codificação de fallback, resultando em saída corrompida. Ao usar `AddECICodetext`, você informa explicitamente ao codificador qual conjunto de caracteres aplicar, eliminando suposições. Se precisar suportar **Árabe**, **Hebraico** ou **emoji**, basta escolher o valor apropriado de `ECIEncodings`.

### Ajustando o nível de correção de erro

O PDF417 oferece quatro níveis de correção de erro (0‑8). Níveis mais altos aumentam a resiliência, mas também ampliam o código de barras. Ajuste‑o via:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // Balanced level
```

### Dimensionamento para impressão vs. tela

Para exibição em tela, você pode manter o padrão de 96 dpi. Para impressão de alta resolução (300 dpi ou mais), defina:

```csharp
generator.Parameters.ImageResolution = 300;
```

Isso garante que o PNG salvo mantenha detalhes suficientes para impressoras a laser.

### Armadilhas comuns

- **Diretiva `using` ausente** – Esquecer `using Aspose.BarCode.Encoding;` fará com que `ECIEncodings` fique indefinido.
- **Diretório não encontrado** – O método `Save` não cria pastas intermediárias; crie‑as previamente ou use `Path.Combine` com `Environment.CurrentDirectory`.
- **Modo de codificação errado** – Se deixar `EncodeMode` em `Pdf417EncodeMode.Auto`, a biblioteca pode tratar seu codetext estendido como texto simples, removendo os marcadores ECI.

---

## Exemplo completo, pronto para executar

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

class Program
{
    static void Main()
    {
        // 1️⃣ Build extended codetext
        Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();
        builder.AddECICodetext(ECIEncodings.Win1251, "Will");
        builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
        builder.AddPlainCodetext("Plain text");
        string extendedCodetext = builder.GetExtendedCodetext();

        // 2️⃣ Initialise generator with the extended codetext
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
        {
            // 3️⃣ Configure appearance
            generator.Parameters.Barcode.XDimension.Pixels = 15;
            generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended;
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
            generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode";

            // 4️⃣ Save to PNG (ensure the folder exists)
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "Pdf417Extended.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }

        Console.WriteLine("PDF417 barcode generated successfully!");
    }
}
```

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como criar código de barras – PDF417 compacto com Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Como criar codetext estendido para dotcode com Aspose.BarCode para .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Criar imagem de código de barras c# – Configurar linhas e colunas do Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}