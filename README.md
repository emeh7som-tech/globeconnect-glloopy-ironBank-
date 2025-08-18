# Glloopy + GlobeConnect + IronBank — Ecossistema Unificado

## Estrutura
- `/glloopy` — **site público** com assistente, embeds de redes e watchdog.
- `/globeconnect` — **infraestrutura secreta** (painel admin/kill-switch/JWT/RSA/logs).
- `/ironbank` — **app pessoal** (web em `/www` + script para empacotar em APK via Capacitor).
- `/ai-orchestrator` — **orquestrador de conteúdo** (fila, tradução/posting *stubs*).

## Como rodar localmente
1. **Glloopy (3000):**
   ```bash
   cd glloopy && npm i && npm start
   ```
2. **GlobeConnect (4000):**
   ```bash
   cd globeconnect && npm i && npm start
   ```
3. **AI Orchestrator (4500):**
   ```bash
   cd ai-orchestrator && npm i && npm start
   ```
4. Ajuste variáveis em `.env` (copie de `.env.example`) conforme suas chaves.

> Integrações reais de YouTube/X/Instagram, tradução (DeepL/IA) e Supabase devem ser adicionadas preenchendo as chaves e implementando os *adapters* de cada plataforma.

## IronBank — APK
- Entre em `/ironbank`, e rode:
  ```bash
  ./build-apk.sh
  ```
  Gere o APK de debug com Android SDK/Gradle instalados.

## Segurança
- Configure `JWT_SECRET` e `KILL_SWITCH_SECRET` em produção.
- **Nunca** exponha chaves privadas no cliente.
- Use HTTPS (Vercel/Cloudflare) no site.
- Restrinja o acesso ao painel do GlobeConnect (JWT + IP allowlist).

## Próximos Passos Sugeridos
1. Conectar **Glloopy** -> **AI Orchestrator** em `/api/assistant` para fila de conteúdo.
2. Adicionar login (Supabase) para abrir o **painel secreto** só para você.
3. Implementar adapters de **YouTube/X/Instagram** para publicação real.
4. Ativar **tradução automática** por público-alvo.
5. Automatizar **métricas** e melhoria contínua (dash + relatórios).

---

> Este pacote é um esqueleto pronto para evoluir. Diga o que priorizar e eu implemento agora.
