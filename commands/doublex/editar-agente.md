Guie o usuário para editar um agente existente na plataforma DoubleX.

1. Chame list_agents para mostrar os agentes disponíveis.
2. Pergunte qual agente o usuário quer editar.
3. Chame get_agent para exibir as configurações atuais do agente.
4. Mostre o resumo atual e pergunte o que o usuário quer alterar:
   - Nome do agente
   - System prompt (comportamento e personalidade)
   - Modelo de IA (chame list_models se o usuário quiser trocar de modelo ou provider)
   - Temperatura: 0 = muito preciso, 0.7 = equilibrado (padrão), 1.5+ = muito criativo
   - Máximo de tokens por resposta (tamanho das respostas)
   - Máximo de iterações de ferramentas

5. Aplique somente os campos que o usuário informou com update_agent.
   Campos não mencionados permanecem iguais.

6. Confirme as alterações mostrando:
   - O que foi alterado (antes → depois)
   - O estado final do agente

7. Ofereça conversar com o agente agora para testar as mudanças (/doublex:conversar).

---
Se receber erro "API key required", "401 Unauthorized" ou "Failed to connect to doublex", o token não está configurado. Oriente o usuário a rodar /doublex:setup antes de continuar.
