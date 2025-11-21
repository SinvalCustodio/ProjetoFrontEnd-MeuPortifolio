# Meu Portfólio Front-end — 1_versão_MeuPortifolio

Olá — este repositório contém a versão inicial do meu portfólio front-end. Abaixo corrijo e organizo as informações técnicas para facilitar manutenção e futura migração.

Resumo

- Protótipo estático em um único arquivo: `Pagina_do_portifólio/1_versão_MeuPortifolio.html`.
- Usei Vue 3 via CDN (Composition API: createApp, ref, onMounted, v-for, v-model) e Tailwind CSS via CDN.
- Dados dinâmicos (nav, skills, projects, contatos, redes) mantidos em arrays reativos e renderizados com `v-for`.

Stack

- Vue 3 (CDN) — Composition API: const { createApp, ref, onMounted } = Vue;
- Tailwind CSS (CDN) — utilitários de estilo.
- Font Awesome — ícones (verificar versão e disponibilidade offline).
- IntersectionObserver — animação das barras de skill (opcional).
- HTML/CSS/JS (single-file protótipo).

Onde está o código

- Arquivo principal: Pagina_do_portifólio/1_versão_MeuPortifolio.html

Como executar localmente (Windows)

- Recomendo usar um servidor HTTP simples para evitar bloqueios de CORS:

  - Python 3:

    - abra o terminal na pasta do projeto e execute:

      - python -m http.server 8000

    - abra no navegador:

      - [http://localhost:8000/Pagina_do_portifólio/1_versão_MeuPortifolio.html](http://localhost:8000/Pagina_do_portifólio/1_versão_MeuPortifolio.html)

  - npx http-server:

    - npx http-server . -p 8000

    - abra: [http://localhost:8000/Pagina_do_portifólio/1_versão_MeuPortifolio.html](http://localhost:8000/Pagina_do_portifólio/1_versão_MeuPortifolio.html)

Onde editar os dados

- Abra `1_versão_MeuPortifolio.html` e edite o bloco `<script>` com `createApp()`:

  - Inclua `onMounted` se for carregar dados externos: const { createApp, ref, onMounted } = Vue;

  - Arrays principais:

    - navItems — itens do menu

    - skills — { name, percentage }

    - projects — { title, description, technologies[], demoUrl, githubUrl }

    - contactForm — { name, email, message } (estado)

    - contactInfos — { icon, text, link? }

    - socialLinks — { icon, link }

Externalizar dados (recomendado)

- Crie `Pagina_do_portifólio/data/projects.json` e carregue via fetch em `onMounted`.

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

- Exemplo de carregamento (dentro de setup):

```javascript
const projects = ref([]);
onMounted(async () => {
  try {
    const res = await fetch('./data/projects.json');
    if (!res.ok) throw new Error('Falha ao carregar projects.json');
    projects.value = await res.json();
  } catch (err) {
    console.error(err);
  }
});
```

- Observação: o caminho `./data/projects.json` é relativo ao diretório servido pelo servidor HTTP.

Migração recomendada (Vite + componentes)

1. Inicializar projeto Vite:

   - npm create vite@latest meu-portfolio -- --template vue

   - cd meu-portfolio && npm install

2. Estruturar:

   - /src/components (Header.vue, Hero.vue, About.vue, Projects.vue, Contact.vue, Footer.vue)

   - /src/data (projects.json, social.json)

   - main.js, App.vue

3. Adicionar Vue Router (rotas) e Pinia (estado global quando necessário).

4. Configurar ESLint, Prettier, Husky + lint-staged e testes (Vitest).

Comandos úteis (PowerShell / CMD)

- Criar projeto Vite:

  - npm create vite@latest meu-portfolio -- --template vue

- Instalar dependências:

  - npm install

- Rodar dev:

  - npm run dev

- Build:

  - npm run build

- Preview:

  - npm run preview

Acessibilidade e segurança (essenciais)

- Inputs: labels associados (for / id).

- ARIA: adicionar aria-* onde necessário.

- Links externos: sempre usar target="_blank" rel="noopener noreferrer".

- Contraste: verificar WCAG AA.

- Validação: validar e sanitizar entradas no backend (quando houver).

Testes e qualidade

- Testes unitários: Vitest + @vue/test-utils.

- E2E: Playwright ou Cypress.

- Lint: ESLint + Prettier (configurar CI).

Deploy (opções)

- Vercel / Netlify: deploy automático a partir do GitHub (recomendado para Vite).

- GitHub Pages: build local e publicar `dist` no branch `gh-pages`.

- Exemplo GitHub Action (após migrar para Vite) disponível no README anterior.

Checklist pré-publicação

- [ ] Atualizar URLs '#' por links reais.

- [ ] Adicionar favicon e metatags (title, description, Open Graph).

- [ ] Testar em dispositivos móveis e rodar Lighthouse.

- [ ] Garantir HTTPS no host de produção.

Observações finais

- Mantive o protótipo simples por intenção: facilita validação rápida. Posso preparar a migração automática para Vite + componentes e gerar os arquivos iniciais (main.js, App.vue, exemplos de componentes e data JSON). Diga qual etapa quer que eu execute primeiro.

Licença
