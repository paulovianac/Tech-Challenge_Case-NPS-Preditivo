# 📊 Tech Challenge Fase 1 — Case NPS Preditivo

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-2.0+-green?logo=pandas)
![Status](https://img.shields.io/badge/Status-Concluído-brightgreen)
![License](https://img.shields.io/badge/License-MIT-yellow)

> **Pós-Graduação em Inteligência Artificial para Cientistas de Dados — FIAP**  
> Tech Challenge — Fase 1 | Maio de 2026

---

## 📌 Objetivo do Projeto

Explorar e analisar dados operacionais de um e-commerce brasileiro para **identificar quais fatores influenciam a satisfação do cliente (NPS)** e propor **ações proativas de melhoria** antes mesmo da aplicação da pesquisa de NPS.

O projeto responde à pergunta central:

> *Quais fatores operacionais realmente influenciam a satisfação do cliente e como a empresa pode agir de forma proativa para melhorar a experiência?*

---

## 📂 Estrutura do Repositório

```
nps-preditivo/
│
├── data/
│   └── desafio_nps_fase_1.csv          # Base de dados original (2.500 registros)
│
├── notebooks/
│   └── notebook_eda_nps.ipynb          # Notebook completo com EDA e análise
│
├── reports/
│   ├── Relatorio_Executivo_NPS.docx    # Relatório executivo completo (Word)
│   ├── Apresentacao_NPS_Preditivo.pptx # Apresentação gerencial (7 slides)
│   ├── roteiro_video_executivo.md      # Roteiro para vídeo de até 5 minutos
│   ├── fig1_distribuicao_nps.png       # Distribuição das notas NPS
│   ├── fig2_correlacao.png             # Mapa de correlação entre variáveis
│   ├── fig3_boxplots_fatores.png       # Boxplots: atraso e reclamações
│   ├── fig4_ponto_ruptura.png          # Ponto de ruptura: atraso × NPS
│   ├── fig5_nps_por_sac.png            # NPS por contatos com SAC
│   ├── fig6_nps_regiao.png             # NPS por região geográfica
│   └── fig7_recompra.png              # Taxa de recompra por categoria
│
├── requirements.txt                    # Dependências do projeto
└── README.md                          # Este arquivo
```

---

## 📊 Descrição da Base de Dados

A base contém **2.500 registros** de pedidos com **19 variáveis**, organizadas em 4 dimensões:

### Dicionário de Dados

| Variável | Descrição | Tipo |
|----------|-----------|------|
| `customer_id` | Identificador único do cliente | int |
| `order_id` | Identificador único do pedido | int |
| `customer_age` | Idade do cliente | int |
| `customer_region` | Região geográfica do cliente (Sudeste, Sul, Nordeste, Norte, Centro-Oeste) | str |
| `customer_tenure_months` | Tempo de relacionamento com a empresa (em meses) | int |
| `order_value` | Valor total do pedido (R$) | float |
| `items_quantity` | Quantidade de itens no pedido | int |
| `discount_value` | Valor de desconto aplicado (R$) | float |
| `payment_installments` | Número de parcelas do pagamento | int |
| `delivery_time_days` | Tempo total de entrega (dias) | int |
| `delivery_delay_days` | Dias de atraso na entrega | int |
| `freight_value` | Valor do frete (R$) | float |
| `delivery_attempts` | Número de tentativas de entrega | int |
| `customer_service_contacts` | Contatos do cliente com o SAC | int |
| `resolution_time_days` | Tempo para resolução de problemas (dias) | int |
| `complaints_count` | Número de reclamações registradas | int |
| `repeat_purchase_30d` | Recompra em até 30 dias (0=não, 1=sim) | int |
| `csat_internal_score` | Score interno de satisfação do cliente (1 a 5) | float |
| `nps_score` | **Nota NPS do cliente (0 a 10)** — TARGET | int |

### Classificação NPS

| Categoria | Faixa | Descrição |
|-----------|-------|-----------|
| 🔴 **Detrator** | 0 a 6 | Insatisfeito — pode prejudicar a marca |
| 🟡 **Neutro** | 7 a 8 | Satisfeito — sem engajamento ativo |
| 🟢 **Promotor** | 9 a 10 | Leal — recomenda a marca ativamente |

---

## 🔬 Metodologia Utilizada

O projeto segue uma abordagem estruturada em **3 etapas obrigatórias**:

### Etapa 1 — Entendimento do Negócio
- Identificação do problema de negócio
- Análise da importância do NPS para e-commerce
- Mapeamento das áreas beneficiadas
- Reflexão sobre impacto na recompra, boca a boca e market share
- Levantamento de indicadores complementares

### Etapa 2 — Definição da Target
- Seleção e justificativa da variável-alvo (`nps_score`)
- Análise do momento de coleta na jornada do cliente
- Avaliação de riscos de uso inadequado

### Etapa 3 — Análise Exploratória dos Dados (EDA)
- Inspeção e limpeza dos dados
- Análise descritiva e de correlações
- Identificação de fatores críticos para satisfação
- Descoberta de pontos de ruptura operacionais
- Análise de perfil de clientes por categoria NPS
- Impacto financeiro via taxa de recompra
- Visualizações interpretativas para público não técnico

**Ferramentas utilizadas:** Python 3.10+, Pandas, NumPy, Matplotlib, Seaborn

---

## 🚀 Como Reproduzir os Resultados

### Pré-requisitos

- Python 3.10 ou superior
- pip (gerenciador de pacotes)

### Passo a passo

```bash
# 1. Clone o repositório
git clone https://github.com/[seu-usuario]/nps-preditivo.git
cd nps-preditivo

# 2. Crie um ambiente virtual (recomendado)
python -m venv venv
source venv/bin/activate    # Linux/Mac
venv\Scripts\activate       # Windows

# 3. Instale as dependências
pip install -r requirements.txt

# 4. Execute o notebook
jupyter notebook notebooks/notebook_eda_nps.ipynb
```

### Estrutura de execução

1. O notebook carrega os dados de `data/desafio_nps_fase_1.csv`
2. Realiza toda a análise exploratória com visualizações
3. Salva os gráficos gerados em `reports/`
4. Todas as métricas e insights são exibidos inline

---

## 📈 Principais Resultados

### Métricas Gerais

| Indicador | Valor |
|-----------|-------|
| NPS Médio | 6,07 |
| Promotores (9-10) | 18,0% |
| Neutros (7-8) | 33,3% |
| Detratores (0-6) | 48,7% |
| **NPS Geral** | **-30,7** |

### 🔑 5 Descobertas Principais

1. **Atraso na entrega** é o principal destruidor de NPS (correlação = -0,159)
2. **Ponto de ruptura:** satisfação cai drasticamente após **3 dias de atraso**
3. Clientes com **4+ contatos com SAC** têm NPS significativamente inferior
4. **Promotores recompram 4,3x mais** que Detratores (48,4% vs 11,2%)
5. **Diferenças regionais são mínimas** — o problema é operacional, não geográfico

### ✅ 5 Recomendações Estratégicas

1. 🚨 Zerar atrasos críticos (>3 dias)
2. 📦 Reduzir tentativas de entrega
3. ⚡ Acelerar resolução no SAC (First Contact Resolution)
4. 🎯 Programa proativo de recuperação de Detratores
5. ⭐ Converter Neutros em Promotores via programas de fidelidade

---

## 👥 Equipe

| Nome | RM |
|------|-----|
| [Inserir nome] | [RM] |
| [Inserir nome] | [RM] |
| [Inserir nome] | [RM] |

---

## 📄 Referências

- Reichheld, F. (2003). *The One Number You Need to Grow*. Harvard Business Review.
- FIAP — Material de apoio Tech Challenge Fase 1
- Bain & Company — NPS Benchmarks por setor
- E-commerce Brasil — Indicadores de mercado 2025/2026

---

**📅 Última atualização:** Maio de 2026
