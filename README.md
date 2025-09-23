
---

# 📚 BookShelf

## 📖 Visão Geral

O **BookShelf** é uma aplicação web moderna para gerenciamento de biblioteca pessoal.
Permite aos usuários **catalogar, organizar e acompanhar o progresso de leitura** dos seus livros de forma simples e intuitiva.

---

## 🚀 Tecnologias Utilizadas

* **Next.js 15** (App Router)
* **React 19**
* **TypeScript**
* **Tailwind CSS**
* **shadcn/ui** (biblioteca de componentes)

---

## ✨ Funcionalidades

### 1. Dashboard Principal

* Estatísticas gerais da biblioteca:

  * Total de livros cadastrados
  * Livros sendo lidos atualmente
  * Livros já finalizados
  * Total de páginas lidas
* Navegação rápida entre seções
* Design responsivo e atrativo

### 2. Biblioteca (Listagem de Livros)

* Exibição em **cards** de todos os livros cadastrados
* Busca por **título ou autor**
* Filtros por **gênero literário**
* Cada card exibe:

  * 📕 Capa do livro (com fallback)
  * ✍️ Título e autor
  * 📅 Ano de publicação
  * ⭐ Avaliação por estrelas (1–5)
  * 🏷️ Gênero como *badge*
  * 🔍 Visualizar | ✏️ Editar | ❌ Excluir

### 3. Adicionar Novo Livro

* Formulário completo:

  * **Obrigatórios**: título, autor
  * **Opcionais**: páginas totais, página atual, status de leitura, ISBN, URL da capa, gênero, avaliação, notas pessoais
* Preview da capa em tempo real
* Barra de progresso do preenchimento
* Validação e feedback visual (sucesso/erro)

### 4. Visualizar Detalhes

* Página individual para cada livro
* Exibição completa de todas as informações
* Sinopse detalhada
* Botões de **editar** e **excluir**

### 5. Editar Livro

* Formulário pré-preenchido
* Atualização em tempo real

### 6. Excluir Livro

* **Dialog de confirmação**
* Prevenção de exclusões acidentais
* Feedback visual claro

---

## 📊 Estrutura de Dados

### Modelo de Livro

```ts
{
  id: string;         // Identificador único
  title: string;      // Título (obrigatório)
  author: string;     // Autor (obrigatório)
  genre?: string;     // Gênero literário
  year?: number;      // Ano de publicação
  pages?: number;     // Total de páginas
  rating?: number;    // Avaliação 1-5
  synopsis?: string;  // Sinopse
  cover?: string;     // URL da capa
}
```

### Status de Leitura

* `QUERO_LER`
* `LENDO`
* `LIDO`
* `PAUSADO`
* `ABANDONADO`

### Gêneros Disponíveis

Literatura Brasileira, Ficção Científica, Realismo Mágico, Ficção, Fantasia, Romance,
Biografia, História, Autoajuda, Tecnologia, Programação, Negócios, Psicologia,
Filosofia, Poesia.

---

## 🖥️ Requisitos Técnicos

### Responsividade

* Mobile-first
* Grid adaptativo para listagem
* Navegação otimizada para todos os dispositivos

### Acessibilidade

* Componentes semânticos
* Navegação por teclado
* Labels apropriados em formulários
* Contraste de cores adequado

### Performance

* Lazy loading de componentes
* Otimização de imagens
* Estados de loading

### Experiência do Usuário

* Feedback visual em todas as ações
* Tratamento de erros amigável
* Design consistente

---

## 🎨 Requisitos de Interface

* **Design System:** shadcn/ui + Tailwind CSS
* **Navegação:** header/navbar, breadcrumbs e botões de voltar
* **Formulários:** validação em tempo real, mensagens de erro claras
* **Feedback:** toasts, loaders, confirmações e indicadores de progresso

---

## 📚 Dados Iniciais

O projeto inicia com **5 livros pré-cadastrados** contendo:

* Diferentes gêneros
* Diferentes anos de publicação
* Avaliações variadas
* Sinopses completas
* URLs de capas válidas

---

## 💡 Dicas de Desenvolvimento

* Comece pelo básico antes dos recursos avançados
* Teste em diferentes dispositivos e tamanhos de tela
* Código organizado e bem comentado
* Aproveite o sistema de tipos do TypeScript
* Trate erros em todas as operações
* Foque na **experiência do usuário**

---

## 📖 Recursos Recomendados

