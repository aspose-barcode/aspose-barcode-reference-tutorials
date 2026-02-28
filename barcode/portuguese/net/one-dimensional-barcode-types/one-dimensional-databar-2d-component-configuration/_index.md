---
date: 2026-02-28
description: Aprenda a criar o gerador de códigos de barras Aspose para códigos de
  barras Databar unidimensionais e 2D em .NET. Siga nosso guia passo a passo para
  configuração e personalização.
linktitle: One-Dimensional Databar 2D Component Configuration
second_title: Aspose.BarCode .NET API
title: Criar Gerador de Código de Barras Aspose – Configuração Databar 2D
url: /pt/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configuração do Componente Databar 2D Unidimensional

Neste tutorial você **criará um gerador de código de barras Aspose** para um componente Databar 2D Unidimensional usando a biblioteca Aspose.BarCode .NET. Seja para etiquetas de varejo, tags de inventário ou qualquer aplicação que precise de dados compactos e de alta densidade, este guia orienta você em cada passo — da configuração do projeto à gravação das imagens PNG finais.

## Respostas Rápidas
- **O que faz a flag do componente 2D?** Indica ao gerador se deve incorporar um símbolo 2D composto dentro do código de barras Databar.  
- **Posso alterar a dimensão X?** Sim, a propriedade `XDimension.Pixels` controla a largura do módulo.  
- **Qual formato de imagem é usado no exemplo?** PNG, via `BarCodeImageFormat.Png`.  
- **Preciso de licença para desenvolvimento?** Uma licença de avaliação funciona para testes; uma licença comercial é necessária para produção.  
- **O código é compatível com .NET Core?** Absolutamente — Aspose.BarCode suporta .NET Framework e .NET Core.

## O que é um Componente Databar 2D Unidimensional?
Um componente Databar 2D combina um código de barras linear tradicional com um pequeno símbolo 2D composto, permitindo armazenar informações extras (como uma URL ou campos de dados adicionais) sem aumentar o tamanho total do código de barras.

## Por que usar Aspose.BarCode para esta tarefa?
- **Integração completa com .NET** – funciona perfeitamente em projetos C#.  
- **API de configuração rica** – ajuste dimensões, habilite/desabilite o componente 2D e escolha entre diversos formatos de saída.  
- **Sem dependências externas** – a biblioteca é autônoma, facilitando a implantação.

## Pré‑requisitos

1. **Instalação** – Certifique‑se de que o Aspose.BarCode para .NET está instalado. Baixe-o no site [aqui](https://releases.aspose.com/barcode/net/).  
2. **Conhecimento Básico** – Familiaridade com C# e desenvolvimento .NET ajudará a seguir os passos.  
3. **Ambiente de Desenvolvimento** – Visual Studio, Rider ou qualquer editor compatível com C#.

Com esses fundamentos cobertos, vamos começar a configurar o componente Databar 2D.

## Importar Namespaces

A primeira coisa a fazer é importar o namespace Aspose.BarCode para acessar suas classes.

```csharp
using Aspose.BarCode;
```

## Definir o Caminho de Saída

Especifique onde as imagens de código de barras geradas serão salvas no seu sistema de arquivos.

```csharp
string path = "Your Directory Path";
```

Substitua `"Your Directory Path"` por um caminho de pasta real na sua máquina.

## Criar um Gerador de Código de Barras

Instancie o `BarcodeGenerator` com o tipo Databar Expanded e forneça os dados que deseja codificar.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

Sinta‑se à vontade para substituir os dados de exemplo pelo seu próprio identificador de aplicação GS1 ou outro payload.

## Como criar gerador de código de barras Aspose para Databar 2D Unidimensional

Agora configure as propriedades visuais e a flag do componente 2D, então salve as imagens.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;

// Disable 2D component flag
gen.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
gen.Save($"{path}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);

// Enable 2D component flag
gen.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
gen.Save($"{path}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

- **XDimension** controla a largura de cada módulo do código de barras.  
- Definir `Is2DCompositeComponent` como **false** gera um Databar linear puro.  
- Definir como **true** adiciona o símbolo 2D composto, útil para codificar dados extras.

## Problemas Comuns & Dicas

- **Caminho Inválido** – Verifique se a pasta existe e se a aplicação tem permissão de gravação.  
- **Exceção de Licença** – Se aparecer um aviso de licenciamento, aplique sua licença Aspose antes de gerar o código de barras.  
- **Imagem Não Visível** – Confirme se o `BarCodeImageFormat` corresponde à extensão de arquivo que você está usando.

## Conclusão

Agora você aprendeu a **criar um gerador de código de barras Aspose** para um componente Databar 2D Unidimensional, alternando a flag 2D composta e ajustando a dimensão X. Essa abordagem flexível permite adaptar o código de barras a uma ampla gama de cenários de negócios. Para personalizações mais avançadas, explore a documentação completa do Aspose.BarCode: [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/).

Se precisar de mais exemplos ou encontrar desafios, a comunidade Aspose é um ótimo lugar para fazer perguntas.

## Perguntas Frequentes

### O Aspose.BarCode para .NET é compatível com vários tipos de código de barras?
- Sim, o Aspose.BarCode para .NET suporta uma ampla variedade de tipos de código de barras, tornando‑o altamente versátil para diferentes aplicações.

### Posso personalizar a aparência dos códigos de barras gerados?
- Absolutamente! Você pode ajustar o tamanho, a cor e diversas outras propriedades visuais do código de barras conforme suas necessidades.

### Existem opções de licenciamento disponíveis para o Aspose.BarCode para .NET?
- Sim, a Aspose oferece opções de licenciamento que atendem a diferentes requisitos. Você pode explorá‑las no site.

### O Aspose.BarCode é adequado tanto para iniciantes quanto para desenvolvedores experientes?
- O Aspose.BarCode foi projetado para ser amigável, sendo adequado tanto para iniciantes quanto para desenvolvedores experientes.

### Onde posso obter suporte e assistência para o Aspose.BarCode para .NET?
- Você pode buscar ajuda e interagir com a comunidade no [Aspose.BarCode for .NET support forum](https://forum.aspose.com/c/barcode/13).

## Perguntas Frequentes

**Q: Posso gerar códigos de barras em formatos diferentes de PNG?**  
A: Sim, o método `Save` suporta BMP, JPEG, GIF, TIFF e mais, bastando especificar o `BarCodeImageFormat` adequado.

**Q: Como aplico uma cor personalizada ao código de barras?**  
A: Use `gen.Parameters.Barcode.ForeColor` e `gen.Parameters.Barcode.BackColor` para definir as cores de primeiro plano e de fundo.

**Q: É possível incorporar um logotipo na imagem do código de barras?**  
A: O Aspose.BarCode fornece a propriedade `Image` onde você pode sobrepor um logotipo após a geração do código de barras.

**Q: Quais versões do .NET são suportadas?**  
A: A biblioteca funciona com .NET Framework 4.5+, .NET Core 3.1+, .NET 5+, e .NET 6+.

**Q: Como melhorar a confiabilidade de leitura em impressões de baixa resolução?**  
A: Aumente o valor de `XDimension` e garanta contraste suficiente entre o código de barras e o fundo.

---

**Última atualização:** 2026-02-28  
**Testado com:** Aspose.BarCode 24.12 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}