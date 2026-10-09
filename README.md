# 🎮 Dashboard de Vendas — Xbox Game Pass Subscriptions

Projeto do desafio de Excel da DIO: transformar dados brutos de assinaturas do Xbox Game Pass em um **dashboard de vendas** visual e interativo, construído com **tabelas dinâmicas, gráficos dinâmicos e segmentação de dados**.

![Dashboard Xbox Game Pass](assets/preview_dashboard.png)

## 🎯 Objetivo

Organizar e visualizar os dados de vendas para responder rapidamente perguntas como:

- Quanto a empresa faturou no total e quantos assinantes tem?
- Qual o faturamento dos passes adicionais (**EA Play** e **Minecraft**)?
- Qual a diferença de faturamento entre quem tem e quem não tem **renovação automática**?
- Qual plano (Core, Standard ou Ultimate) e qual tipo de assinatura (Monthly, Quarterly ou Annual) mais vendem?
- Como o faturamento evoluiu ao longo dos meses?

## 📁 Conteúdo do repositório

| Arquivo | Descrição |
|---|---|
| `dashboard_xbox.xlsx` | Pasta de trabalho com o dashboard concluído |
| `assets/preview_dashboard.png` | Imagem do dashboard |
| `README.md` | Este documento |

## 📊 Dados utilizados

Base fornecida pelo curso (aba **Bases**, formatada como tabela `Tabela1`): **295 assinantes**, com início entre **01/01/2024 e 16/12/2024**.

| Coluna | Descrição |
|---|---|
| Subscriber ID | Identificador do assinante |
| Name | Nome do assinante |
| Plan | Plano: Core, Standard ou Ultimate |
| Start Date | Data de início da assinatura |
| Auto Renewal | Renovação automática (Yes/No) |
| Subscription Price | Preço do plano |
| Subscription Type | Tipo: Monthly, Quarterly ou Annual |
| EA Play Season Pass / Price | Contratou o EA Play? Valor |
| Minecraft Season Pass / Price | Contratou o Minecraft? Valor |
| Coupon Value | Valor do cupom de desconto |
| Total Value | Valor total da venda |

## 🗂️ Estrutura da planilha

1. **Dashboard** — painel final, com indicadores, gráficos e filtro.
2. **Calculos** — 7 tabelas dinâmicas que alimentam o dashboard (aba oculta).
3. **Bases** — dados brutos, em tabela do Excel.

### Indicadores (cartões)

| Cartão | Cálculo | Valor (visão geral) |
|---|---|---|
| Faturamento total | Soma de Total Value | R$ 7.633 |
| EA Play Season Pass | Soma de EA Play Season Pass Price | R$ 2.940 |
| Minecraft Season Pass | Soma de Minecraft Season Pass Price | R$ 3.880 |
| Assinantes | Contagem de Subscriber ID | 295 |
| Ticket médio por assinante | Média de Total Value | R$ 25,87 |
| Cupons concedidos | Soma de Coupon Value | R$ 2.122 |

### Gráficos

| Gráfico | Tabela dinâmica (Linhas → Valores) | Responde ao filtro? |
|---|---|---|
| Faturamento por renovação automática (barras) | Auto Renewal → Soma de Total Value | Sim |
| Faturamento por plano (colunas) | Plan → Soma de Total Value | Sim |
| Faturamento por tipo de assinatura (rosca) | Subscription Type → Soma de Total Value | Não (sempre o total geral) |
| Faturamento por mês de início (linha) | Start Date (agrupada por mês) → Soma de Total Value | Sim |

### Interatividade

A **segmentação de dados** *Subscription Type* (Annual, Monthly, Quarterly) filtra os cartões e os gráficos ao mesmo tempo. Ela está conectada a todas as tabelas dinâmicas, **exceto** à da rosca, que mostra sempre o panorama geral.

Exemplo, com **Annual** selecionado: faturamento R$ 1.754, 71 assinantes, ticket médio R$ 24,70, EA Play R$ 600 e Minecraft R$ 940. Sem renovação automática são R$ 217 e com renovação R$ 1.537.

## 🔁 Como reproduzir

1. Abra o Excel e cole a base na aba **Bases**. Selecione os dados, aperte **Ctrl+T** e dê o nome `Tabela1` à tabela.
2. Crie as abas **Calculos** e **Dashboard**.
3. Na aba **Calculos**, crie as tabelas dinâmicas em **Inserir > Tabela Dinâmica**, usando `Tabela1` como origem, conforme as tabelas acima. Para os cartões, uma única tabela com os quatro valores (soma, contagem, média e soma de cupons) e sem linhas. Para o gráfico mensal, agrupe a data por **Meses**.
4. Para cada tabela de gráfico, use **Análise de Tabela Dinâmica > Gráfico Dinâmico**, recorte e cole no Dashboard. Oculte os botões de campo e remova título, legenda e linhas de grade.
5. No Dashboard, monte os cartões com formas e ligue cada um à célula da tabela dinâmica correspondente.
6. Insira a segmentação de dados de **Subscription Type** e conecte às tabelas pelo menu **Segmentação > Conexões de Relatório** (menos a da rosca).
7. Aplique o visual: fundo `#E8E6E9`, faixa lateral e destaques em `#22C55E`, cores de apoio `#9BC848` e `#2AE6B1`.
8. Oculte a aba **Calculos** e desative as linhas de grade do Dashboard.

## 🎨 Paleta de cores

| Cor | Hex | Uso |
|---|---|---|
| Verde Xbox | `#22C55E` | Títulos, números, gráficos e faixa lateral |
| Verde-limão | `#9BC848` | Apoio nos gráficos |
| Verde-água | `#2AE6B1` | Apoio nos gráficos |
| Cinza | `#E8E6E9` | Fundo do painel |

## ⚠️ Observações

- Os dados de dezembro de 2024 vão só até 16/12, por isso a queda no último ponto do gráfico mensal.
- Janeiro e fevereiro têm poucas vendas na base.
- Logos de Xbox, EA Play e Minecraft pertencem aos seus respectivos titulares e foram fornecidos no material do desafio, usados apenas para fins educacionais.

## 🛠️ Ferramentas

Microsoft Excel: tabelas, tabelas dinâmicas, gráficos dinâmicos e segmentação de dados.

## 👩‍💻 Autora

**Helen** — [github.com/Helenh12](https://github.com/Helenh12)
