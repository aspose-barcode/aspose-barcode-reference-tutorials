---
category: general
date: 2026-07-30
description: Leia vários códigos de barras em C# usando Aspose.BarCode. Aprenda passo
  a passo como decodificar PDF417, detectar o modo compacto e lidar com muitos códigos
  de barras em uma única imagem.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read multiple barcodes c#
- BarCodeReader C#
- PDF417 decoding
- barcode compact mode
- C# barcode library
language: pt
lastmod: 2026-07-30
og_description: Leia vários códigos de barras em C# com Aspose.BarCode. Este guia
  mostra como decodificar todos os códigos de barras em uma imagem, verificar o modo
  compacto e integrar em aplicativos .NET.
og_image_alt: Screenshot of C# console output showing compact mode status for PDF417
  barcodes
og_title: Ler Vários Códigos de Barras C# – Tutorial Completo para PDF417
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Read multiple barcodes C# using Aspose.BarCode. Learn step‑by‑step
    how to decode PDF417, detect compact mode, and handle many barcodes in one image.
  headline: Read Multiple Barcodes C# – Complete Guide with PDF417
  type: TechArticle
- description: Read multiple barcodes C# using Aspose.BarCode. Learn step‑by‑step
    how to decode PDF417, detect compact mode, and handle many barcodes in one image.
  name: Read Multiple Barcodes C# – Complete Guide with PDF417
  steps:
  - name: Why This Code Works
    text: '- **`BarCodeReader`** is the workhorse from the **BarCodeReader C#** API.
      It opens the image, applies pre‑processing, and searches for symbols of the
      type you specify. - **`ReadBarCodes()`** returns an array, not just a single
      result. That’s the key to **reading multiple barcodes C#**—the method aut'
  - name: 1️⃣ No Barcodes Detected
    text: 'If `ReadBarCodes()` returns an empty array, the most common culprits are:'
  - name: 2️⃣ Extremely Large Images
    text: 'Processing a 10 MP photo can be memory‑hungry. You can limit the scan area:'
  - name: 3️⃣ Thread‑Safety
    text: '`BarCodeReader` implements `IDisposable` and is **not** thread‑safe. Spin
      up separate instances per thread if you need parallel processing.'
  - name: 4️⃣ Licensing
    text: 'Aspose.BarCode works in trial mode out of the box, but you’ll see a watermark
      on the output image. For production, set the license early:'
  - name: 5️⃣ Logging
    text: When you integrate this into a larger service, replace `Console.WriteLine`
      with a structured logger (Serilog, NLog). That way you can capture `CodeText`,
      `CodeType`, and `IsTruncated` as fields for downstream analytics.
  type: HowTo
tags:
- C#
- BarCode
- PDF417
- Aspose
- Barcode Decoding
title: Ler Múltiplos Códigos de Barras C# – Guia Completo com PDF417
url: /pt/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ler Vários Códigos de Barras C# – Guia Completo com PDF417

Já se perguntou como **ler vários códigos de barras C#** a partir de uma única imagem? Talvez você tenha um lote de etiquetas de envio, um collage de ingressos ou um documento PDF417 que agrupa vários códigos em uma foto. No meu dia a dia, encontrei exatamente esse obstáculo—até descobrir o `BarCodeReader` da Aspose.BarCode. Este tutorial mostrará como decodificar cada código de barras em uma imagem, identificar se cada PDF417 está em modo compacto (truncado) e tratar os resultados de forma limpa.

Também vamos acrescentar algumas dicas extras—como o que fazer quando a imagem contém diferentes simbologias de código de barras, ou quando uma varredura não retorna nenhum resultado. Ao final, você terá um aplicativo console pronto‑para‑executar que **lê vários códigos de barras C#** como um profissional.

## O que você precisará

Antes de começar, certifique‑se de que tem o seguinte instalado na sua máquina:

- **.NET 6.0** SDK ou superior (o código também funciona com .NET Framework 4.6+ , mas .NET 6 é o ponto ideal).
- **Aspose.BarCode for .NET** pacote NuGet (`Install-Package Aspose.BarCode`).
- Uma imagem de exemplo que contenha códigos de barras **PDF417**—de preferência uma que misture símbolos compactos e de tamanho completo. O tutorial usa `CompactPdf417.png`, mas qualquer PNG/JPEG serve.
- Seu IDE favorito (Visual Studio, Rider ou VS Code).  

É só isso—sem DLLs extras, sem dependências nativas. Aspose.BarCode é código totalmente gerenciado, podendo ser inserido em qualquer projeto .NET.

