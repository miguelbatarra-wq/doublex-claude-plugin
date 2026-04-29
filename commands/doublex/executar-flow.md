Envie uma mensagem para um flow multi-agente e aguarde a resposta completa.

Use este comando quando quiser uma resposta imediata do flow.
Para flows longos sem pressa, use /doublex:status-flow.

1. Chame list_flows para mostrar os flows disponíveis.
2. Pergunte qual flow o usuário quer usar.
3. Pergunte a mensagem que o usuário quer enviar.
4. Chame send_message_to_flow com o flowId e a mensagem.
5. Trate cada possível status da resposta:

   **status = "success"**
   Mostre a resposta do flow de forma clara. Informe o tempo de execução (durationMs).

   **status = "waiting"**
   O flow pausou — um agente está aguardando resposta do usuário.
   Exiba a resposta do agente e peça a próxima mensagem.
   Chame send_message_to_flow novamente usando o mesmo sessionId retornado.
   Repita até o status ser "success".

   **status = "timeout"**
   O flow demorou mais que o esperado. Use /doublex:status-flow com o runId
   retornado para verificar o resultado quando ficar pronto.

   **status = "error"**
   Mostre o erro de forma clara e sugira verificar as configurações do flow.

---
Se receber erro "API key required", "401 Unauthorized" ou "Failed to connect to doublex", o token não está configurado. Oriente o usuário a rodar /doublex:setup antes de continuar.
