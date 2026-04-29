Mostre ao usuário todos os agentes de IA cadastrados na plataforma DoubleX.

1. Chame list_agents.
2. Apresente os agentes em formato de tabela com: nome, modelo, status e conversas.
3. Separe visualmente os agentes ACTIVE dos PENDING.
4. Informe o total de agentes e quantos estão ativos.
5. Se não houver agentes, ofereça criar um com /doublex:novo-agente.
6. Pergunte se o usuário quer:
   - Ver detalhes completos de algum agente (/doublex:detalhe-agente)
   - Editar algum agente (/doublex:editar-agente)
   - Conversar com algum agente (/doublex:conversar)
   - Criar um novo agente (/doublex:novo-agente)

---
Se receber erro "API key required", "401 Unauthorized" ou "Failed to connect to doublex", o token não está configurado. Oriente o usuário a rodar /doublex:setup antes de continuar.
