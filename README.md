# Sprint 4 - Análise Estatística de Dados (Megaline)

## Descrição do Projeto

Neste projeto, atuei como analista de dados para a empresa de telecomunicações **Megaline**, que oferece dois planos pré-pagos: **Surf** e **Ultimate**.

O objetivo principal foi analisar o comportamento dos clientes e determinar **qual plano gera mais receita em média**, auxiliando o time de negócios na tomada de decisão sobre investimentos em publicidade.

---

## Objetivo

- Analisar o comportamento dos usuários dos planos Surf e Ultimate
- Calcular a receita mensal gerada por cliente
- Comparar estatisticamente os planos
- Testar hipóteses sobre diferenças de receita entre:
  - Planos (Surf vs Ultimate)
  - Regiões (NY-NJ vs outras)

---

## Conjuntos de Dados

O projeto utiliza 5 tabelas:

- `megaline_users.csv` → informações dos usuários
- `megaline_calls.csv` → dados de chamadas
- `megaline_messages.csv` → mensagens de texto
- `megaline_internet.csv` → uso de internet
- `megaline_plans.csv` → detalhes dos planos

---

## Etapa 1 - Preparação dos Dados

Durante o pré-processamento:

- Conversão de tipos de dados (datas e numéricos)
- Verificação e tratamento de valores ausentes
- Padronização das colunas
- Conversão de MB para GB no consumo de internet
- Ajuste de regras de arredondamento conforme especificação:
  - Chamadas → arredondadas para cima por chamada
  - Internet → arredondada no total mensal

---

## Etapa 2 - Engenharia de Features

Foram criadas métricas mensais por usuário:

- Total de minutos por mês
- Total de mensagens por mês
- Consumo de internet por mês (GB)
- Receita mensal por usuário

### Cálculo da Receita

A receita foi calculada considerando:

- Mensalidade fixa do plano
- Excedentes:
  - Minutos
  - Mensagens
  - Dados

---

## Etapa 3 - Análise Exploratória

Foram analisados os seguintes aspectos:

- Distribuição de uso de:
  - Minutos
  - Mensagens
  - Internet
- Comparação entre planos
- Construção de histogramas
- Cálculo de métricas estatísticas:
  - Média
  - Variância
  - Desvio padrão

### Principais Insights:

- Usuários do plano **Ultimate** tendem a consumir mais recursos
- O plano **Surf** possui maior incidência de excedentes
- Distribuições apresentam assimetria (principalmente internet)

---

## Etapa 4 - Teste de Hipóteses

### Hipótese 1: Receita dos Planos

- **H0 (nula):** A receita média dos planos Surf e Ultimate é igual
- **H1 (alternativa):** As receitas médias são diferentes

### Hipótese 2: Receita por Região

- **H0 (nula):** A receita média de NY-NJ é igual às outras regiões
- **H1 (alternativa):** As receitas são diferentes

### Metodologia

- Teste t de Student para amostras independentes
- Nível de significância (alpha): 0.05

---

## Conclusão

Com base na análise:

- Foi possível identificar diferenças no comportamento de uso entre os planos
- A receita média varia entre os planos analisados
- Os testes estatísticos indicaram se as diferenças são significativas
- Os resultados podem orientar decisões estratégicas da empresa

---

## Tecnologias Utilizadas

- Python
- Pandas
- NumPy
- Matplotlib / Seaborn
- SciPy (testes estatísticos)
- Jupyter Notebook