# JORNADA — Especificação Técnica

**Tela de Recepção de Barcos | Redesign Visual Profissional**

---

## 📊 Visão Geral

**Jornada** é a tela principal onde o usuário:
- Recebe um barco com mensagens de outros navegantes
- Lê o histórico de mensagens acumuladas
- Escreve sua própria mensagem
- Envia o barco para o próximo navegante

### Proposta Visual Atual
Ambiente submarino tropical com iluminação natural — céu diurno acima, fundo do mar vivo com corais, algas e peixes. O barco "flutua" na linha d'água separando os dois mundos.

---

## 🎨 Composição Visual

### Layout por Altura
```
Tela: 1080 × 1920 px (portrait)

[  0% –  24%]  ← SKY LAYER (arquivo: jornada-sky.jpg)
[   24%]        ← WATER LINE (animação CSS)
[ 24% – 100%]  ← UNDERWATER LAYER (arquivo: jornada-under.jpg)
```

### Camada 1: Sky (Arquivo: `jornada-sky.jpg`)
**Dimensões:** 1080 × 560 px (24% da tela)  
**Formato:** JPG, qualidade 85, < 50 KB

**Conteúdo visual:**
- **Céu:** Gradiente ciano claro (topo) → azul turquesa (base)
- **Sol:** Posicionado no canto **superior esquerdo** (~15% from left, ~10% from top)
  - Círculo amarelo dourado: 140 px de diâmetro
  - Raios de sol: 8 raios triangulares saindo do círculo (tipo mandala solar)
  - Halo suave: gradiente radial semi-transparente ao redor
- **Gaivotas:** 4–5 silhuetas de gaivotas voando em formação no céu (diferentes alturas)
- **Nuvens:** 3–4 nuvens fofas e brancas, distribuídas (centro e direita)
- **Ilha à esquerda:**
  - Farol listrado: branco + faixa vermelha (estilo clássico)
  - Altura: ~80 px
  - Base com pedras e grama
  - Posição: ~12% from left, ~50% height
- **Ilha à direita:**
  - 2–3 palmeiras (copas verdes, troncos marrons)
  - Areia clara na base
  - Posição: ~85% from left
- **Horizonte:** Linha de água turquesa vibrante (~72% da altura do arquivo)
- **Reflexo de luz:** Trilha dourada da luz solar refletindo na água (sutil)

**Estilo:** Ilustração digital aquarela-like com transições suaves, cores quentes e vibração tropical. Sem textos.

---

### Camada 2: Linha d'Água (Efeito CSS/SVG)
**Arquivo:** Não — gerado por código

```css
Posição: Y = 460 px (24% de 1920)
Altura: 20 px
Efeito: Duas ondas sobrepostas (SVG ou CSS)
  - Onda 1: Branca (#FFFFFF), 80% opacidade
  - Onda 2: Ciano claro (#7EC8E3), 60% opacidade
Animação: Movimento horizontal leve (~3 s, loop infinito)
```

---

### Camada 3: Underwater (Arquivo: `jornada-under.jpg`)
**Dimensões:** 1080 × 1800 px (restante da tela)  
**Formato:** JPG, qualidade 85, < 70 KB

**Conteúdo visual:**
- **Água:** Azul vivo gradiente (topo mais claro → fundo mais escuro)
  - Topo: ~#1E90FF
  - Meio: ~#1873CC
  - Fundo: ~#0D1B2E
- **Raios de luz solar:** 5–7 feixes cônicos descendo do topo (tipo luz subaquática)
  - Cor: branco/amarelo claro, 40% opacidade
  - Espaçamento: distribuído por toda a largura
- **Corais e algas: CRÍTICO — apenas nas LATERAIS**
  - **Esquerda:** Coluna de coral colorido (vermelho, rosa, laranja) subindo
  - **Direita:** Algas verdes e marrom ondulando (tipo floresta de algas)
  - **Centro (LIVRE):** Deixar vazio/limpo para os cartões se sobreporem sem conflito visual
- **Fundo do mar:**
  - Areia clara com padrão de ondulação (não um gradiente flat)
  - Bolhas subindo (várias tamanhos, 30–50% opacidade)
