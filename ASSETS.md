# R. Amaral — Documentação de Assets

> Projeto de turismo extraído do Figma
> Arquivo: [R amaral](https://www.figma.com/proto/pxCxtAsVGsQj5MxlghwW75/R-amaral?node-id=45-4946)
> Última atualização Figma: 24/02/2026

---

## Informações do Projeto

| Campo             | Valor                          |
|-------------------|-------------------------------|
| Nome              | R. Amaral                     |
| Tipo              | Website / Landing Page        |
| Canvas            | 1440 × 5864 px (Desktop)      |
| Criado em         | 20/02/2026                    |
| Atualizado em     | 24/02/2026                    |
| File ID (Figma)   | `pxCxtAsVGsQj5MxlghwW75`      |
| Node ID (Proto)   | `45-4946`                     |

---

## Paleta de Cores

> Extrair do Figma via **Plugins > Color Palette** ou exportar tokens manualmente.

| Nome         | Hex         | Uso                        |
|--------------|-------------|----------------------------|
| Background   | `#CCCCCC`   | Fundo padrão (cinza claro) |
| Primary      | —           | A preencher                |
| Secondary    | —           | A preencher                |
| Accent       | —           | A preencher                |
| Text Dark    | —           | A preencher                |
| Text Light   | —           | A preencher                |

---

## Tipografia

> Exportar do Figma em **Inspect > Text Styles**.

| Estilo        | Família   | Peso   | Tamanho | Uso              |
|---------------|-----------|--------|---------|------------------|
| Heading 1     | —         | —      | —       | Títulos          |
| Heading 2     | —         | —      | —       | Subtítulos       |
| Body          | —         | —      | —       | Texto corrido    |
| Caption       | —         | —      | —       | Legendas         |

---

## Componentes

> Extrair do Figma em **Assets Panel > Components**.

### Header / Navbar
- [ ] Logo
- [ ] Menu de navegação
- [ ] Botão CTA principal

### Hero Section
- [ ] Imagem de fundo
- [ ] Headline
- [ ] Subtítulo
- [ ] Botão de ação

### Seções de Conteúdo
- [ ] Cards de atrações turísticas
- [ ] Galeria de imagens
- [ ] Seção de depoimentos/reviews

### Footer
- [ ] Links de navegação
- [ ] Contato
- [ ] Redes sociais

---

## Ícones

> Exportar do Figma como SVG em **Design > Export**.

| Ícone             | Formato | Localização             |
|-------------------|---------|-------------------------|
| —                 | SVG     | `assets/images/icons/`  |

---

## Imagens

| Imagem            | Formato  | Localização              | Notas        |
|-------------------|----------|--------------------------|--------------|
| Hero banner       | JPG/WebP | `assets/images/hero/`    |              |
| Galeria           | JPG/WebP | `assets/images/gallery/` |              |
| Logos / marcas    | PNG/SVG  | `assets/images/logos/`   |              |

---

## Fontes

| Fonte    | Formato  | Localização        | Fonte        |
|----------|----------|--------------------|--------------|
| —        | WOFF2    | `assets/fonts/`    | Google/Adobe |

---

## Design Exports

Os arquivos exportados do Figma devem ser organizados em:

```
design/
  exports/
    screens/      → Prints de telas completas (PNG)
    components/   → Componentes isolados (PNG/SVG)
    icons/        → Ícones (SVG)
  figma/          → Link/referência ao arquivo original
```

---

## Como Exportar do Figma

1. Abra o arquivo no Figma: [R amaral](https://www.figma.com/file/pxCxtAsVGsQj5MxlghwW75)
2. Selecione um frame ou componente
3. No painel direito, clique em **Export**
4. Escolha o formato (SVG para ícones/vetores, PNG 2x para imagens)
5. Salve na pasta correspondente conforme estrutura acima

### Via API (automatizado)

```bash
# Requer FIGMA_TOKEN no ambiente
curl -H "X-Figma-Token: $FIGMA_TOKEN" \
  "https://api.figma.com/v1/files/pxCxtAsVGsQj5MxlghwW75" \
  -o design/figma/file-data.json
```

---

## Estrutura de Pastas

```
projeto-turismo/
├── assets/
│   ├── fonts/           → Fontes web (WOFF2)
│   ├── images/
│   │   ├── hero/        → Imagens do banner principal
│   │   ├── gallery/     → Galeria de fotos
│   │   ├── icons/       → Ícones SVG
│   │   └── logos/       → Logos e marcas
│   └── videos/          → Vídeos (se houver)
├── design/
│   ├── exports/
│   │   ├── components/  → Componentes exportados
│   │   ├── screens/     → Telas completas
│   │   └── icons/       → Ícones exportados
│   └── figma/           → Referências e dados do Figma
├── docs/                → Documentação adicional
├── public/              → Arquivos públicos estáticos
├── src/
│   ├── components/      → Componentes de código
│   ├── hooks/           → Hooks customizados
│   ├── pages/           → Páginas
│   ├── styles/          → CSS/SCSS global
│   └── utils/           → Utilitários
├── ASSETS.md            → Este arquivo
└── README.md            → Documentação principal
```

---

*Para preencher as informações em aberto, acesse o arquivo no Figma e use o painel Inspect.*
