Ajude o usuário a configurar o plugin da DoubleX no Claude Code.

Siga estes passos em ordem:

1. Explique que é necessário gerar um token de acesso na plataforma DoubleX.
2. Oriente: "Acesse app.doublex.ai → Configurações → API Keys → Criar nova key.
   Dê um nome como 'Meu Claude Code' e copie o token gerado (ele aparece só uma vez)."
3. Peça que o usuário cole o token aqui.
4. Após receber o token (substitua dxp_TOKEN_AQUI pelo token recebido):

   Adicionar ao perfil permanentemente (Mac/Linux):
   !echo 'export DOUBLEX_API_KEY="dxp_TOKEN_AQUI"' >> ~/.zshrc

   Ativar na sessão atual:
   !export DOUBLEX_API_KEY="dxp_TOKEN_AQUI"

   Registrar o MCP server no Claude Code com o token (use a skill update-config):
   Adicione ao settings.json em mcpServers:
   {
     "doublex": {
       "type": "http",
       "url": "https://agent.doublex.ai/mcp",
       "headers": {
         "Authorization": "Bearer dxp_TOKEN_AQUI"
       }
     }
   }

5. Rode /reload-plugins para o MCP server carregar com o token configurado.

6. Informe ao usuário:
   "Plugin configurado com sucesso! Você já pode usar todos os comandos /doublex:*."

7. Oriente o usuário a digitar /doublex:ajuda para ver tudo que pode fazer.

---
Se receber erro "API key required", "401 Unauthorized" ou "Failed to connect to doublex", o token não está configurado. Oriente o usuário a rodar /doublex:setup antes de continuar.