- **Criaturas marinhas (fundo):**
  - 1–2 estrelas-do-mar (rosa/laranja) no fundo
  - 1 concha grande no canto inferior
  - Nada muito intrusivo — apenas cenário

**Estilo:** Ilustração luminosa e aconchegante, cores vibrantes mas não saturadas demais. Profundidade visual clara.

---

## 🚢 Componentes Interativos

### 1. Barco Principal
**Arquivo:** `boat-jornada.png` (SEPARADO)  
**Dimensões:** 569 × 768 px (exibido ~132 × 178 px na tela)  
**Formato:** PNG com fundo transparente

**Características:**
- Barquinho cartoon/game-style (não realista demais, nem infantil)
- Casco: Branco com faixa azul (#2E86AB) descendo
- Cabine/Casa: Estrutura de madeira, janela pequena, escotilha
- Vela: Branca ou creme, com padrão sutil (listras leves ou degradê)
- Bandeirinha: Vermelha no topo do mastro
- **Corda dourada:** Descendo do casco com uma argola pendendo (onde as mensagens se "penduralm")
- Sombra suave abaixo para profundidade
- **Animação:** Flutua suavemente (bobbing) — sobe/desce 2–3 px a cada 2s

**Posição na tela:**
- Horizontal: Centro (540 px)
- Vertical: ~480 px (bem na linha d'água)

---

### 2. Cartão de Mensagens (Coluna Esquerda)
**Localização:** Abaixo do barco, lado esquerdo (~10% from left)  
**Dimensões:** ~380 px de largura × altura variável

**Estrutura do cartão:**
- Fundo: `paper` (#F8F2E0)
- Borda: 3 px solid `paper-border` (#8B6F47)
- Border radius: 24 px
- Padding: 20 px
- Box shadow: 0 8px 24px rgba(139, 111, 71, 0.15)

**Conteúdo interno:**
```
┌─────────────────────────────────────┐
│ ≋ Mensagens do barco ≋              │
│                                     │
│ 12 países · 8 mensagens             │
├─────────────────────────────────────┤
│ [Mini-cartão 1] ▼                   │
│ [Mini-cartão 2]                     │
│ [Mini-cartão 3]                     │
│ ... (scroll interno)                │
└─────────────────────────────────────┘
```

**Título:** Cormorant 21 px, `text-primary`, centralizado, com decoração "≋"

**Mini-cartão (cada mensagem):**
- Fundo: #FFFFFF
- Border radius: 14 px
- Padding: 12 px 16 px
- Margin bottom: 8 px
- Box shadow: 0 2px 8px rgba(0, 0, 0, 0.08)

**Anatomia do mini-cartão:**
```
[1]  País | Data | Bandeira
     
     "Olá navegantes! Que jornada incrível..."
```

- **[1]** Círculo numerado: 22 px, cor rotativa (6 cores primárias)
- **País:** Inter 13 px, **negrito**, `text-primary`
- **Data:** Inter 11 px, `text-muted`, DD/MM/AAAA
- **Bandeira:** Emoji ou ícone SVG pequeno (16 px) à direita
- **Texto:** Inter 13 px, `text-primary`, até 500 caracteres (truncado com "...")

---

### 3. Quadro de Escrita (Coluna Direita)
**Localização:** Direita do barco, lado direito (~55% from left)  
**Dimensões:** ~380 px de largura

**Estrutura:**
- Mesmo estilo do cartão de mensagens (papel envelhecido)
- Fundo: `paper` (#F8F2E0)
- Borda: 3 px solid `paper-border` (#8B6F47)
- Border radius: 24 px
- Padding: 20 px

**Conteúdo:**
```
┌─────────────────────────────────────┐
│ ≋ Sua mensagem ≋                    │
│                                     │
│ ┌─────────────────────────────────┐ │
│ │ Escreva sua mensagem aqui...    │ │
│ │                                 │ │
│ │                                 │ │
│ └─────────────────────────────────┘ │
│                     0 / 500          │
│                                     │
│ [  Mandar seguir viagem  ]           │
│  Deixar passar                       │
└─────────────────────────────────────┘
```

**Textarea:**
- Fundo: #FFFFFF
- Borda: 2 px solid `ocean-light` (#7EC8E3) — bem visível
- Border radius: 12 px
- Padding: 12 px 16 px
- Min-height: 130 px
- Font: Inter 15 px
- Focus: Borda muda para `ocean-surface` (#2E86AB)

**Contador:** Inter 12 px, `text-muted`, canto inferior direito

**Botão "Mandar seguir viagem":**
- Pílula (`ocean-surface`)
- Largura: 220 px mínimo
- Centralizado dentro do cartão
- Habilitado com 1+ caractere

**Link "Deixar passar":**
- Inter 12 px, cor `paper-border`
- Sem decoração, hover com underline
- Centralizado abaixo do botão

---

## 🐠 Peixes Decorativos (Animados)

**Arquivo:** `fish-pack.svg` (SEPARADO, múltiplas variações)

12 peixinhos coloridos nadando pelas laterais da tela:
- 6 pela esquerda
- 6 pela direita
- Cores variadas: azul, laranja, amarelo, rosa, verde, roxo
- Tamanho: 24–36 px (pequenos)
- Animação: Movimento horizontal contínuo (tipo "nadar") — diferentes velocidades
- **Importante:** Nunca atrás dos cartões (z-index baixo)

---

## 🎬 Animações

### Chegada do Barco
```
Entrada: Desliza da ESQUERDA até o CENTRO
Duração: 400 ms
Efeito: cubic-bezier(0.34, 1.56, 0.64, 1) — mola suave
Sons: Buzina de navio (1.8 s, sintetizada)
```

### Partida do Barco
```
Saída: Desliza para a DIREITA e desaparece
Duração: 300 ms
Efeito: ease-in
```

### Estados Visuais

**Carregando:** Spinner azul (24 px) + "Consultando o horizonte..."
**Erro:** Cartão vermelho com mensagem de erro
**Vazio:** Barquinho translúcido + "O mar está calmo..." (Cormorant 22 px branca)

---

## 📱 Responsividade

| Breakpoint | Ajustes |
|-----------|---------|
| Mobile (320–480 px) | Cartões empilhados verticalmente, barco redimensiona |
| Tablet (768–1024 px) | Cartões lado a lado, espaçamento aumenta |
| Desktop (1025+ px) | Layout original mantido |

**Regra de ouro:** Background em modo "cover" — corta nas bordas, conteúdo importante no centro.

---

## 🔧 Implementação

### Estrutura HTML Sugerida
```html
<section class="jornada">
  <!-- Background layers -->
  <div class="sky-layer"></div>
  <div class="water-line"></div>
  <div class="underwater-layer"></div>
  
  <!-- Fish animation -->
  <div class="fish-container">
    <svg class="fish fish-left-1"></svg>
    <!-- ... mais peixes ... -->
  </div>
  
  <!-- Main content -->
  <div class="boat-container">
    <img class="boat" src="boat-jornada.png" alt="Barco">
  </div>
  
  <div class="messages-column">
    <!-- Cartão de mensagens -->
  </div>
  
  <div class="write-column">
    <!-- Quadro de escrita -->
  </div>
</section>
```

### CSS Variables Reutilizáveis
```css
:root {
  --jornada-sky-height: 24%;
  --jornada-water-line-y: 460px;
  --boat-size-w: 132px;
  --boat-size-h: 178px;
  --card-width: 380px;
}
```

---

## 📋 Checklist de Entrega

- [ ] `jornada-sky.jpg` (1080×560, <50 KB)
- [ ] `jornada-under.jpg` (1080×1800, <70 KB)
- [ ] `boat-jornada.png` (569×768, transparente)
- [ ] `fish-pack.svg` (múltiplas variações)
- [ ] Especificação CSS completa
- [ ] HTML preview interativo
- [ ] Animações implementadas

---

**Versão:** 1.0  
**Status:** 🎨 Pronto para redesign  
**Data:** Julho 2026
