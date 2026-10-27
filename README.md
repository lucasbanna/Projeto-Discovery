# Condoisennes – Página de Links

Página de links pessoal (estilo "link na bio") com **alternância entre modo escuro e claro**, perfil, lista de links e ícones de redes sociais. Feita com HTML, CSS e JavaScript puros, sem frameworks.

## Funcionalidades

- Foto de perfil e nome de usuário no topo.
- **Switch de tema (dark/light)** com animação de deslize; a foto de perfil também muda conforme o tema.
- Lista de links em botões com efeito *glassmorphism* (`backdrop-filter: blur`) e efeito *hover*.
- Ícones de redes sociais (GitHub, LinkedIn e Instagram) usando [Ionicons](https://ionic.io/ionicons).
- Layout responsivo (mobile first) com fundo diferente para desktop (a partir de 700px).
- Tipografia com a fonte **Inter** (Google Fonts).

## Tecnologias

| Tecnologia | Uso |
|---|---|
| HTML5 | Estrutura da página |
| CSS3 | Estilo, variáveis CSS, animações e media queries |
| JavaScript | Alternância de tema e troca da foto de perfil |
| Google Fonts | Fonte Inter |
| Ionicons 8 | Ícones das redes sociais |

## Estrutura do projeto

```
.
├── index.html
├── style.css
├── script.js
└── assets/
    ├── avatar.png              # foto de perfil (modo dark)
    ├── avatar-light.png        # foto de perfil (modo light)
    ├── moon-stars.svg          # ícone do switch (modo dark)
    ├── sun.svg                 # ícone do switch (modo light)
    ├── bg-mobile-light.jpg     # fundo mobile (modo light)
    ├── bg-desktop.jpg          # fundo desktop (modo dark)
    └── bg-desktop-light.jpg    # fundo desktop (modo light)
```

## Como executar

1. Clone ou baixe o repositório.
2. Garanta que a pasta `assets/` contenha todas as imagens listadas acima.
3. Abra o `index.html` no navegador (ou use a extensão *Live Server* do VS Code).

> É necessária conexão com a internet para carregar a fonte Inter e os ícones (Ionicons).

## Como funciona

### Troca de tema

O tema é controlado pela classe `light` na tag `<html>`:

- **Dark (padrão):** variáveis definidas em `:root`.
- **Light:** a classe `.light` sobrescreve as variáveis (`--text-color`, `--bg-url`, `--surface-color`, etc.).

A função `toggleMode()` em `script.js`, chamada pelo `onclick` do switch:

1. Adiciona ou remove a classe `light` do `<html>`.
2. Troca o `src` e o `alt` da imagem de perfil (`avatar.png` ↔ `avatar-light.png`).

O botão do switch desliza usando as animações `slide-in` e `slide-back` definidas no CSS.

### Responsividade

- Container com `max-width: 588px`, centralizado.
- Em telas com `min-width: 700px`, o fundo muda para `bg-desktop.jpg` (dark) ou `bg-desktop-light.jpg` (light).

## Personalização

- **Nome e foto:** edite o bloco `#profile` no `index.html` e substitua as imagens em `assets/`.
- **Links:** edite os itens `<li><a href="...">` dentro do `<ul>`.
- **Redes sociais:** altere os `href` e os nomes dos ícones (`<ion-icon name="...">`) no bloco `#social-links`.
- **Cores:** ajuste as variáveis em `:root` e `.light` no `style.css`.

## Pontos de atenção / melhorias

- No link do Instagram, falta a aspa de abertura no `href` (`href=https://www.instagram.com/lucas.banna/"`). Corrija para `href="https://www.instagram.com/lucas.banna/"`.
- O `alt` inicial da foto ("foto do tim maia") não corresponde ao `alt` definido pelo JS ("foto do modo dark"); vale padronizar.
- O switch é uma `<div>` com `onclick`; para melhor acessibilidade, o clique poderia ficar no `<button>` com `aria-label`.
- A regra `#profile img` aparece duplicada no CSS e pode ser unificada.
- Os links "Inscrever-se no MLW" e "Baixar meu e-book" ainda apontam para `#`.
- O tema escolhido não é salvo; é possível persistir com `localStorage`.
- O rodapé ainda contém texto genérico.

## Autor

**Lucas Eduardo da Silva Banna**

- GitHub: [@lucasbanna](https://github.com/lucasbanna)
- LinkedIn: [Lucas Eduardo da Silva Banna](https://www.linkedin.com/in/lucas-eduardo-da-silva-banna-3955053a4/)
- Instagram: [@lucas.banna](https://www.instagram.com/lucas.banna/)
