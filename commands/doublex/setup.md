Ajude o usuário a configurar o plugin da DoubleX no Claude Code.

Siga estes passos em ordem:

1. Explique que é necessário gerar um token de acesso na plataforma DoubleX.
2. Oriente: "Acesse app.doublex.ai → Configurações → API Keys → Criar nova key.
   Dê um nome como 'Meu Claude Code' e copie o token gerado (ele aparece só uma vez)."
3. Peça que o usuário cole o token aqui.
4. Após receber o token, execute automaticamente os comandos abaixo para configurar
   (substitua dxp_TOKEN_AQUI pelo token recebido):

   Para adicionar ao perfil permanentemente (Mac/Linux):
   !echo 'export DOUBLEX_API_KEY="dxp_TOKEN_AQUI"' >> ~/.zshrc

   Para ativar na sessão atual:
   !export DOUBLEX_API_KEY="dxp_TOKEN_AQUI"

   Para verificar se foi configurado:
   !echo "Token configurado: $DOUBLEX_API_KEY"

5. Informe ao usuário:
   "Token configurado com sucesso! Para garantir que funciona em todas as sessões,
   reinicie o Claude Code uma vez. Após reiniciar, o plugin estará pronto."

6. Oriente o usuário a digitar /doublex:ajuda para ver tudo que pode fazer.

---
Se receber erro "API key required", "401 Unauthorized" ou "Failed to connect to doublex", o token não está configurado. Oriente o usuário a rodar /doublex:setup antes de continuar.
