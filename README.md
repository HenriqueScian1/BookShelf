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

## 🏁 Conclusão

O objetivo do **BookShelf** é proporcionar uma experiência completa e intuitiva no gerenciamento de uma biblioteca pessoal.

> **Qualidade da implementação é mais importante do que quantidade de funcionalidades extras.**

---
