# Publicar — pacote pronto para o GitHub Pages

Estes arquivos vão para a **raiz do repositório `joseluizcosta-sys/Artigos`**
(a mesma pasta onde ficam as pastas dos papers). São estáticos e
autossuficientes — funcionam no GitHub Pages sem build.

## Arquivos deste pacote

| Arquivo | O que é |
|---|---|
| `index.html` | O site pessoal (landing). Vira a nova página inicial do `/Artigos/`. |
| `papers.json` | A lista de papers que o site lê sozinho. **Edite este ao publicar um paper novo.** |
| `cv.html` | Currículo (sem telefone), pronto para imprimir/Salvar como PDF. |
| `jose-luiz-costa.jpeg` | Foto do hero. |
| `jc-logo.png` | Marca jC (header e rodapé). |
| `favicon.ico`, `favicon-32.png`, `favicon-16.png`, `apple-touch-icon.png` | Ícones. |

> **Atenção:** o `index.html` atual do repositório (a antiga página "Coletânea")
> será substituído por este. Os papers continuam intactos — este novo index já
> os lista, lendo de `papers.json`.

## Publicar um paper novo (fluxo)

1. Suba a pasta do paper como sempre: `meu-slug/index.html` (e `meu-slug/en/` se tiver EN).
2. Adicione um bloco no **topo** do array `"papers"` em `papers.json`:
   ```json
   {
     "slug": "meu-slug",
     "hasEn": true,
     "tag":   { "pt": "White Paper · Julho 2026", "en": "White Paper · July 2026" },
     "title": { "pt": "Título", "en": "Title" },
     "dek":   { "pt": "Resumo curto…", "en": "Short summary…" }
   }
   ```
3. Commit. O site mostra o novo paper na próxima visita — sem tocar no `index.html`.

## Observações

- O site lê `papers.json` da **mesma pasta** (caminho relativo), então funciona
  onde quer que seja hospedado. Se falhar, cai numa lista embutida dos 3 papers
  atuais — nunca fica vazio.
- Idioma (PT/EN) e tema (claro/escuro) ficam salvos no navegador do visitante.
- Para gerar o PDF do currículo: abra `cv.html` e use Imprimir → Salvar como PDF.
