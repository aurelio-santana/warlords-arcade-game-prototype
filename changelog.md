# Changelog

## Alterações para deploy e apresentação ME 2026

- 1401a1e — Alterada a rota principal de /monolito para /play; desativada a integração de login Google, mantendo o login e o cadastro convencionais; organizado exemplos de variáveis de ambiente e remoção ts-node da configuração do PM2. Alterações em App.tsx e ecosystem.config.js.

- df87c3d e 1d663e4 — Predição configurável: adicionada a variável REACT_APP_ENABLE_CLIENT_PREDICTION para testar movimentos com ou sem predição local. Com a predição desligada, o cliente envia o movimento ao servidor sem aplicar primeiro a simulação local; a reconciliação da posição do próprio jogador também fica condicionada à opção. Veja WebSocketContext.tsx e frontend/.env.example.

- 43ba7c5 — Interpolação configurável: acrescentou opções para habilitar ou desabilitar a interpolação de jogadores e bola. Desligada, a posição é atualizada diretamente; ligada, o jogo interpola até a posição recebida. Isso afeta renderScreen.ts e o tratamento de mensagens em WebSocketContext.tsx.

- 025763a — Endereços de deploy: passou o CORS do backend a usar DOMAIN_ADDRESS e configurou o WebSocket do frontend para usar REACT_APP_DOMAIN_ADDRESS e o caminho /ws. Alterações em backend/src/index.ts e WebSocketService.ts.

Observações: os exemplos de ambiente definem as opções de predição e interpolação como true, preservando esses comportamentos quando o exemplo é usado como base; se as variáveis forem omitidas, o código as considera desligadas. 