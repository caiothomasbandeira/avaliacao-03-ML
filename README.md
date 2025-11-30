# Avaliação 03 – Marketing com Aprendizado por Reforço

Projeto completo em notebook (`marketing_rl_notebook.ipynb`) que carrega um dataset público, conduz análise exploratória, treina um modelo probabilístico de conversão e um agente Q-Learning para selecionar canais de campanha. Ao final, o notebook gera um PDF (`relatorio_marketing_rl.pdf`) com o resumo do experimento.

## Pré-requisitos

- Python 3.13 (ou compatível)
- Git (opcional, apenas para clonar)

## Passo a passo

1. **Clonar ou baixar** este repositório.
2. **Criar o ambiente virtual** (Windows PowerShell):
	```powershell
	python -m venv .venv
	```
3. **Ativar o ambiente**:
	```powershell
	.\.venv\Scripts\Activate.ps1
	```
4. **Instalar dependências**:
	```powershell
	pip install -r requirements.txt
	```
5. **Abrir o Jupyter Lab/Notebook** (o notebook já usa `marketing_rl_notebook.ipynb`):
	```powershell
	jupyter lab
	```
	ou
	```powershell
	jupyter notebook
	```
6. **Executar todas as células** do notebook. Os dados são lidos diretamente do link do Dropbox (nenhum arquivo é salvo localmente) e, ao final, o relatório PDF é criado na raiz do projeto.

## Estrutura

- `marketing_rl_notebook.ipynb`: pipeline completa (EDA, modelo, RL, PDF).
- `requirements.txt`: bibliotecas necessárias.
- `relatorio_marketing_rl.pdf`: relatório gerado ao final do notebook.

## Resultados principais

- Modelo de regressão logística com ROC-AUC ~0,78 para estimar conversões.
- Agente Q-Learning com exploração decrescente, média de recompensa ~104 e taxa de conversão simulada ~61% durante a avaliação.

## Checklist de requisitos atendidos

- Dataset público realista carregado diretamente via URL (sem persistência em disco).
- Ambiente de simulação onde cada episódio sorteia clientes e o agente escolhe canais de marketing.
- Recompensa composta por bônus de conversão e penalidade de custo por ação.
- Implementação de algoritmo de RL (Q-Learning tabular com política \(\varepsilon\)-greedy).
- Avaliação do impacto das decisões do agente com métricas de recompensa e conversão.
- Relatório em PDF documentando todas as etapas e conclusões.

## Próximos passos sugeridos

- Incorporar métricas financeiras (receita, LTV) ao reward do agente.
- Testar algoritmos baseados em Deep Q-Network ou políticas contínuas.
- Integrar o agente a campanhas reais para monitorar uplift de conversão.
