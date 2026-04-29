Edite a estrutura (grafo) de um flow multi-agente existente na plataforma DoubleX.

1. Chame list_flows para mostrar os flows disponíveis.
2. Pergunte qual flow o usuário quer editar.
3. Chame get_flow para mostrar a estrutura atual.
4. Explique o grafo atual em linguagem simples: quais agentes participam, em qual ordem,
   e se algum pausa para aguardar resposta do usuário.
5. Pergunte o que o usuário quer alterar:
   - Adicionar um agente (em qual posição?)
   - Remover um agente
   - Mudar a ordem de execução
   - Adicionar um roteador para ramificação condicional
   - Ativar/desativar pausa para resposta do usuário em algum agente
   - Alterar condições de roteamento

6. Se o usuário quiser adicionar agente: chame list_agents para mostrar os disponíveis.

7. Monte o grafo COMPLETO com todas as alterações aplicadas:
   - Manter sempre um node "start" e pelo menos um node "end"
   - Nodes "agent" precisam de agentId válido
   - Espaçamento horizontal: positionX 100, 350, 600, 850... positionY=200
   - Nodes com pausa: config={ "waitForUserInput": true }

8. Chame update_flow_graph com o grafo novo completo (substitui o anterior inteiro).

9. Confirme mostrando o novo diagrama em texto e o que foi alterado.

---
Se receber erro "API key required", "401 Unauthorized" ou "Failed to connect to doublex", o token não está configurado. Oriente o usuário a rodar /doublex:setup antes de continuar.
