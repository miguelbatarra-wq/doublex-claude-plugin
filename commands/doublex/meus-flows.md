Mostre ao usuário todos os flows multi-agente cadastrados na plataforma DoubleX.

1. Chame list_flows.
2. Apresente os flows em tabela com: nome, status (ativo/inativo), agentes (nodes) e conexões (edges).
3. Separe visualmente os flows ativos dos inativos.
4. Informe o total de flows e quantos estão ativos.
5. Se não houver flows, ofereça criar um com /doublex:novo-flow.
6. Pergunte se o usuário quer:
   - Ver os detalhes e estrutura de um flow (/doublex:detalhe-flow)
   - Editar o grafo de um flow (/doublex:editar-flow)
   - Enviar uma mensagem de teste (/doublex:executar-flow)
   - Criar um novo flow (/doublex:novo-flow)

---
Se receber erro "API key required", "401 Unauthorized" ou "Failed to connect to doublex", o token não está configurado. Oriente o usuário a rodar /doublex:setup antes de continuar.
