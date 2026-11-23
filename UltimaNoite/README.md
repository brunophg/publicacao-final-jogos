# Última Noite

Jogo 2D de sobrevivência contra ondas de zumbis, desenvolvido no **ct.js (v5.3.1)** 

Sobreviva o máximo de ondas possível em um cenário urbano sob quarentena, gerencie suas moedas na loja de melhorias e enfrente a escuridão progressiva da noite.

---

## Grupo
**Grupo:** 17
### Integrantes
- Alceu Botelho
- Bernardo Dutra Aperibense Ottoni 
- Bruno Oliveira de Souza 
- Nicolas Reis Xavier Silva

## Principais Funcionalidades

- **Combate *Top-Down***: movimentação em 8 direções com normalização diagonal, mira livre acompanhando o cursor do mouse e sistema de disparos com colisão em obstáculos do cenário.
- **Ondas Progressivas**: a cada nova onda, aumenta a quantidade de zumbis, além da vida, dano e velocidade dos inimigos. O sistema calcula áreas livres e acessíveis para evitar *spawns* presos ou muito próximos ao jogador.
- **Campo de Visão Dinâmico**: uma camada de escuridão noturna se intensifica conforme as ondas avançam, mantendo um foco circular de visão centrado no jogador que pode ser ampliado por melhorias.
- **Loja de Melhorias entre Ondas**: ao eliminar todos os zumbis de uma onda, as moedas restantes são coletadas automaticamente e 3 melhorias aleatórias são oferecidas:
  | Melhoria | Efeito | Preço |
  | :--- | :--- | :---: |
  | **Dano +5** | Aumenta o dano dos projéteis | 15 moedas |
  | **Velocidade +20** | Aumenta a velocidade de movimento | 10 moedas |
  | **Vida Máxima +20** | Aumenta o limite máximo de vida | 20 moedas |
  | **Velocidade de Projétil +75** | Aumenta a velocidade dos tiros | 15 moedas |
  | **Campo de Visão +1** | Amplia o raio iluminado ao redor do jogador e suaviza a escuridão | 15 moedas |
- **Itens e Pontuação**: zumbis derrotados concedem pontos e podem deixar moedas e kits médicos. O recorde de pontuação é salvo automaticamente no `localStorage`.
- **Interface Completa**: menu principal, HUD com barra de vida do jogador e dos zumbis, contador de ondas/inimigos, menu de pausa com congelamento de animações e temporizadores, e tela de *Game Over*.

---

## Controles

| Ação | Tecla / Botão |
| :--- | :--- |
| Mover | `W` `A` `S` `D` ou `Setas` |
| Mirar | Mouse |
| Atirar | Botão esquerdo do mouse |
| Comprar melhoria (na loja) | `1`, `2` ou `3` |
| Pular loja | `0` |
| Pausar / Continuar | `P` ou `Esc` |

---

## Estrutura do Projeto (`UltimaNoite.ict`)

- **Salas (`Salas`)**
  - `rm_menu`: tela inicial do jogo.
  - `rm_jogo`: arena principal (`1280 × 720`).
  - `rm_gameover`: tela de fim de jogo com pontuação, onda alcançada e recorde.
- **Templates Principais (`Template`)**
  - `Jogador`: movimentação, mira, disparo, animação e atributos do soldado.
  - `Zumbi`: perseguição, ataque, dano, barra de vida e *drops*.
  - `GerenciadorOndas`: controle de ondas, geração de zonas de *spawn* e loja de melhorias.
  - `Hud`: barra de vida, placar, vinheta/campo de visão dinâmico, interface da loja e tela de pausa.
  - `Projetil`, `Moeda`, `KitMedico`, `Obstaculo`, `Cenario`, `TelaMenu`, `TelaGameOver`.

---

## Como Executar

1. Instale o **[ct.js](https://ctjs.rocks/)** (versão **5.3.1** ou compatível).
2. Certifique-se de que o arquivo `UltimaNoite.ict` esteja na pasta completa do projeto (junto com as subpastas de texturas e sons, como `img` e `snd`).
3. Abra o **ct.js**, clique em **Open Project** (*Browse*) e selecione `UltimaNoite.ict`.
4. Clique em **Launch** (botão de *Play*) para testar o jogo.