![Read multiple barcodes C# console output](image.png "Read multiple barcodes C# console output")

*Texto alternativo da imagem: Ler vários códigos de barras C# – captura de tela do console exibindo o status do modo compacto para códigos de barras PDF417.*

## Etapa 1 – Instalar e Referenciar a Biblioteca BarCodeReader C#

Primeiro de tudo, você precisa da classe **BarCodeReader C#** que alimenta a decodificação. Abra seu terminal (ou Package Manager Console) e execute:

```powershell
dotnet add package Aspose.BarCode
```

Ou, se estiver usando o gerenciador NuGet do Visual Studio, basta procurar por *Aspose.BarCode* e clicar em **Install**. Isso traz a versão estável mais recente (em julho 2026 é a 23.9), que suporta PDF417, QR, DataMatrix e dezenas de outras simbologias.

Por que isso importa: a biblioteca abstrai todo o trabalho pesado de processamento de imagem, correção de erros e reconhecimento de símbolos. Você poderia escrever seu próprio scanner, mas gastaria semanas lidando com casos‑limite. Aspose oferece uma **biblioteca de códigos de barras C#** testada em batalha e atualizada para runtimes .NET modernos.

## Etapa 2 – Configurar um Projeto Console Minimalista

Crie um novo aplicativo console para focarmos na lógica de código de barras sem distrações de UI:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Substitua o `Program.cs` gerado pelo exemplo completo abaixo. Sinta‑se à vontade para manter o namespace padrão ou renomeá‑lo—não há nada especial exigido.

## Etapa 3 – Escrever a Implementação Completa “Read Multiple Barcodes C#”

A seguir, um exemplo de código **completo e executável**. Ele cobre todas as quatro etapas do trecho original, adiciona tratamento de erros e imprime diagnósticos úteis.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // ---------------------------------------------------------
            // 1️⃣  Initialize the BarCodeReader for the target image.
            // ---------------------------------------------------------
            // Replace the path with your own image location.
            const string imagePath = "YOUR_DIRECTORY/CompactPdf417.png";

            // The DecodeType.Pdf417 tells the reader to look for PDF417 symbols.
            // You could pass DecodeType.AllSupported to scan every possible barcode.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
            {
                // ---------------------------------------------------------
                // 2️⃣  Iterate over every barcode found in the picture.
                // ---------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes detected – double‑check the image path and content.");
                    return;
                }

                // ---------------------------------------------------------
                // 3️⃣  Process each result: check compact mode and output data.
                // ---------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    // The Extended property gives us PDF417‑specific info.
                    bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;

                    // Display the raw text and the compact‑mode flag.
                    Console.WriteLine($"Code Text   : {result.CodeText}");
                    Console.WriteLine($"Compact mode: {isCompact}");
                    Console.WriteLine(new string('-', 30));
                }
            }

            // ---------------------------------------------------------
            // 4️⃣  Keep the console window open when debugging.
            // ---------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Por que este código funciona

- **`BarCodeReader`** é o motor da API **BarCodeReader C#**. Ele abre a imagem, aplica pré‑processamento e procura símbolos do tipo especificado.
- **`ReadBarCodes()`** devolve um array, não apenas um único resultado. Esse é o ponto chave para **ler vários códigos de barras C#**—o método coleta automaticamente cada correspondência encontrada.
- **`result.Extended.Pdf417.IsTruncated`** indica se o PDF417 está em modo *compacto* (também chamado truncado). Essa flag só existe para PDF417, por isso usamos o operador condicional nulo (`?.`) para evitar exceções caso outra simbologia apareça.
- O laço `foreach` imprime tanto o texto decodificado quanto o status de compacto, oferecendo uma verificação rápida.

## Etapa 4 – Tratando Diferentes Tipos de Código de Barras (Opcional)

Se sua imagem puder conter mais que PDF417, basta mudar o segundo argumento do `BarCodeReader` para `DecodeType.AllSupported`. O laço permanece o mesmo, mas você precisará proteger contra `result.Extended` ser nulo para símbolos que não sejam PDF417:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Symbology : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // PDF417‑specific check only when applicable.
        if (result.CodeType == DecodeType.Pdf417)
        {
            bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;
            Console.WriteLine($"Compact mode: {isCompact}");
        }

        Console.WriteLine(new string('=', 30));
    }
}
```

Essa pequena alteração transforma sua **biblioteca de códigos de barras C#** em um scanner universal, perfeito para lotes com simbologias mistas.

## Etapa 5 – Casos de Borda e Dicas de Boas Práticas

### 1️⃣ Nenhum código de barras detectado  
Se `ReadBarCodes()` retornar um array vazio, os culpados mais comuns são:

- Caminho de arquivo errado ou permissões de leitura ausentes.
- Qualidade da imagem muito baixa (desfoque, baixo contraste). Considere pré‑processar com `reader.ImagePreprocessingOptions` (ex.: `reader.ImagePreprocessingOptions.Denoise = true;`).

### 2️⃣ Imagens extremamente grandes  
Processar uma foto de 10 MP pode consumir muita memória. Você pode limitar a área de varredura:

```csharp
reader.SetRegionOfInterest(0, 0, 2000, 2000); // left, top, width, height
```

### 3️⃣ Segurança em threads  
`BarCodeReader` implementa `IDisposable` e **não** é thread‑safe. Crie instâncias separadas por thread se precisar de processamento paralelo.

### 4️⃣ Licenciamento  
Aspose.BarCode funciona em modo de avaliação por padrão, mas exibirá uma marca d'água na imagem de saída. Para produção, defina a licença logo no início:

```csharp
License license = new License();
license.SetLicense("Aspose.BarCode.lic");
```

### 5️⃣ Registro de logs  
Ao integrar isso a um serviço maior, substitua `Console.WriteLine` por um logger estruturado (Serilog, NLog). Assim você pode capturar `CodeText`, `CodeType` e `IsTruncated` como campos para análises posteriores.

## Recapitulação do Exemplo Completo

Juntando tudo, aqui está o *programa inteiro* que você pode copiar‑colar em `Program.cs`:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            const string imagePath = "YOUR_DIRECTORY


## O que você deve aprender a seguir?


Os tutoriais a seguir abordam tópicos intimamente relacionados que expandem as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}