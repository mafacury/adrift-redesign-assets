# Adrift — Redesign Assets & Components

**Versão 1.0 · Julho/2026**

Repositório centralizado para redesign visual do Adrift — especificações técnicas, componentes interativos e prompts para geração de ilustrações.

## 📁 Estrutura

```
adrift-redesign-assets/
├── /specs/                     # Especificações técnicas detalhadas
│   ├── jornada-spec.md         # Tela Jornada (recepção de barcos)
│   ├── mapa-spec.md            # Tela Mapa (acompanhamento de rotas)
│   ├── pier-spec.md            # Tela Pier (lançamento de barcos)
│   └── design-system.md        # Sistema de design unificado
│
├── /illustrations/             # Guias para geração de arte
│   ├── prompts-nano-banana.md  # Prompts otimizados para IA
│   ├── color-palette.md        # Paleta de cores e tokens
│   └── visual-style.md         # Tom visual e referências
│
├── /components/                # Componentes prontos para código
│   ├── jornada/
│   │   ├── index.html          # Preview interativo
│   │   ├── styles.css          # Estilos
│   │   ├── components.svg      # Elementos vetoriais
│   │   └── README.md           # Guia de uso
│   │
│   ├── mapa/
│   │   ├── index.html
│   │   ├── styles.css
│   │   ├── components.svg
│   │   └── README.md
│   │
│   └── pier/
│       ├── index.html
│       ├── styles.css
│       ├── components.svg
│       └── README.md
│
├── /assets/                    # Elementos reutilizáveis
│   ├── icons/                  # Ícones SVG
│   ├── boats/                  # Variações de barcos
│   ├── decorative/             # Elementos decorativos
│   └── textures/               # Texturas e padrões
│
└── README.md                   # Este arquivo
```

## 🎨 Telas Cobertas

- **Jornada** — Recepção de barcos, leitura de mensagens, envio do barco
- **Mapa** — Acompanhamento de rotas, estatísticas, histórico
- **Pier** — Lançamento de novo barco, escrita de mensagem inicial

## 🚀 Como Usar

### 1. Visualizar Componentes
Abra qualquer arquivo `index.html` em `/components/` em um navegador para ver o preview interativo.

### 2. Gerar Ilustrações
Consulte `/illustrations/prompts-nano-banana.md` para os prompts otimizados.

### 3. Integrar no VS Code
Cada componente está separado em:
- HTML (estrutura)
- CSS (estilos)
- SVG (elementos vetoriais)

Copie e adapte conforme necessário para seu projeto React.

## 📋 Especificações Técnicas

| Tela | Resolução | Fundo | Componentes |
|------|-----------|-------|------------|
| Jornada | 1080×1920 | Tropical (2 arquivos) | Barco, cartões, peixinhos |
| Mapa | 1280×628 | Pergaminho | Pinos, rotas, painel |
| Pier | 1080×1920 | Golden Hour | Formulário, veleiro |

## 🎯 Próximas Etapas

- [ ] Gerar ilustrações com Nano Banana
- [ ] Revisar especificações técnicas
- [ ] Testar componentes em diferentes resoluções
- [ ] Integrar com React/Expo
- [ ] Adicionar animações
- [ ] Otimizar peso de imagens

## 📞 Notas

- Todos os componentes são **mobile-first**
- Texto é **renderizado por código** (nunca embutido nas imagens)
- Paleta de cores segue tokens do design system
- Ícones são SVG customizado (sem bibliotecas prontas)

---

**Status:** 🚧 Em desenvolvimento  
**Última atualização:** Julho 2026
