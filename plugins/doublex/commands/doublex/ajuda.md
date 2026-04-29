Apresente ao usuário tudo que o plugin DoubleX oferece de forma clara e amigável.

Explique que com este plugin ele pode gerenciar sua plataforma de agentes de IA
diretamente pelo Claude Code, sem precisar abrir o painel web.

Liste os comandos disponíveis organizados por categoria:

**Configuração**
- /doublex:setup — Configurar o plugin pela primeira vez

**Agentes de IA**
- /doublex:novo-agente — Criar um novo agente
- /doublex:meus-agentes — Ver todos os seus agentes
- /doublex:detalhe-agente — Ver todos os detalhes de um agente específico
- /doublex:editar-agente — Editar um agente existente
- /doublex:conversar — Conversar diretamente com um agente

**Flows Multi-Agente**
- /doublex:novo-flow — Criar um novo flow
- /doublex:meus-flows — Ver todos os seus flows
- /doublex:detalhe-flow — Ver detalhes e estrutura de um flow
- /doublex:editar-flow — Editar o grafo de um flow
- /doublex:executar-flow — Enviar mensagem para um flow (aguarda resposta)
- /doublex:status-flow — Executar flow em background e acompanhar o status

**Utilitários**
- /doublex:modelos — Ver todos os modelos de IA disponíveis
- /doublex:ajuda — Mostrar esta ajuda

Informe também que o usuário pode falar naturalmente sem usar comandos, por exemplo:
"cria um agente de suporte", "lista meus flows", "conversa com o agente X".

Pergunte ao usuário: "O que você quer fazer agora?"

---
Se receber erro "API key required", "401 Unauthorized" ou "Failed to connect to doublex", o token não está configurado. Oriente o usuário a rodar /doublex:setup antes de continuar.
