Guie o usuário pela criação de um flow multi-agente na plataforma DoubleX.

1. Chame list_agents para ter os agentes disponíveis em mãos antes de perguntar.

2. Faça as seguintes perguntas ao usuário:
   - "Qual será o nome do flow?"
   - "O que esse flow vai fazer? Descreva o processo de atendimento."
   - "Quais agentes vão participar e em qual ordem?"
   - "Algum agente deve pausar para esperar resposta do usuário antes de continuar?"

3. Crie o flow com create_flow usando nome e descrição.

4. Monte o grafo com update_flow_graph seguindo estas regras:
   - Node "start": id="node-start", label="Início", positionX=100, positionY=200
   - Nodes "agent": um para cada agente, posições em 350, 600, 850... positionY=200
     - Se deve pausar para usuário: config={ "waitForUserInput": true }
   - Node "end": id="node-end", label="Fim", última posição, positionY=200
   - Edges conectando todos em sequência

5. Confirme mostrando o diagrama do flow em texto:
   [Início] → [Agente 1] → [Agente 2] → [Fim]
   Indique quais nodes têm pausa para usuário com "(⏸ aguarda resposta)".

6. Ofereça testar o flow agora com /doublex:executar-flow.

---
Se receber erro "API key required", "401 Unauthorized" ou "Failed to connect to doublex", o token não está configurado. Oriente o usuário a rodar /doublex:setup antes de continuar.
