Execute um flow em background e acompanhe o status até a conclusão.

Use este comando para flows longos ou complexos onde você não quer esperar na hora.
Para resposta imediata, use /doublex:executar-flow.

1. Chame list_flows para mostrar os flows disponíveis.
2. Pergunte qual flow executar e a mensagem inicial.
3. Chame run_flow — retorna um runId imediatamente sem aguardar o resultado.
4. Informe: "Flow iniciado! ID da execução: {runId}. Verificando o progresso..."
5. Chame get_flow_status com o runId para verificar o estado atual.
6. Trate cada status:

   **status = "running"**
   Informe que ainda está processando. Verifique novamente em alguns segundos
   (até 3 tentativas com intervalo). Se ainda running, forneça o runId ao usuário
   para ele verificar depois com /doublex:status-flow.

   **status = "success"**
   Mostre o resultado final e o tempo de execução (durationMs).

   **status = "waiting"**
   O flow pausou aguardando resposta do usuário. Exiba a mensagem do agente,
   peça a resposta do usuário e use send_message_to_flow com o sessionId para continuar.

   **status = "error"**
   Mostre o erro de forma clara com o campo "error" retornado.

   **status = "cancelled"**
   Informe que a execução foi cancelada.

---
Se receber erro "API key required", "401 Unauthorized" ou "Failed to connect to doublex", o token não está configurado. Oriente o usuário a rodar /doublex:setup antes de continuar.
