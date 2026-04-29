Guie o usuário pela criação de um novo agente de IA na plataforma DoubleX.

Siga esta sequência:

1. Chame list_models para ter os modelos disponíveis em mãos antes de perguntar.

2. Faça as seguintes perguntas ao usuário (pode fazer todas de uma vez):
   - "Qual será o nome do agente?"
   - "O que esse agente vai fazer? Descreva o comportamento dele."
   - "Qual modelo de IA quer usar?" — apresente as opções agrupadas por provider.

3. Com base na descrição do comportamento, monte um system prompt profissional e
   completo se o usuário não forneceu um texto pronto. O system prompt deve:
   - Definir claramente o papel e o nome do agente
   - Descrever o tom de comunicação (formal, informal, técnico, etc.)
   - Listar as principais responsabilidades e limitações
   - Incluir instruções sobre como iniciar a conversa com o usuário

4. Chame create_agent com todos os dados coletados.

5. Confirme a criação mostrando: nome, modelo, status e os primeiros 150 caracteres
   do system prompt configurado.

6. Informe que o agente foi criado com status PENDING. Para ativá-lo, acesse o painel
   da DoubleX. Ofereça conversar com ele agora mesmo usando /doublex:conversar.

---
Se receber erro "API key required", "401 Unauthorized" ou "Failed to connect to doublex", o token não está configurado. Oriente o usuário a rodar /doublex:setup antes de continuar.
