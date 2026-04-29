Inicie uma conversa com um agente de IA da plataforma DoubleX.

1. Chame list_agents para mostrar os agentes disponíveis.
2. Pergunte com qual agente o usuário quer conversar.
3. Peça a mensagem inicial que o usuário quer enviar.
4. Chame chat_with_agent com o agentId e a mensagem.
5. Mostre a resposta do agente de forma clara, apresentando-a como uma conversa:
   - Prefixe com o nome do agente: "**[Nome do Agente]:** resposta aqui"
6. Pergunte se o usuário quer continuar conversando.
7. Se sim: inclua o histórico completo da conversa no campo history da próxima chamada
   para que o agente mantenha o contexto. Continue até o usuário encerrar.
8. Se o usuário quiser encerrar: resuma os pontos principais da conversa.

---
Se receber erro "API key required", "401 Unauthorized" ou "Failed to connect to doublex", o token não está configurado. Oriente o usuário a rodar /doublex:setup antes de continuar.
