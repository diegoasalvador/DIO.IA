# Engenharia de Prompts e "Cicatrizes"

Este documento registra o **processo** de conversar com o NotebookLM: as perguntas estratégicas elaboradas, as variações de prompts testadas, as respostas obtidas (com referências) e as dificuldades encontradas - as chamadas "cicatrizes" do processo de aprendizagem ativa.

> Como usar: cada seção mostra o objetivo do estudo, o prompt testado, o que retornou e a análise. As respostas apresentadas são exemplos baseados nas fontes curadas - no seu notebook, substitua pelos resultados reais que você obtiver.

## Estratégia adotada

1. **Começar amplo**: entender os conceitos fundamentais antes de mergulhar em detalhes.
2. **Iterar em camadas**: de definição -> benefícios -> arquitetura -> segurança.
3. **Exigir citações**: sempre pedir que o NotebookLM aponte a fonte da resposta (isso reduz alucinação).
4. **Registrar o que falhou**: cada prompt que gerou resposta rasa ou vaga virou uma "cicatriz" que me ensinou a melhorar a pergunta.

## Perguntas estratégicas e variações testadas

### Tema 1 - Fundamentos (o que é nuvem)

**Objetivo**: consolidar a definição formal e as características essenciais da computação em nuvem.

- **Prompt v1**: `O que é computação em nuvem?`
  - **Resposta**: Resposta genérica, sem citações claras e misturando características com exemplos.
  - **Avaliação**: Muito amplo. Não direcionou o NotebookLM para as fontes.

- **Prompt v2 (ajustado)**: `Com base no documento NIST SP 800-145, explique o que é computação em nuvem e liste as 5 características essenciais desse modelo, citando a fonte para cada item.`
  - **Resposta**: Resposta estruturada com on-demand self-service, acesso amplo pela rede, pooling de recursos, elasticidade rápida e serviço medido, cada uma com citação para o NIST.
  - **Avaliação**: Muito melhor. Indicar a fonte específica e o formato de saída (listar com citações) guiou a resposta.

### Tema 2 - Modelos de serviço (IaaS, PaaS, SaaS)

**Objetivo**: entender as diferenças e exemplos práticos.

- **Prompt v1**: `Qual a diferença entre IaaS, PaaS e SaaS?`
  - **Resposta**: Resposta razoável, mas sem exemplos na AWS e sem uma analogia para fixar.
  - **Cicatriz**: Faltou pedir um formato comparativo.

- **Prompt v2 (ajustado)**: `Crie uma tabela comparando IaaS, PaaS e SaaS com as colunas: definição, o que o usuário gerencia, o que o provedor gerencia e 2 exemplos na AWS. Use apenas as fontes do notebook e cite-as.`
  - **Resposta**: Tabela comparativa com exemplos (ex.: EC2 para IaaS, Elastic Beanstalk para PaaS, serviços como o próprio AWS SaaS offerings). Citações apontadas.
  - **Avaliação**: O pedido de tabela + colunas explícitas + exemplos + citações produziu resposta de qualidade de estudo.

### Tema 3 - Arquitetura (Well-Architected Framework)

**Objetivo**: dominar os pilares do framework.

- **Prompt v1**: `Quais são os pilares do Well-Architected Framework?`
  - **Resposta**: Listou os pilares, mas de forma superficial, sem explicar o objetivo de cada um.
  - **Cicatriz**: prompt sem contexto de aplicação.

- **Prompt v2 (ajustado)**: `Explique os 5 pilares do AWS Well-Architected Framework. Para cada pilar: objetivo, uma pergunta-chave que o pilar tenta responder e uma prática recomendada da fonte. Ao final, explique por que os pilares são usados em conjunto em uma revisão de arquitetura.`
  - **Resposta**: Resposta organizada por pilar, com perguntas-chave (ex.: "Como você monitora os recursos?" para Excelência Operacional) e práticas recomendadas, tudo com citações do framework.
  - **Avaliação**: Estruturar o pedido em "objetivo + pergunta-chave + prática" deu profundidade.

### Tema 4 - Segurança (Modelo de Responsabilidade Compartilhada)

**Objetivo**: entender quem é responsável pelo quê na nuvem AWS.

- **Prompt v1**: `Como funciona a segurança na AWS?`
  - **Resposta**: Resposta genérica sobre ferramentas de segurança, sem abordar a divisão de responsabilidades.
  - **Cicatriz**: precisou de direcionamento específico.

- **Prompt v2 (ajustado)**: `Com base no modelo de responsabilidade compartilhada da AWS, liste quais são as responsabilidades do cliente e quais são as responsabilidades da AWS. Dê 3 exemplos de itens do lado do cliente (ex.: dados, configurações) e 3 do lado da AWS (ex.: hardware, infraestrutura global). Cite as fontes.`
  - **Resposta**: Divisão clara: AWS = segurança **da** nuvem (hardware, software, rede, datacenters, regiões/AZs); cliente = segurança **na** nuvem (dados, plataforma, aplicações, IAM, configurações). Exemplos com citações.
  - **Avaliação**: Excelente. A pergunta pediu a estrutura da resposta (2 listas + exemplos), o que ajudou muito.

## Registro das respostas obtidas (exemplo de consolidação)

> Abaixo, um exemplo do formato de como registrei as respostas. Substitua pelo conteúdo real do seu notebook.

**Pergunta**: `Explique, com base nas fontes, por que a nuvem reduz custos em comparação com um datacenter próprio.`

**Resposta obtida** (síntese):
- Nuvem troca despesas fixas (capex - compra de servidores/datacenters) por despesas variáveis (opex - pagar conforme o uso).
- Economias de escala do provedor reduzem o custo unitário dos recursos.
- Modelo pay-as-you-go permite pagar apenas pelo que consumir (on-demand).
- Referências: fonte AWS "What is Cloud Computing?" (seção Benefits) e whitepaper de visão geral.

## "Cicatrizes" - Dificuldades encontradas e como resolvi

| # | Problema | Causa provável | Ajuste aplicado | Resultado |
| --- | --- | --- | --- | --- |
| 1 | Resposta genérica sem citações | Prompt muito amplo, sem indicar fonte | Nomear a fonte e pedir citações explícitas | Respostas fundamentadas nas fontes |
| 2 | Resposta superficial sobre pilares | Não pedi estrutura de saída | Definir o formato (objetivo + pergunta-chave + prática) | Resposta aprofundada |
| 3 | Mistura de conceitos (nuvem vs. modelo de serviço) | Pergunta com dois assuntos juntos | Dividir em perguntas menores e específicas | Respostas limpas por tópico |
| 4 | Exemplos fora das fontes | Não restrinji o escopo | Adicionar "use apenas as fontes do notebook" | Exemplos alinhados às fontes |
| 5 | Lista muito longa e repetitiva | Não limitei a quantidade de itens | "Liste os 5 principais", "dê 3 exemplos" | Saída enxuta e objetiva |

## Aprendizados sobre engenharia de prompts (resumo)

1. **Contexto e fonte**: sempre indicar a fonte (ou pedir citação) para reduzir alucinação.
2. **Formato de saída**: pedir tabela, lista numerada ou estrutura específica melhora a usabilidade do resultado.
3. **Escopo**: uma pergunta por vez; restringir quantidades ("3 exemplos", "5 pilares").
4. **Iteração**: a primeira resposta quase nunca é a melhor; refinar com base na resposta anterior.
5. **Validação humana**: a IA organiza e sintetiza, mas a curadoria e o julgamento crítico continuam sendo humanos.
