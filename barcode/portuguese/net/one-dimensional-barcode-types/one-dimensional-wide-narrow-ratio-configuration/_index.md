---
date: 2026-03-02
description: Aprenda a gerar códigos de barras com Aspose.BarCode para .NET, incluindo
  dicas de geração de códigos de barras no Visual Studio, neste guia passo a passo
  sobre a configuração da proporção larga‑estreita.
linktitle: One-Dimensional Wide-Narrow Ratio Configuration
second_title: Aspose.BarCode .NET API
title: Como gerar código de barras – Configuração da relação larga‑estreita
url: /pt/net/one-dimensional-barcode-types/one-dimensional-wide-narrow-ratio-configuration/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configuração da Razão Larga‑Estreita Unidimensional

Você está procurando **how to generate barcode** de forma fácil em suas aplicações .NET? Aspose.BarCode for .NET torna a geração de códigos de barras em projetos Visual Studio simples e poderosa. Neste tutorial, vamos percorrer a criação de códigos de barras unidimensionais com uma razão larga‑estreita personalizada, explicar por que a razão é importante e mostrar como ajustá‑la para diferentes ambientes de leitura.

## Respostas Rápidas
- **O que controla a razão larga‑estreita?** Ela define a largura relativa das barras “largas” em relação às barras “estreitas” em um código de barras 1D.  
- **Qual tipo de código de barras é usado no exemplo?** Code 39 Extended, uma simbologia popular para dados alfanuméricos.  
- **Posso mudar a razão em tempo de execução?** Sim – basta definir `gen.Parameters.Barcode.WideNarrowRatio` para o valor desejado antes de salvar.  
- **Preciso de licença para este recurso?** A razão larga‑estreita funciona com a avaliação gratuita; uma licença completa desbloqueia todas as opções de renderização.  
- **Isso é compatível com .NET Core?** Absolutamente – Aspose.BarCode suporta .NET Framework, .NET Core e .NET 5/6+.

## O que é uma Razão Larga‑Estreita?
Em códigos de barras unidimensionais cada barra é “larga” ou “estreita”. A razão (por exemplo, 2 ou 5) determina quantas vezes uma barra larga é mais larga que uma barra estreita. Ajustar essa razão pode melhorar a legibilidade em impressoras ou scanners de baixa resolução.

## Por que usar Aspose.BarCode for .NET?
* **Controle total** – Cada aspecto visual, incluindo a razão larga‑estreita, pode ser definido programaticamente.  
* **Multiplataforma** – Funciona no Visual Studio, Visual Studio Code e em qualquer runtime .NET.  
* **Sem dependências externas** – Não é necessário DLLs nativas ou ferramentas de terceiros.  
* **Documentação rica e suporte** – Inclui exemplos, fóruns e guias de início rápido.

## Pré‑requisitos

Antes de mergulharmos no mundo dos códigos de barras com Aspose.BarCode for .NET, você precisa ter os seguintes pré‑requisitos em vigor:

### 1. Ambiente Visual Studio
   - Certifique‑se de que o Visual Studio está instalado em seu sistema para trabalhar com aplicações .NET.
   
### 2. Biblioteca Aspose.BarCode for .NET
   - Você deve ter a biblioteca Aspose.BarCode for .NET instalada. Você pode baixá‑la a partir do [website](https://releases.aspose.com/barcode/net/).

### 3. Chave de Licença (Opcional)
   - Se você possui uma chave de licença, ela pode ser usada para desbloquear recursos adicionais da biblioteca. Você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

Agora que você tem os pré‑requisitos configurados, vamos criar códigos de barras unidimensionais com configuração de razão larga‑estreita usando Aspose.BarCode for .NET.

## Importar Namespaces

Primeiro, você precisa incluir os namespaces necessários em seu projeto para acessar os recursos do Aspose.BarCode for .NET. Você pode fazer isso adicionando as seguintes instruções using no topo do seu código:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Etapa 1: Definir o Caminho do Diretório

Comece definindo o caminho onde você deseja salvar as imagens de código de barras geradas. Você pode fazer isso com o código a seguir:

```csharp
string path = "Your Directory Path";
```

Substitua `"Your Directory Path"` pelo caminho real do diretório onde deseja salvar as imagens de código de barras.

## Etapa 2: Criar um Código de Barras Unidimensional com Razão Larga‑Estreita

Agora, vamos criar um código de barras unidimensional com configuração de razão larga‑estreita usando Aspose.BarCode for .NET. Neste exemplo, usaremos o tipo de codificação Code39Extended e definiremos os dados como `"ASPOSE"`:

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code39Extended, "ASPOSE");
```

Esta linha de código inicializa um gerador de código de barras com o tipo de codificação e os dados especificados.

## Etapa 3: Definir a Razão Larga/Estreita

A razão larga‑estreita determina a proporção entre os elementos largos e estreitos no código de barras. Nesta etapa, definiremos a razão larga‑estreita para **2**:

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 2;
```

