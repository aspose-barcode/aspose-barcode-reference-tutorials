---
date: 2026-02-12
description: Aprenda a criar códigos de barras code128 com uma proporção personalizada
  de estreito‑largo em Java usando Aspose.BarCode e gerar imagens PNG de códigos de
  barras de forma eficiente. Siga nosso guia passo a passo.
linktitle: Configuring Wide-Narrow Ratio
second_title: Aspose.BarCode Java API
title: Como criar código de barras CODE_128 com proporção larga‑estreita em Java
url: /pt/java/barcode-configuration/configuring-wide-narrow-ratio/
weight: 17
---

 Java 24.11 (latest at time of writing) (translate "Testado com:" maybe)

**Author:** Aspose (keep)

Then closing shortcodes.

Also note: "For Portuguese, ensure proper RTL formatting if needed" Not needed.

Now produce final content with same markdown.

Let's craft translation.

Be careful to keep bold markers.

Let's write.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Criar Código de Barras CODE_128 com Proporção Wide‑Narrow em Java

## Introdução

Se você precisa **criar código128 barcode** com proporções visuais precisas, ajustar a proporção wide‑narrow é a chave. Neste tutorial vamos percorrer um processo de criação de **barcode passo‑a‑passo** usando Aspose.BarCode para Java, mostrando como configurar a proporção, **gerar imagens de barcode PNG** e **salvar a imagem do barcode** no disco. Seja para rótulos de inventário, etiquetas de envio ou qualquer aplicação que exija um código de barras CODE_128 com estilo personalizado, você encontrará tudo o que precisa aqui.

## Respostas Rápidas
- **O que é a proporção wide‑narrow?** Ela controla a largura relativa das barras largas em relação às barras estreitas em um código de barras.  
- **Qual simbologia suporta ajuste de proporção?** A maioria das simbologias 1‑D, incluindo CODE_128, permite definir uma proporção personalizada.  
- **Preciso de licença?** Um teste gratuito está disponível, mas uma licença comercial é necessária para uso em produção.  
- **Posso gerar uma imagem de código de barras em formato PNG?** Sim—use `generator.save(...)` para gerar imagens de barcode PNG.  
- **O código é compatível com Java 8+?** Absolutamente; Aspose.BarCode funciona com todas as versões modernas do Java.

## Pré-requisitos

Antes de mergulharmos no código, certifique‑se de que você tem o seguinte:

- Java Development Kit (JDK) instalado na sua máquina.  
- Biblioteca Aspose.BarCode para Java. Baixe-a a partir do [download link](https://releases.aspose.com/barcode/java/).

## Importar Pacotes

Para começar, importe a classe essencial da Aspose.BarCode para o seu projeto.

```java
// Import Aspose.BarCode library
import com.aspose.barcode.generation.BarcodeGenerator;
```

## O que é a proporção wide‑narrow e por que ajustá‑la?

A proporção wide‑narrow determina quão espessas as barras “largas” aparecem em comparação com as “estreitas”. Ajustar essa proporção pode melhorar a legibilidade pelos scanners, atender a padrões específicos de impressão ou simplesmente combinar com o estilo visual de uma marca.

## Como criar código de barras code128 com proporção wide‑narrow em Java

Abaixo está um guia **barcode passo‑a‑passo** que o conduz por cada parte do processo.

### Etapa 1: Definir Diretório do Documento

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Certifique‑se de que o diretório exista e que você tenha permissões de gravação; é aqui que o arquivo de **salvar imagem do barcode** será colocado.

### Etapa 2: Instanciar Objeto Barcode

```java
// Instantiate barcode object
// Create an instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

Aqui nós **criamos code128 barcode** passando `EncodeTypes.CODE_128` para o construtor.

### Etapa 3: Definir Proporção Wide‑Narrow

```java
// Set the wide to narrow ratio for the barcode
generator.getParameters().getBarcode().setWideNarrowRatio(3.0f);
```

O método `setWideNarrowRatio` permite ajustar finamente o espaçamento visual. Um valor de `3.0f` significa que a barra larga tem três vezes a largura de uma barra estreita.

### Etapa 4: Salvar Imagem no Disco

```java
// Save the image to disk in PNG format
generator.save(dataDir + "wideNarrowRatio.png");
```

Chamar `save` **gerará a imagem do barcode** e a armazenará como um arquivo PNG, concluindo a etapa de **salvar imagem do barcode**.

## Por que ajustar a proporção wide‑narrow?

- **Compatibilidade com Scanner:** Alguns scanners preferem uma proporção entre 2.0 e 3.0 para taxas de leitura ótimas.  
- **Qualidade de Impressão:** Ajustar a proporção pode compensar limitações de DPI da impressora, evitando barras distorcidas.  
- **Consistência de Marca:** Algumas empresas desejam códigos de barras que se alinhem visualmente com cores corporativas ou diretrizes de design.

## Problemas Comuns e Soluções

| Problema | Motivo | Correção |
|----------|--------|----------|
| O barcode parece distorcido | Proporção muito alta/baixa para a impressora | Ajuste o valor passado para `setWideNarrowRatio` (ex.: 2.0‑2.5). |
| Arquivo não criado | Caminho `dataDir` inválido ou permissões insuficientes | Verifique o caminho do diretório e assegure que a aplicação tenha acesso de gravação. |
| O scanner não lê o barcode | Proporção fora da faixa recomendada para a simbologia | Use proporções padrão (2.0‑3.0) ou teste com o scanner alvo. |

## Perguntas Frequentes

**Q: Posso usar Aspose.BarCode com outros frameworks Java?**  
A: Sim, Aspose.BarCode foi projetado para funcionar perfeitamente com Spring, Java EE, Android e outros ambientes Java.

**Q: Como posso gerar códigos de barras com diferentes simbologias?**  
A: Basta alterar o tipo de simbologia no construtor `BarcodeGenerator`, por exemplo `EncodeTypes.QR` para códigos QR.

**Q: Existe uma versão de teste disponível para Aspose.BarCode?**  
A: Sim, você pode acessar a versão de teste gratuita [aqui](https://releases.aspose.com/).

**Q: Onde encontro documentação detalhada para Aspose.BarCode?**  
A: Consulte a documentação [aqui](https://reference.aspose.com/barcode/java/).

**Q: Como obter suporte para Aspose.BarCode?**  
A: Visite o fórum Aspose.BarCode [aqui](https://forum.aspose.com/c/barcode/13) para suporte e discussões da comunidade.

---

**Última atualização:** 2026-02-12  
**Testado com:** Aspose.BarCode para Java 24.11 (mais recente no momento da escrita)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}