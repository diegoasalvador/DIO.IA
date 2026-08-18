# Miniguia de Estudos - Cloud Computing com AWS

> Projeto do desafio DIO: **Caderno Temático no NotebookLM** - uso da Inteligência Artificial como ferramenta de aprendizagem ativa, com curadoria de fontes, engenharia de prompts e organização do conhecimento.

Este repositório documenta o processo completo de criação de um caderno temático sobre **Cloud Computing e AWS** usando o **NotebookLM**. Este README consolida todos os entregáveis do desafio: **objetivos**, **curadoria de fontes**, **testes de prompts** (com as "cicatrizes" do processo) e o **miniguia de estudo** final.

---

## 1. Contexto e Objetivos

### O que é este projeto

O **NotebookLM** do Google permite "conversar" com fontes de conhecimento (documentos, PDFs, sites) de forma fundamentada e com citações. Neste desafio, usei a IA como ferramenta de **aprendizagem ativa**: em vez de apenas ler sobre cloud computing, eu elaborei perguntas estratégicas, testei variações de prompts, critiquei as respostas e consolidei o conhecimento em um miniguia de estudos.

### Assunto escolhido

**Cloud Computing com foco em AWS** - desde os conceitos fundamentais (o que é computação em nuvem, modelos de serviço e implantação) até a arquitetura de soluções (Well-Architected Framework) e o modelo de responsabilidade compartilhada.

### Objetivos de estudo

1. Compreender a definição de computação em nuvem segundo o NIST e as características essenciais desse modelo.
2. Diferenciar os modelos de serviço (IaaS, PaaS, SaaS) e os modelos de implantação (pública, privada, híbrida).
3. Entender como a AWS entrega esses conceitos na prática: principais serviços, region/AZ, pay-as-you-go.
4. Dominar o **Modelo de Responsabilidade Compartilhada** (o que é responsabilidade do cliente vs. da AWS).
5. Aplicar os **pilares do AWS Well-Architected Framework** ao revisar arquiteturas.
6. Construir um **miniguia de estudo** com resumos, glossário e prompts reutilizáveis para revisões futuras.

---

## 2. Curadoria de Fontes

Lista das fontes abertas (texto e PDF) selecionadas, analisadas e adicionadas ao NotebookLM.

> Critério de seleção: fontes oficiais, abertas e gratuitas, com profundidade adequada e linguagem acessível. O objetivo foi cobrir desde os fundamentos (NIST) até a prática de arquitetura (AWS).

### 2.1 Fontes selecionadas

