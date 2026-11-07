# Skill: shorts animados (personagens 2D num mundo 3D) com o Claude

Skill para o Claude Code que cria shorts verticais de 55-70 s no estilo "personagens 2D chapados num mundo 3D
colorido": contorno de tinta, cidade pintada, desfoque de lente, câmera deslizando, trilha e efeitos sonoros.
Tudo é renderizado com three.js dentro do Remotion, no seu próprio computador. Não usa gerador de vídeo de IA.

## Crédito
Esta skill é baseada em **claude-animated-shorts**, de **Mr omi**: https://github.com/mromidev/claude-animated-shorts
(licença MIT, veja `LICENSE`). Todo o pipeline, as regras de estilo, os relatórios de medição e o código do exemplo
"The Bridge That Fell for a Song" são do projeto original.

## O que mudou nesta versão
- **Correções de render** em `templates/bridge/Bridge.tsx` e `templates/scripts/bridge-stills.mjs`, feitas durante a
  produção do short "José no Egito".
- **Exemplo novo:** `exemplos/jose-no-egito/`, com o roteiro em inglês e em português (fatos e fontes, fórmula
  das batidas) e as notas de produção (`NOTAS_JOSE.md`).
- **Removido:** `references/frames/` e `references/sheets/`. São quadros de vídeos de um canal de terceiros e não
  são redistribuídos aqui. Os textos `references/STYLE_BIBLE.md` e `references/reports/` (as medições, em números)
  continuam. Para comparar os seus quadros com uma referência, monte as suas próprias folhas de quadros a partir dos
  vídeos que você estudar (os scripts em `templates/scripts/` fazem isso).

## Instalar
1. Copie esta pasta para `~/.claude/skills/cartoon-3d-short/`.
2. Instale Node.js, Python 3 e ffmpeg, e um projeto Remotion com `@remotion/three`.
3. No Claude Code, diga: *"Use a skill de cartoon short e faça um short sobre …"*.

## Dicas do José no Egito
- **Render no seu PC:** o render 2K de 69 s levou cerca de 12 min (≈4 fps), com `--scale 1.3333 --concurrency=3`.
- **Placa de vídeo:** no Windows, em Configurações › Sistema › Tela › Gráficos, coloque o Chrome do Remotion em
  "Alto desempenho" (placa dedicada).
- **Disco:** defina `REMOTION_TMP` numa unidade com espaço. Cada bundle copia a pasta `public/` (~1,3 GB).
- **Versão em português:** a mesma imagem do vídeo em inglês, com a narração em `en-US-AndrewMultilingualNeural`
  (edge-tts, +25 a +30%) e legendas geradas a partir dos tempos de cada palavra.
