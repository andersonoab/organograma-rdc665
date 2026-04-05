# 🗂 Organograma RDC 665

**Ferramenta interativa de gestão do organograma regulatório** para empresas em transição de importador para fabricante de produtos médicos, conforme **RDC 665/2022 (ANVISA)**.

Roda 100% no navegador — sem servidor, sem instalação, sem dependências externas.

---

## ✨ Funcionalidades

### Organograma interativo
- Visualização em canvas com **drag & drop** de nós
- **Pan** do canvas segurando e arrastando o fundo
- Dois modos de visualização: **Importador** e **Fabricante**
- Linhas de conexão entre áreas com estilo visual por tipo de relação
- Indicação visual por status de cada área:
  - 🟢 **Já existe** — área já operante
  - 🟠 **Fortalecer** — área existente que precisa ser estruturada
  - 🔵 **Criar/Ajustar** — área nova a ser implantada
  - 🟣 **Transversal** — área de suporte transversal ao SGQ

### Busca
- Busca por **nome, cargo, matrícula ou área**
- Highlight animado nos nós e pessoas encontrados
- Navegação entre resultados com **Próximo**

### Painel lateral
- Ações regulatórias por área ao clicar em um nó
- Checklist RH detalhado com referências aos artigos da RDC 665
- Especificações da área com nível de detalhe para auditoria

### Plano de Ação RH
- Checklist regulatório com **progresso visual**
- **10 pilares de ação** para migração Importador → Fabricante
- Plano editável livre para notas e decisões de auditoria
- Referências aos Arts. 8º, 13–15, 34, 70–71 e 77 da RDC 665

### Importação de dados
| Arquivo | O que importa |
|---|---|
| `.txt` | Configuração completa do organograma (áreas, ações, checklist, plano) |
| `.xlsx / .csv` | Base de funcionários com vínculo automático às áreas |
| `.json` | Estado completo salvo anteriormente |

### Exportação
- **Exportar JSON** — salva estado completo para compartilhar
- **Exportar Excel** — base de funcionários + posições + checklist
- **Imprimir Auditoria** — relatório completo para ANVISA
- **Imprimir Organograma** — visão pessoal por área

---

## 🚀 Como usar

### Opção 1 — GitHub Pages (recomendado)
Acesse diretamente pelo navegador, sem instalar nada:
```
https://seuusuario.github.io/organograma-rdc665/
```

### Opção 2 — Local
1. Baixe os arquivos do repositório
2. Abra `index.html` direto no navegador
3. Pronto

---

## 📁 Estrutura do repositório

```
organograma-rdc665/
├── index.html               ← Organograma principal
├── gerador_txt.html         ← Gerador de arquivo de configuração TXT
└── README.md
```

---

## ⚙️ Configurando para a sua empresa

A ferramenta é **totalmente adaptável**. O conteúdo (áreas, ações, checklist) é separado do código — basta gerar um novo arquivo de configuração.

### 1. Gere o TXT da sua empresa
Abra `gerador_txt.html` no navegador:
- Cadastre as áreas da sua empresa com ID, título e status
- Adicione as ações regulatórias por área
- Edite o checklist e o plano de ação de RH
- Clique em **▶ GERAR E BAIXAR TXT**

### 2. Importe os funcionários
Prepare um `.xlsx` ou `.csv` com as colunas:

| Coluna | Descrição |
|---|---|
| `2-Diretoria` | Nome da área / diretoria |
| `9-Matricula` | Matrícula do colaborador |
| `10-Nome` | Nome completo |
| `29-Título Cargo` | Cargo |
| `38-Matrícula Gestor` | Matrícula do gestor direto |
| `39-Gestor` | Nome do gestor direto |

### 3. Vincule funcionários às áreas
Na aba **Area_Map** do Excel exportado, mapeie os nomes de área do seu sistema para os IDs do TXT. O campo `areaMatch` no TXT define a palavra-chave de correspondência.

---

## 🔒 Privacidade e armazenamento

Todos os dados ficam **apenas no seu navegador** (`localStorage`). Nenhuma informação é enviada para servidores externos. Para compartilhar o estado entre usuários, use a função **Exportar JSON** e distribua o arquivo.

---

## 📋 Referências regulatórias

| Área | Artigos RDC 665/2022 |
|---|---|
| Alta Administração / RD | Arts. 5º a 12 |
| Garantia da Qualidade (QA) | Arts. 13 a 55 |
| Controle de Qualidade (QC) | Arts. 56 a 70 |
| Compras / Fornecedores | Arts. 33 a 42 |
| Produção | Arts. 43 a 55 |
| Reclamações / Pós-mercado | Arts. 71 a 85 |
| Assistência Técnica | Arts. 63 a 70 |
| Recursos Humanos | Arts. 13–15, 34, 70, 71 e 77 |
| SST / Medicina Ocupacional | Arts. 70, 71 e 77 |

---

## 🛠 Tecnologias

- HTML5 + CSS3 + JavaScript puro — sem framework
- [SheetJS](https://sheetjs.com/) — leitura e escrita de Excel
- [IBM Plex Sans / IBM Plex Mono](https://fonts.google.com/specimen/IBM+Plex+Sans) — tipografia
- `localStorage` — persistência local de estado

---

## 📄 Licença

Uso interno. Adapte livremente para a sua empresa.
