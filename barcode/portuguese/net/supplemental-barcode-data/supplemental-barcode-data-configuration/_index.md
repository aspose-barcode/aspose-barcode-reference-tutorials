---
date: 2026-03-07
description: Aprenda a criar códigos de barras EAN‑13 com dados suplementares em C#
  usando Aspose.BarCode para .NET – gere PNG do código de barras rapidamente.
linktitle: Supplemental Barcode Data Configuration
second_title: Aspose.BarCode .NET API
title: Criar código de barras EAN-13 com dados suplementares – Aspose.BarCode
url: /pt/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Código de Barras EAN-13 com Dados Suplementares – Aspose.BarCode para .NET

Neste tutorial prático você **criará um código de barras EAN-13** que inclui dados suplementares EAN‑2 ou EAN‑5, e verá como **gerar arquivos PNG de código de barras** com apenas algumas linhas de C#. Seja construindo um sistema de checkout de varejo, uma aplicação de logística ou uma ferramenta simples de inventário, a capacidade de adicionar informações suplementares torna seus códigos de barras muito mais úteis.

## Respostas Rápidas
- **O que significa “dados suplementares”?** Dígitos extras (EAN‑2/EAN‑5) impressos ao lado do código de barras principal, frequentemente usados para preço ou números de edição.  
- **Qual tipo de código de barras é usado?** EAN‑13 como símbolo principal, com suplementos opcionais EAN‑2 ou EAN‑5.  
- **Posso gerar imagens PNG?** Sim – o método `Save` permite exportar diretamente para PNG.  
- **Preciso de licença para desenvolvimento?** Um teste gratuito funciona para testes; uma licença comercial é necessária para produção.  
- **É compatível com .NET Core / .NET 6?** Absolutamente – Aspose.BarCode suporta todos os runtimes .NET modernos.

## Pré-requisitos

- Visual Studio (ou qualquer IDE compatível com .NET).  
- Uma cópia do Aspose.BarCode para .NET – faça o download **[aqui](https://releases.aspose.com/barcode/net/)**.  
- Conhecimento básico de C#.  
- Uma pasta gravável onde os arquivos PNG gerados serão salvos.

## Importando Namespaces

Primeiro, adicione o namespace Aspose.BarCode para que você possa acessar as classes do gerador:

```csharp
using Aspose.BarCode.Generation;
```

> **Dica:** Se você estiver usando .NET Core, adicione o pacote NuGet `Aspose.BarCode` ao seu projeto em vez de referenciar o DLL manualmente.

## O que é um Código de Barras Suplementar?

Um código de barras suplementar é uma sequência numérica auxiliar impressa ao lado do código de barras principal.  
- **EAN‑2** – suplemento de dois dígitos, frequentemente usado para números de edição em revistas.  
- **EAN‑5** – suplemento de cinco dígitos, comumente usado para extensões de preço em itens de varejo.

Adicionar esses suplementos não altera os dados primários do EAN‑13; ele simplesmente fornece contexto extra que os scanners podem ler.

## Por que usar Aspose.BarCode para Dados Suplementares?

- **API de uma linha** – configure tanto o código de barras principal quanto seu suplemento em um único objeto.  
- **Controle total sobre dimensões** – ajuste a dimensão X, espaçamento do suplemento e o formato da imagem.  
- **Multiplataforma** – funciona no .NET Framework, .NET Core e .NET 5/6+.  

## Guia Passo a Passo

### Etapa 1: Configurar o Diretório de Saída

Defina onde os arquivos PNG serão armazenados. Substitua o placeholder por um caminho real na sua máquina.

```csharp
string path = "Your Directory Path";
```

### Etapa 2: Inicializar o Gerador de Código de Barras (Barcode Generator C#)

Crie uma instância `BarcodeGenerator`, especificando **EAN‑13** como o tipo principal e fornecendo a carga útil de 13 dígitos.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

### Etapa 3: Ajustar as Dimensões do Código de Barras

Ajuste finamente o tamanho visual do código de barras e o espaço reservado para o suplemento.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

### Etapa 4: Adicionar um Suplemento EAN‑2

Defina os dados suplementares para um valor de dois dígitos (ex.: “12”). Isso aparecerá à direita do código de barras principal.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

### Etapa 5: Salvar o Código de Barras EAN‑2 como PNG

Exporte a imagem. O argumento `BarCodeImageFormat.Png` garante um arquivo PNG de alta qualidade.

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

### Etapa 6: Alternar para um Suplemento EAN‑5

Altere o `SupplementData` para uma string de cinco dígitos para extensões de preço.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

### Etapa 7: Salvar o Código de Barras EAN‑5 como PNG

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

> **Por que isso funciona:** A mesma instância `BarcodeGenerator` é reutilizada, portanto você só precisa modificar a propriedade `SupplementData` antes de cada chamada `Save`. Isso mantém o código conciso e evita a criação desnecessária de objetos.

## Problemas Comuns & Dicas

- **Caminho de diretório inválido** – certifique-se de que a pasta exista e que a aplicação tenha permissões de gravação.  
- **Comprimento do suplemento incorreto** – EAN‑2 espera exatamente 2 dígitos, EAN‑5 espera 5; caso contrário, uma exceção é lançada.  
- **Imagem não visível** – verifique se `BarCodeImageFormat.Png` está sendo usado; outros formatos (por exemplo, JPEG) podem introduzir artefatos de compressão que afetam a legibilidade pelo scanner.  

## Perguntas Frequentes

### Posso usar Aspose.BarCode para .NET no meu projeto .NET Core?
Sim, Aspose.BarCode para .NET é totalmente compatível com .NET Core, .NET 5 e .NET 6.

### Existe um teste gratuito disponível para Aspose.BarCode para .NET?
Sim, você pode experimentá‑lo gratuitamente visitando **[este link](https://releases.aspose.com/)**.

### Onde posso obter uma licença temporária para Aspose.BarCode para .NET?
Você pode obter uma licença temporária em **[este link](https://purchase.aspose.com/temporary-license/)**.

### O Aspose.BarCode suporta uma ampla variedade de tipos de código de barras?
Absolutamente – ele suporta EAN‑13, QR Code, Code 128, DataMatrix, PDF‑417 e muitos outros.

### Posso personalizar a aparência dos códigos de barras gerados?
Sim, você pode modificar cores, fontes, margens e até adicionar imagens de fundo usando a extensa API `Parameters`.

## Conclusão

Agora você sabe como **criar um código de barras EAN-13** com dados suplementares EAN‑2 ou EAN‑5 e **gerar arquivos PNG de código de barras** usando Aspose.BarCode para .NET. Essa abordagem lhe dá controle total sobre as dimensões do código de barras, o espaçamento do suplemento e o formato de saída, tornando‑a ideal para varejo, logística e qualquer cenário onde informações numéricas extras são necessárias.

Para uma exploração mais aprofundada, consulte o guia de referência completo: **[documentação do Aspose.BarCode para .NET](https://reference.aspose.com/barcode/net/)**.

---

**Última atualização:** 2026-03-07  
**Testado com:** Aspose.BarCode 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}