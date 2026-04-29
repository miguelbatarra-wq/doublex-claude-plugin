Mostre ao usuário todos os modelos de IA disponíveis na plataforma DoubleX.

1. Chame a tool list_models sem filtro para retornar todos os providers.
2. Apresente os resultados organizados por provider (OpenAI, Anthropic, Google, Groq).
3. Para cada modelo mostre: nome, chave (key), janela de contexto e máximo de tokens de saída.
4. Destaque modelos populares recomendados para uso geral:
   - OpenAI: gpt-4o (equilibrado), gpt-4o-mini (econômico), gpt-5.1 (mais avançado)
   - Anthropic: claude-sonnet-4-6 (equilibrado), claude-opus-4-6 (mais avançado)
   - Google: gemini-2.5-flash (rápido), gemini-2.5-pro (mais avançado)
5. Explique que a "chave" (key) é o valor exato a usar ao criar ou editar um agente.
6. Pergunte se o usuário quer criar um agente com algum desses modelos.

---
Se receber erro "API key required", "401 Unauthorized" ou "Failed to connect to doublex", o token não está configurado. Oriente o usuário a rodar /doublex:setup antes de continuar.