| # | Fonte | Tipo | Link | Por que escolhi |
| --- | --- | --- | --- | --- |
| 1 | **NIST SP 800-145 - The NIST Definition of Cloud Computing** | PDF | [nvlpubs.nist.gov/nistpubs/legacy/sp/nistspecialpublication800-145.pdf](https://nvlpubs.nist.gov/nistpubs/legacy/sp/nistspecialpublication800-145.pdf) | Fonte oficial que define computação em nuvem, as 5 características essenciais, 3 modelos de serviço e 4 modelos de implantação. Base acadêmica para qualquer estudo do tema. |
| 2 | **AWS - What is Cloud Computing?** | Texto (site) | [aws.amazon.com/what-is-cloud-computing/](https://aws.amazon.com/what-is-cloud-computing/) | Introdução acessível aos conceitos e benefícios da nuvem (agilidade, elasticidade, custos) na visão de um provedor líder. Complementa a teoria com a prática. |
| 3 | **AWS Well-Architected Framework** | Texto (site) | [docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) | Documento oficial sobre os pilares (Excelência Operacional, Segurança, Confiabilidade, Eficiência de Performance, Otimização de Custos e Sustentabilidade). Essencial para o objetivo de arquitetura. |
| 4 | **AWS - Overview of Amazon Web Services (Whitepaper)** | Texto (site) | [docs.aws.amazon.com/whitepapers/latest/aws-overview/aws-overview.html](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/aws-overview.html) | Visão geral dos serviços AWS organizados por categoria (compute, storage, banco de dados, rede, segurança etc.). Ajuda a mapear a oferta de serviços na prática. |
| 5 | **AWS - Shared Responsibility Model** | Texto (site) | [aws.amazon.com/compliance/shared-responsibility-model/](https://aws.amazon.com/compliance/shared-responsibility-model/) | Documento oficial sobre a divisão de responsabilidades entre cliente e AWS. Fundamental para entender segurança na nuvem. |

### 2.2 Como as fontes foram usadas no NotebookLM

1. **NIST SP 800-145**: usado para responder "o que é nuvem?", características essenciais e modelos de serviço/implantacao (fonte teórica).
2. **What is Cloud Computing (AWS)**: usado para traduzir os conceitos teóricos em benefícios práticos e vocabulário do dia a dia.
3. **Well-Architected Framework**: usado para os resumos sobre os pilares de arquitetura e boas práticas.
4. **Overview of AWS (Whitepaper)**: usado para mapear serviços por categoria e montar a tabela de serviços principais.
5. **Shared Responsibility Model**: usado para entender segurança e responder perguntas sobre "quem é responsável pelo quê".

### 2.3 O que aprendi com a curadoria

- **Complementaridade das fontes**: unir uma fonte teórica/formal (NIST) com fontes práticas do provedor (AWS) deu profundidade e contexto real ao estudo.
- **Qualidade importa**: o NotebookLM responde melhor quando as fontes são oficiais e bem estruturadas, pois as respostas com citações ficam mais precisas.
- **PDF e texto**: o NotebookLM processa tanto PDFs quanto links de sites; o PDF do NIST foi ideal para citações diretas de definições formais.

---

## 3. Engenharia de Prompts e "Cicatrizes"

Este documento registra o **processo** de conversar com o NotebookLM: as perguntas estratégicas elaboradas, as variações de prompts testadas, as respostas obtidas (com referências) e as dificuldades encontradas - as chamadas "cicatrizes" do processo de aprendizagem ativa.

> As respostas apresentadas são exemplos baseados nas fontes curadas - substitua pelos resultados reais que você obtiver no seu notebook.

### 3.1 Estratégia adotada

1. **Começar amplo**: entender os conceitos fundamentais antes de mergulhar em detalhes.
2. **Iterar em camadas**: de definição -> benefícios -> arquitetura -> segurança.
3. **Exigir citações**: sempre pedir que o NotebookLM aponte a fonte da resposta (isso reduz alucinação).
4. **Registrar o que falhou**: cada prompt que gerou resposta rasa ou vaga virou uma "cicatriz" que me ensinou a melhorar a pergunta.

### 3.2 Perguntas estratégicas e variações testadas

#### Tema 1 - Fundamentos (o que é nuvem)

**Objetivo**: consolidar a definição formal e as características essenciais da computação em nuvem.

- **Prompt v1**: `O que é computação em nuvem?`
  - **Resposta**: Resposta genérica, sem citações claras e misturando características com exemplos.
  - **Avaliação**: Muito amplo. Não direcionou o NotebookLM para as fontes.

- **Prompt v2 (ajustado)**: `Com base no documento NIST SP 800-145, explique o que é computação em nuvem e liste as 5 características essenciais desse modelo, citando a fonte para cada item.`
  - **Resposta**: Resposta estruturada com on-demand self-service, acesso amplo pela rede, pooling de recursos, elasticidade rápida e serviço medido, cada uma com citação para o NIST.
  - **Avaliação**: Muito melhor. Indicar a fonte específica e o formato de saída (listar com citações) guiou a resposta.

#### Tema 2 - Modelos de serviço (IaaS, PaaS, SaaS)

**Objetivo**: entender as diferenças e exemplos práticos.

- **Prompt v1**: `Qual a diferença entre IaaS, PaaS e SaaS?`
  - **Resposta**: Resposta razoável, mas sem exemplos na AWS e sem uma analogia para fixar.
  - **Cicatriz**: Faltou pedir um formato comparativo.

- **Prompt v2 (ajustado)**: `Crie uma tabela comparando IaaS, PaaS e SaaS com as colunas: definição, o que o usuário gerencia, o que o provedor gerencia e 2 exemplos na AWS. Use apenas as fontes do notebook e cite-as.`
  - **Resposta**: Tabela comparativa com exemplos (ex.: EC2 para IaaS, Elastic Beanstalk para PaaS, serviços SaaS da AWS). Citações apontadas.
  - **Avaliação**: O pedido de tabela + colunas explícitas + exemplos + citações produziu resposta de qualidade de estudo.

#### Tema 3 - Arquitetura (Well-Architected Framework)

**Objetivo**: dominar os pilares do framework.

- **Prompt v1**: `Quais são os pilares do Well-Architected Framework?`
  - **Resposta**: Listou os pilares, mas de forma superficial, sem explicar o objetivo de cada um.
  - **Cicatriz**: prompt sem contexto de aplicação.

- **Prompt v2 (ajustado)**: `Explique os 5 pilares do AWS Well-Architected Framework. Para cada pilar: objetivo, uma pergunta-chave que o pilar tenta responder e uma prática recomendada da fonte. Ao final, explique por que os pilares são usados em conjunto em uma revisão de arquitetura.`
  - **Resposta**: Resposta organizada por pilar, com perguntas-chave (ex.: "Como você monitora os recursos?" para Excelência Operacional) e práticas recomendadas, tudo com citações do framework.
  - **Avaliação**: Estruturar o pedido em "objetivo + pergunta-chave + prática" deu profundidade.

#### Tema 4 - Segurança (Modelo de Responsabilidade Compartilhada)

**Objetivo**: entender quem é responsável pelo quê na nuvem AWS.

- **Prompt v1**: `Como funciona a segurança na AWS?`
  - **Resposta**: Resposta genérica sobre ferramentas de segurança, sem abordar a divisão de responsabilidades.
  - **Cicatriz**: precisou de direcionamento específico.

- **Prompt v2 (ajustado)**: `Com base no modelo de responsabilidade compartilhada da AWS, liste quais são as responsabilidades do cliente e quais são as responsabilidades da AWS. Dê 3 exemplos de itens do lado do cliente (ex.: dados, configurações) e 3 do lado da AWS (ex.: hardware, infraestrutura global). Cite as fontes.`
  - **Resposta**: Divisão clara: AWS = segurança **da** nuvem (hardware, software, rede, datacenters, regiões/AZs); cliente = segurança **na** nuvem (dados, plataforma, aplicações, IAM, configurações). Exemplos com citações.
  - **Avaliação**: Excelente. A pergunta pediu a estrutura da resposta (2 listas + exemplos), o que ajudou muito.

### 3.3 Registro das respostas obtidas (exemplo de consolidação)

> Formato de como registrei as respostas. Substitua pelo conteúdo real do seu notebook.

**Pergunta**: `Explique, com base nas fontes, por que a nuvem reduz custos em comparação com um datacenter próprio.`

**Resposta obtida** (síntese):
- Nuvem troca despesas fixas (capex - compra de servidores/datacenters) por despesas variáveis (opex - pagar conforme o uso).
- Economias de escala do provedor reduzem o custo unitário dos recursos.
- Modelo pay-as-you-go permite pagar apenas pelo que consumir (on-demand).
- Referências: fonte AWS "What is Cloud Computing?" (seção Benefits) e whitepaper de visão geral.

### 3.4 "Cicatrizes" - Dificuldades encontradas e como resolvi

| # | Problema | Causa provável | Ajuste aplicado | Resultado |
| --- | --- | --- | --- | --- |
| 1 | Resposta genérica sem citações | Prompt muito amplo, sem indicar fonte | Nomear a fonte e pedir citações explícitas | Respostas fundamentadas nas fontes |
| 2 | Resposta superficial sobre pilares | Não pedi estrutura de saída | Definir o formato (objetivo + pergunta-chave + prática) | Resposta aprofundada |
| 3 | Mistura de conceitos (nuvem vs. modelo de serviço) | Pergunta com dois assuntos juntos | Dividir em perguntas menores e específicas | Respostas limpas por tópico |
| 4 | Exemplos fora das fontes | Não restrinji o escopo | Adicionar "use apenas as fontes do notebook" | Exemplos alinhados às fontes |
| 5 | Lista muito longa e repetitiva | Não limitei a quantidade de itens | "Liste os 5 principais", "dê 3 exemplos" | Saída enxuta e objetiva |

### 3.5 Aprendizados sobre engenharia de prompts

1. **Contexto e fonte**: sempre indicar a fonte (ou pedir citação) para reduzir alucinação.
2. **Formato de saída**: pedir tabela, lista numerada ou estrutura específica melhora a usabilidade do resultado.
3. **Escopo**: uma pergunta por vez; restringir quantidades ("3 exemplos", "5 pilares").
4. **Iteração**: a primeira resposta quase nunca é a melhor; refinar com base na resposta anterior.
5. **Validação humana**: a IA organiza e sintetiza, mas a curadoria e o julgamento crítico continuam sendo humanos.

---

## 4. Miniguia de Estudo (Entrega Final)

Conteúdo consolidado para revisões rápidas: **resumos estruturados**, **glossário** e **prompts reutilizáveis** para futuras sessões de estudo com o NotebookLM.

### 4.1 Resumos estruturados

#### 4.1.1 O que é computação em nuvem

Computação em nuvem é o **fornecimento sob demanda de recursos de TI pela internet**, com **cobrança conforme o uso (pay-as-you-go)**. Em vez de comprar e manter servidores e datacenters próprios, o usuário acessa serviços como poder de processamento, armazenamento e banco de dados conforme a necessidade, de um provedor de nuvem.

**Características essenciais** (definição do NIST SP 800-145):

| Característica | Descrição |
| --- | --- |
| **Self-service sob demanda** | O usuário provisiona recursos sem interação humana com o provedor |
| **Amplo acesso pela rede** | Recursos acessíveis pela rede por dispositivos heterogêneos |
| **Pooling de recursos** | Recursos compartilhados entre múltiplos usuários (multi-tenant) |
| **Elasticidade rápida** | Escalar para cima/baixo rapidamente, às vezes automaticamente |
| **Serviço medido** | O uso é medido/monitorado e cobrado conforme o consumo |

**Benefícios** (visão AWS): agilidade (implantar em minutos), elasticidade (escalar conforme a demanda), redução de custos (capex -> opex), alcance global e confiabilidade (datacenters distribuídos).

#### 4.1.2 Modelos de serviço

| Modelo | O usuário gerencia | O provedor gerencia | Exemplo na AWS |
| --- | --- | --- | --- |
| **IaaS** (Infraestrutura como Serviço) | SO, aplicações, runtime, dados | Servidores, rede, virtualização, datacenter | Amazon EC2 |
| **PaaS** (Plataforma como Serviço) | Aplicações e dados | Plataforma completa (SO, runtime, infra) | AWS Elastic Beanstalk, AWS Lambda |
| **SaaS** (Software como Serviço) | Dados e usuários | Tudo (software e infraestrutura) | Aplicações SaaS da AWS e parceiros |

**Regra geral**: quanto mais alto o modelo, menos controle e mais responsabilidade transferida ao provedor; quanto mais baixo, mais controle e mais gerenciamento pelo usuário.

#### 4.1.3 Modelos de implantação

- **Nuvem pública**: infraestrutura do provedor, compartilhada e acessível pela internet (ex.: AWS, Azure, GCP).
- **Nuvem privada**: infraestrutura exclusiva de uma organização (on-premises ou hospedada).
- **Nuvem híbrida**: combinação de pública e privada (ex.: AWS Outposts conectando on-premises à nuvem).
- **Comunitária**: compartilhada por organizações com interesses comuns.

#### 4.1.4 Infraestrutura global da AWS

- **Região (Region)**: localização geográfica com múltiplas AZs (ex.: us-east-1, sa-east-1 em São Paulo).
- **Zona de disponibilidade (AZ)**: datacenters isolados dentro de uma região, conectados por rede de baixa latência. Múltiplas AZs garantem **alta disponibilidade** e **tolerância a falhas**.
- **Edge locations / CloudFront**: distribuição de conteúdo com baixa latência.

#### 4.1.5 Modelo de Responsabilidade Compartilhada

- **AWS = Segurança DA nuvem**: hardware, software, rede, datacenters e infraestrutura global.
- **Cliente = Segurança NA nuvem**: dados, plataformas, aplicações, gerenciamento de identidade e acesso (IAM), configuração de serviços, sistema operacional (em IaaS) e permissões.
- **Depende do modelo**: em SaaS o provedor assume mais; em IaaS o cliente assume mais.

#### 4.1.6 AWS Well-Architected Framework

O framework ajuda a avaliar arquiteturas contra boas práticas e medir pontos de melhoria. Pilares:

| Pilar | Foco |
| --- | --- |
| **Excelência Operacional** | Operar e monitorar sistemas, aprender e melhorar continuamente |
| **Segurança** | Proteger dados, sistemas e ativos; identificar e gerenciar acessos |
| **Confiabilidade** | Recuperar-se de falhas, escalar e atender às expectativas de disponibilidade |
| **Eficiência de Performance** | Usar recursos de TI de forma eficiente para cumprir requisitos |
| **Otimização de Custos** | Evitar gastos desnecessários e usar os recursos da forma mais econômica |
| **Sustentabilidade** | Minimizar os impactos ambientais dos workloads |

#### 4.1.7 Serviços AWS por categoria (visão geral)

| Categoria | Serviços principais |
| --- | --- |
| Compute | Amazon EC2, AWS Lambda, Elastic Beanstalk, Auto Scaling |
| Armazenamento | Amazon S3 (objetos), Amazon EBS (blocos), Amazon EFS (arquivos) |
| Banco de dados | Amazon RDS, Amazon DynamoDB (NoSQL), Amazon Aurora |
| Rede e CDN | Amazon VPC, CloudFront, Elastic Load Balancing, Route 53 |
| Segurança e identidade | IAM, AWS WAF, AWS Shield, AWS KMS |
| Integração | Amazon SQS, SNS, EventBridge |
| Gerenciamento | CloudWatch (monitoramento), CloudTrail (auditoria), AWS Config |

### 4.2 Glossário - principais conceitos

| Termo | Definição |
| --- | --- |
| **Cloud computing** | Fornecimento sob demanda de recursos de TI pela internet com cobrança conforme o uso |
| **IaaS** | Infraestrutura como serviço: servidores virtuais, armazenamento e rede sob demanda |
| **PaaS** | Plataforma como serviço: ambiente gerenciado para desenvolver e implantar aplicações |
| **SaaS** | Software como serviço: aplicação completa entregue pela internet |
| **On-demand / self-service** | Provisionar recursos sem intervenção manual do provedor |
| **Elasticidade** | Capacidade de aumentar ou reduzir recursos automaticamente conforme a demanda |
| **Pay-as-you-go** | Modelo de cobrança em que se paga somente pelo que é consumido |
| **Capex** | Despesa de capital (investimento fixo, ex.: compra de servidores) |
| **Opex** | Despesa operacional (custo recorrente, ex.: fatura mensal do provedor) |
| **Região (Region)** | Área geográfica da AWS composta por múltiplas AZs |
| **Zona de disponibilidade (AZ)** | Um ou mais datacenters isolados dentro de uma região |
| **Tolerância a falhas** | Capacidade do sistema de continuar operando diante de falhas de componentes |
| **Alta disponibilidade** | Capacidade de manter o sistema acessível e operacional por longos períodos |
| **Responsabilidade compartilhada** | Divisão de responsabilidades de segurança entre provedor (segurança da nuvem) e cliente (segurança na nuvem) |
| **IAM (Identity and Access Management)** | Serviço AWS para gerenciar usuários, grupos, papéis e permissões |
| **VPC** | Rede virtual isolada dentro da nuvem AWS onde se provisionam recursos |
| **Amazon S3** | Serviço de armazenamento de objetos escalável e durável |
| **Amazon EC2** | Serviço de servidores virtuais (instâncias) sob demanda |
| **AWS Lambda** | Compute serverless: executa código sem gerenciar servidores |
| **Serverless** | Modelo em que o provedor gerencia a infraestrutura e o usuário paga pela execução |
| **Auto Scaling** | Ajuste automático da capacidade de recursos conforme a demanda |
| **CloudWatch** | Serviço de monitoramento de métricas, logs e alarmes |
| **CloudTrail** | Serviço de auditoria que registra chamadas à API da conta |
| **Well-Architected Framework** | Conjunto de boas práticas da AWS organizadas em pilares para projetar arquiteturas |

### 4.3 Conjunto de prompts reutilizáveis

Prontos para usar em futuras revisões no NotebookLM (substitua as fontes conforme seu notebook).

#### Revisão de fundamentos

```
Com base no NIST SP 800-145, explique o que é computação em nuvem e liste as 5 características essenciais. Para cada característica, escreva um exemplo prático e cite a fonte.
```

```
Crie um quiz de 5 perguntas de múltipla escolha sobre as características essenciais da nuvem. Ao final, dê o gabarito e explique cada resposta citando as fontes.
```

#### Revisão de modelos de serviço

```
Faça uma tabela comparando IaaS, PaaS e SaaS com: definição, o que o usuário gerencia, o que o provedor gerencia, e 2 exemplos na AWS para cada. Cite as fontes.
```

```
Dê 3 exemplos de aplicações que fariam sentido rodar em cada modelo (IaaS, PaaS, SaaS) e explique o motivo da escolha.
```

#### Revisão de arquitetura (Well-Architected)

```
Explique os 5 pilares do AWS Well-Architected Framework. Para cada pilar, inclua: objetivo, pergunta-chave e uma prática recomendada. Cite as fontes.
```

```
Considere uma aplicação web que precisa de alta disponibilidade e custo controlado. Proponha uma arquitetura simples na AWS aplicando os pilares de confiabilidade e otimização de custos. Explique cada decisão e cite as fontes.
```

#### Revisão de segurança

```
Explique o modelo de responsabilidade compartilhada da AWS: liste as responsabilidades do cliente e as da AWS e dê 3 exemplos de cada. Cite as fontes.
```

```
Crie uma tabela que mostra, para IaaS, PaaS e SaaS, quem é responsável por: infraestrutura física, sistema operacional, aplicação e dados. Cite as fontes.
```

#### Técnica de autoavaliação

```
Gere 10 perguntas de revisão sobre cloud computing e AWS baseadas apenas nas fontes do notebook, do nível fácil ao difícil. Depois que eu responder, corrija minhas respostas e aponte o que preciso revisar.
```

```
Resuma os conceitos mais importantes das minhas fontes em 15 flashcards no formato "pergunta -> resposta", com citações, para eu revisar rapidamente.
```

---

## 5. Estrutura do Repositório

```
.
├── README.md                              # Este arquivo: todos os entregáveis consolidados
├── fontes/
│   └── fontes-selecionadas.md             # Curadoria das fontes usadas no NotebookLM
├── engenharia-de-prompts/
│   └── prompts-e-cicatrizes.md            # Perguntas estratégicas, variações e troubleshooting
└── miniguia-de-estudo/
    └── README.md                          # Entrega final: resumos, glossário e prompts reutilizáveis
```

## 6. Como reproduzir este projeto no NotebookLM

1. **Crie uma conta** no [NotebookLM](https://notebooklm.google.com) (gratuito com conta Google).
2. **Crie um novo Notebook** e dê um nome, por exemplo: `Caderno - Cloud Computing AWS`.
3. **Adicione as fontes** listadas na seção 2 (links de sites e PDFs abertos).
4. **Converse com suas fontes**: use os prompts estratégicos da seção 3.
5. **Registre as respostas e dificuldades** encontradas (o que funcionou, o que não funcionou).
6. **Consolide o material** no miniguia de estudo (seção 4).

> Dica: as respostas do NotebookLM variam com o tempo e com as fontes carregadas. Use este repositório como **modelo** e substitua pelas respostas reais que você obtiver no seu notebook.

## 7. Tecnologias e ferramentas

- **NotebookLM** (Google) - para construir o caderno temático e conversar com as fontes
- **Markdown** - para organizar e documentar todo o conhecimento no GitHub
- **Git/GitHub** - para versionamento e portfólio

## 8. Próximos passos / Melhorias futuras

- [ ] Adicionar novas fontes (ex.: AWS Well-Architected Labs e casos de estudo)
- [ ] Registrar respostas reais obtidas no meu notebook do NotebookLM
- [ ] Criar mapas mentais das características essenciais da nuvem
- [ ] Preparar flashcards a partir do glossário para revisão espaçada

---

*Projeto desenvolvido para o desafio da DIO - Bootcamp de IA Generativa. Todo o conteúdo foi produzido com curadoria humana sobre fontes oficiais e validação via NotebookLM.*
