Mostre todos os detalhes de um flow multi-agente específico da plataforma DoubleX.

1. Chame list_flows para mostrar os flows disponíveis.
2. Pergunte qual flow o usuário quer consultar.
3. Chame get_flow com o id escolhido.
4. Apresente de forma organizada:

   **Identificação**
   - Nome, ID, status (ativo/inativo), criado em, descrição

   **Diagrama do Grafo**
   Monte e exiba um diagrama em texto mostrando o fluxo de execução. Exemplos:
   - Linear: [Início] → [Agente A] → [Agente B] → [Fim]
   - Com ramificação: [Início] → [Agente A] → [Roteador] → [Agente B] / [Agente C] → [Fim]
   - Com pausa: [Início] → [Agente A ⏸] → [Agente B] → [Fim]
   (Use ⏸ para nodes com waitForUserInput=true)

   **Nodes em detalhe**
   Tabela: tipo | label | agente vinculado | pausa para usuário

   **Conexões (Edges)**
   Tabela: origem → destino | condição (se houver)

5. Ofereça ao usuário:
   - Editar o grafo (/doublex:editar-flow)
   - Enviar uma mensagem de teste (/doublex:executar-flow)

---
Se receber erro "API key required", "401 Unauthorized" ou "Failed to connect to doublex", o token não está configurado. Oriente o usuário a rodar /doublex:setup antes de continuar.
