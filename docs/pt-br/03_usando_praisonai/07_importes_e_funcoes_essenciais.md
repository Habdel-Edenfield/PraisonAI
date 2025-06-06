# Importações e Funções Essenciais

Esta lição apresenta as importações mais comuns do PraisonAI para criar agentes e fluxos de trabalho. Use-a como referência rápida ao iniciar seus projetos.

## Principais Módulos

```python
from praisonaiagents import Agent, Task, PraisonAIAgents, Tools
from praisonaiagents.utils import get_logger
```

- `Agent` define o comportamento de um agente individual.
- `Task` encapsula uma unidade de trabalho executável por um agente.
- `PraisonAIAgents` orquestra múltiplos agentes e tarefas.
- `Tools` dá acesso ao catálogo de ferramentas internas.
- `get_logger` cria um logger padronizado para acompanhar a execução.

## Exemplo Rápido

```python
from praisonaiagents import Agent, Task, PraisonAIAgents, Tools
from praisonaiagents.utils import get_logger

logger = get_logger()

# Define a tarefa
minha_tarefa = Task(
    description="Gerar resumo do texto",
    tools=[Tools.SEARCH]
)

# Define o agente
meu_agente = Agent(
    role="Escritor",
    goal="Produzir conteúdo de qualidade",
    tasks=[minha_tarefa]
)

# Cria o orquestrador e executa
workflow = PraisonAIAgents(agents=[meu_agente], logger=logger)
workflow.run()
```

O código acima demonstra como importar e iniciar rapidamente um fluxo simples com um único agente e uma tarefa.
