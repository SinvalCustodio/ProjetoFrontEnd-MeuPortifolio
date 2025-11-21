# Meu Portfólio Front-end — 1_versão_MeuPortifolio

Olá — este repositório contém a versão inicial do meu portfólio front-end. Abaixo corrijo e organizo as informações técnicas para facilitar manutenção e futura migração.

Resumo

- Protótipo estático em um único arquivo: `Pagina_do_portifólio/1_versão_MeuPortifolio.html`.

- Usei Vue 3 via CDN (Composition API: createApp, ref, onMounted, v-for, v-model) e Tailwind CSS via CDN.

- Dados dinâmicos (nav, skills, projects, contatos, redes) mantidos em arrays reativas e renderizados com `v-for`.

Stack

- Vue 3 (CDN) — Composition API: const { createApp, ref, onMounted } = Vue;

- Tailwind CSS (CDN) — utilitários de estilo.

- Font Awesome — ícones.

- IntersectionObserver — animação das barras de skill.

- HTML/CSS/JS (single-file protótipo).

Onde está o código

- Arquivo principal: Pagina_do_portifólio/1_versão_MeuPortifolio.html

Como executar localmente (Windows)

- Recomendo usar um servidor HTTP simples para evitar bloqueios de CORS:

  - Python 3:

    - abra o terminal na pasta do projeto e execute:

      - python -m http.server 8000

    - abra no navegador:

      - http://localhost:8000/Pagina_do_portifólio/1_versão_MeuPortifolio.html

  - npx http-server:

    - npx http-server . -p 8000

    - abra: http://localhost:8000/Pagina_do_portifólio/1_versão_MeuPortifolio.html

Onde editar os dados

- Abra `Pagina_do_portifólio/1_versão_MeuPortifolio.html` e edite o bloco `<script>` com `createApp()`:

  - Inclua `onMounted` se for carregar dados externos: const { createApp, ref, onMounted } = Vue;

  - Arrays principais:

    - navItems — itens do menu

    - skills — { name, percentage }

    - projects — { title, description, technologies[], demoUrl, githubUrl }

    - contactForm — { name, email, message } (estado)

    - contactInfos — { icon, text, link? }

    - socialLinks — { icon, link }

Externalizar dados (recomendado)

- Crie `Pagina_do_portifólio/projects.json` (ou mova para `Pagina_do_portifólio/data/projects.json` e atualize o fetch) e carregue via fetch em `onMounted`.

- Exemplo projects.json:

```json
[
  {
    "title": "E-commerce Responsivo",
    "description": "Loja virtual com carrinho e integração de pagamento.",
    "technologies": ["Vue.js", "Tailwind CSS", "Node.js"],
    "demoUrl": "#",
    "githubUrl": "https://github.com/usuario/repo"
  }
]
```

Licença

- Atualize conforme desejado.