E então, salvaremos a imagem do código de barras gerado no caminho especificado:

```csharp
gen.Save($"{path}WideNarrow2Code39.png", BarCodeImageFormat.Png);
```

## Etapa 4: Ajustar a Razão Larga‑Estreita

Você pode experimentar diferentes razões larga‑estreita para obter a aparência desejada do código de barras. Por exemplo, se quiser um código de barras mais largo, defina a razão larga‑estreita para **5**:

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 5;
```

E salve a imagem do código de barras:

```csharp
gen.Save($"{path}WideNarrow5Code39.png", BarCodeImageFormat.Png);
```

Agora você criou com sucesso códigos de barras unidimensionais com diferentes razões larga‑estreita usando Aspose.BarCode for .NET. Esta biblioteca oferece a flexibilidade de gerar códigos de barras adaptados aos seus requisitos específicos.

## Problemas Comuns e Soluções
- **Imagem não salva** – Verifique se a variável `path` aponta para uma pasta existente e se sua aplicação tem permissões de gravação.  
- **Código de barras aparece distorcido** – Experimente uma razão menor (por exemplo, 2) para impressoras de baixa resolução; razões maiores podem causar artefatos de impressão.  
- **Caracteres não suportados** – Code 39 Extended suporta o conjunto ASCII completo; certifique‑se de que sua string de dados não contenha caracteres de controle proibidos.

## Conclusão

Aspose.BarCode for .NET é uma biblioteca versátil que simplifica a geração e personalização de códigos de barras em suas aplicações .NET. Neste tutorial, abordamos o básico de criação de códigos de barras unidimensionais com configuração de razão larga‑estreita. Com a capacidade de ajustar finamente vários parâmetros, você pode criar códigos de barras que se adequam perfeitamente às suas necessidades, seja desenvolvendo um recurso **how to generate barcode** em um aplicativo desktop ou um serviço **barcode generation visual studio**.

## Perguntas Frequentes

### 1. Como posso obter uma licença para Aspose.BarCode for .NET?
Você pode comprar uma licença no [site da Aspose](https://purchase.aspose.com/buy).

### 2. Posso usar Aspose.BarCode for .NET sem uma licença?
Sim, você pode usá‑la com uma licença temporária, que fornece funcionalidade limitada.

### 3. Aspose.BarCode for .NET é compatível com .NET Core?
Sim, Aspose.BarCode for .NET é compatível com .NET Core e .NET Framework.

### 4. Existem limitações nos tipos de códigos de barras que posso gerar?
Aspose.BarCode for .NET suporta uma ampla gama de simbologias de código de barras, incluindo QR Code, Code 39 e muitas outras.

### 5. Como posso obter suporte ou fazer perguntas sobre Aspose.BarCode for .NET?
Você pode visitar o [fórum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) para suporte e discussões.

### Perguntas e Respostas Adicionais

**Q: Alterar a razão larga‑estreita afeta a velocidade de leitura?**  
A: Uma razão maior pode tornar as barras mais espessas, o que pode melhorar a legibilidade em scanners de baixa qualidade, mas pode aumentar ligeiramente a quantidade de dados que o scanner processa.

**Q: Posso definir a razão para outras simbologias como Code128?**  
A: Sim, a propriedade `WideNarrowRatio` se aplica a todas as simbologias 1D que suportam elementos largos e estreitos.

---

**Última atualização:** 2026-03-02  
**Testado com:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}