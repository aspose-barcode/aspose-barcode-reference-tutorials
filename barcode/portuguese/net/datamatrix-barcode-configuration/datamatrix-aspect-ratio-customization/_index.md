---
date: 2026-01-12
description: Aprenda a criar PNG de código de barras com uma proporção personalizada
  de DataMatrix usando Aspose.BarCode para .NET. Guia passo a passo para geração de
  códigos de barras e personalização de tamanho.
linktitle: DataMatrix Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
title: Criar PNG de Código de Barras – Proporção do DataMatrix – Aspose.BarCode
url: /pt/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar PNG de Código de Barras – Proporção do DataMatrix – Aspose.BarCode

Gerar um **barcode PNG** com uma proporção personalizada do DataMatrix é uma necessidade comum quando você precisa que o código de barras se ajuste a restrições de layout específicas. Neste tutorial, percorreremos os passos exatos para **criar arquivos barcode PNG** usando Aspose.BarCode para .NET, explicaremos por que você pode querer ajustar a proporção e mostraremos como afinar a saída para sua aplicação.

## Respostas Rápidas
- **O que controla a “aspect ratio”?** Ela define a proporção largura‑altura dos módulos do DataMatrix.  
- **Posso gerar PNG, JPEG ou SVG?** Sim – o método `Save` suporta PNG, JPEG, BMP, GIF e outros.  
- **Preciso de licença para este recurso?** Um teste gratuito funciona para desenvolvimento; uma licença completa é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **Quantos valores de aspect‑ratio são válidos?** Qualquer número de ponto flutuante positivo; valores típicos são 0.5 – 2.0.

## O que é um código de barras DataMatrix e por que ajustar sua proporção?
DataMatrix é um código de barras matricial bidimensional que armazena grandes quantidades de dados em um espaço pequeno. Ajustar a **aspect ratio** permite esticar ou comprimir os módulos horizontalmente, o que pode ser útil para encaixar o código de barras em colunas estreitas ou etiquetas largas sem sacrificar a legibilidade.

## Pré-requisitos

Antes de começarmos a personalizar as proporções do DataMatrix, certifique‑se de que você tem os seguintes pré‑requisitos em vigor:

1. **Visual Studio** – qualquer versão recente serve.  
2. **Aspose.BarCode for .NET** – faça o download [aqui](https://releases.aspose.com/barcode/net/).  
3. **.NET Framework / .NET Core** – seu projeto deve direcionar uma versão suportada.

## Importar Namespaces

Primeiro, você precisa importar o namespace necessário em seu projeto C#:

```csharp
using Aspose.BarCode.Generation;
```

> **Dica profissional:** Mantenha esta instrução `using` no topo do seu arquivo para que a classe `BarcodeGenerator` esteja sempre disponível.

## Guia Passo a Passo

### Passo 1: Configurar Seu Projeto
Crie um novo projeto de console ou Windows Forms no Visual Studio e adicione uma referência ao DLL do Aspose.BarCode.

### Passo 2: Inicializar um Gerador de Código de Barras
Instancie um `BarcodeGenerator` com o tipo DataMatrix e os dados que você deseja codificar:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> Esta linha cria um gerador pronto para produzir um código de barras DataMatrix que contém o texto de exemplo.

### Passo 3: Personalizar a Proporção e Salvar Arquivos PNG
Agora você pode alterar a **aspect ratio** e salvar cada versão como uma imagem PNG:

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- A primeira chamada cria um código de barras com proporção quadrada (`AspectRatio = 1`).  
- A segunda chamada comprime o código de barras horizontalmente (`AspectRatio = 0.5`), produzindo uma aparência mais larga.

Agora você tem dois arquivos **barcode PNG** com diferentes proporções prontos para uso em relatórios, etiquetas ou elementos de UI.

## Problemas Comuns & Soluções
| Problema | Solução |
|----------|---------|
| **Imagem gerada está borrada** | Aumente o parâmetro `Resolution` antes de salvar (`gen.Parameters.ImageResolution = 300`). |
| **Código de barras não lê** | Certifique‑se de que a proporção permaneça entre 0.5 – 2.0 e mantenha uma zona silenciosa suficiente (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **Erros de caminho de arquivo** | Use `Path.Combine` para construir o caminho de saída e verifique se a pasta existe. |

## Perguntas Frequentes

**Q: Posso personalizar a proporção de outros tipos de código de barras usando Aspose.BarCode para .NET?**  
A: Sim, muitos códigos de barras 2‑D (por exemplo, QR, PDF417) suportam ajustes de aspect‑ratio através de seus objetos de parâmetro específicos.

**Q: Existe um teste gratuito disponível para Aspose.BarCode para .NET?**  
A: Sim, você pode acessar um teste gratuito do Aspose.BarCode para .NET [aqui](https://releases.aspose.com/).

**Q: Onde posso comprar uma licença para Aspose.BarCode para .NET?**  
A: Você pode comprar uma licença no site da Aspose [aqui](https://purchase.aspose.com/buy).

**Q: O Aspose.BarCode para .NET é compatível com diferentes versões do .NET Framework?**  
A: Sim, funciona com .NET Framework 4.x, .NET Core 3.1+ e as versões mais recentes do .NET.

**Q: Posso gerar códigos de barras em diferentes formatos com Aspose.BarCode para .NET?**  
A: Absolutamente – PNG, JPEG, BMP, GIF, TIFF, SVG e PDF são todos suportados nativamente.

## Conclusão

Personalizar a **aspect ratio** de um código de barras DataMatrix e **criar arquivos barcode PNG** é simples com Aspose.BarCode para .NET. Seguindo os passos acima, você pode gerar códigos de barras com tamanho perfeito que atendem aos requisitos exatos de layout do seu projeto. Explore outros parâmetros como `Resolution`, `Margin` e `Color` para ajustar ainda mais a saída.

Para uma exploração mais profunda, confira a [documentação](https://reference.aspose.com/barcode/net/) oficial ou junte‑se à comunidade no [fórum Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Última atualização:** 2026-01-12  
**Testado com:** Aspose.BarCode 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}