* [Documentação oficial do Next.js 15](https://nextjs.org/)
* [shadcn/ui](https://ui.shadcn.com/)
* [Guia de boas práticas do React](https://react.dev/)
* [Tailwind CSS](https://tailwindcss.com/)

---

# 📚 BookShelf – Parte 2

## 📖 Visão Geral

Na **segunda parte** do projeto **BookShelf**, você implementará duas funcionalidades essenciais que elevam a qualidade e a arquitetura da aplicação:

1. 🎨 **Sistema de Temas (Dark Mode)** – Permite aos usuários escolher entre diferentes estilos visuais.
2. 🌐 **API Routes com CRUD Completo** – Estabelece uma arquitetura robusta para operações de dados.

---

## 🌙 Parte 1 – Sistema de Temas (Dark Mode)

### ✅ Requisitos Funcionais

#### 1.1 Opções de Tema

* ☀️ **Light Mode**: Tema claro (padrão)
* 🌙 **Dark Mode**: Ideal para ambientes de pouca luz
* 🖥️ **System Mode**: Segue automaticamente a preferência do sistema operacional

#### 1.2 Toggle de Tema

* Alternância acessível em todas as páginas
* Menu dropdown com as três opções disponíveis
* Ícone correspondente ao tema ativo (☀️, 🌙 ou 🖥️)
* Transições suaves entre os temas

#### 1.3 Persistência

* Preferência salva no **localStorage**
* Carregamento automático da preferência salva
* Uso da preferência do sistema quando não houver configuração

#### 1.4 Prevenção de Flash (FOUC)

* Evitar “flash” de conteúdo não estilizado
* Aplicar tema correto **antes da renderização** do React
* Fallback seguro para ambientes sem `localStorage`

---

### ⚙️ Requisitos Técnicos

#### 1.5 Sistema de Cores

* Variáveis CSS para todas as cores
* Conjuntos separados para tema claro e escuro
* Consistência visual em ambos os modos

#### 1.6 Integração com shadcn/ui

* Todos os componentes devem suportar ambos os temas
* Contraste adequado e acessibilidade garantida

#### 1.7 Componentes Afetados

* 📕 Cards de livros
* 📝 Formulários
* 💬 Modais/Dialogs
* 🔘 Botões e links
* 📊 Tabelas e listas
* 🧭 Navegação
* 🏷️ Badges e tags

---

## 🌐 Parte 2 – Sistema de API Routes

### ✅ Requisitos Funcionais

#### 2.1 Endpoints de Livros

* **Listagem e Criação**

  * `GET /api/books` – Listar todos os livros
  * `POST /api/books` – Criar novo livro
* **Operações Individuais**

  * `GET /api/books/[id]` – Obter detalhes de um livro
  * `PUT /api/books/[id]` – Atualizar livro existente
  * `DELETE /api/books/[id]` – Remover livro

#### 2.2 Endpoints de Categorias

* `GET /api/categories` – Listar todas as categorias/gêneros
* `POST /api/categories/genres` – Adicionar novo gênero
* `DELETE /api/categories/genres/[genre]` – Remover gênero

---

### 🏗️ Requisitos de Arquitetura

#### 2.3 Migração para Server Components

* **Data Fetching no Servidor**

  * Converter páginas de listagem para *Server Components*
  * Eliminar `useState`/`useEffect` desnecessários
* **Server Actions para Mutações**

  * Criar ações para criação, atualização e exclusão
  * Revalidação automática após mutações
  * Uso de `redirect` após ações críticas

#### 2.4 Componentes Híbridos

* **Server Components (sem `"use client"`)**

  * Páginas de listagem
  * Páginas de detalhes
  * Componentes de exibição estáticos
* **Client Components (com `"use client"`)**

  * Formulários interativos
  * Componentes com estado local
  * Elementos com event handlers
  * Modais e dialogs

#### 2.5 Gerenciamento de Estado na URL

* Implementar filtros e busca via **query parameters**
* Manter filtros na URL para compartilhamento
* Preservar filtros durante a navegação

---

### ⚙️ Requisitos Técnicos

#### 2.6 Estrutura de Arquivos

```
app/api/
├── books/
│   ├── route.ts
│   └── [id]/
│       └── route.ts
└── categories/
    └── route.ts
```

---

## 🏁 Conclusão

O objetivo do **BookShelf** é proporcionar uma experiência completa e intuitiva no gerenciamento de uma biblioteca pessoal.

> **Qualidade da implementação é mais importante do que quantidade de funcionalidades extras.**

---
