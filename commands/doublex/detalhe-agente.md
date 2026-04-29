Mostre todos os detalhes de um agente específico da plataforma DoubleX.

1. Chame list_agents para mostrar os agentes disponíveis.
2. Pergunte qual agente o usuário quer consultar.
3. Chame get_agent com o id do agente escolhido.
4. Apresente todas as informações organizadas por seção:

   **Identificação**
   - Nome, ID, status (ACTIVE/PENDING), visibilidade (private/public), criado em

   **Modelo de IA**
   - Provider, modelo, temperatura, max tokens por resposta, max iterações de tool calling

   **Comportamento**
   - System prompt completo (sem cortes — exiba tudo)
   - Personalidade configurada (se houver)
   - Welcome message (se houver)

   **Recursos Configurados**
   - Tools ativas (lista)
   - Bases de conhecimento vinculadas
   - Habilidades (skills)
   - Agendamentos ativos

5. Ofereça ao usuário:
   - Editar o agente (/doublex:editar-agente)
   - Conversar com ele agora (/doublex:conversar)

---
Se receber erro "API key required", "401 Unauthorized" ou "Failed to connect to doublex", o token não está configurado. Oriente o usuário a rodar /doublex:setup antes de continuar.
