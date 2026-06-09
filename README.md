# DANIversário · site do convite

Site estático (GitHub Pages) pro aniversário de 28 anos — 1 e 2 de agosto de 2026.

## Arquivos

| Arquivo | O que é |
|---|---|
| `index.html` | Página inicial (hub) com countdown e navegação. **Use o `index-atualizado.html`** — luzinhas alinhadas ao fio, "Save the Date" removido, cards na ordem Convite → Confirmar → Como chegar, todos como "Em breve". |
| `index-atualizado.html` | Versão nova do hub. Renomeie para `index.html` (veja abaixo). |
| `confirmar.html` | **Página de confirmação via Google Agenda** — pronta, mas ainda não ligada no hub. Ligue (troque o card por um link) quando o convite estiver no ar. |

> O próprio site já é o save-the-date (data + countdown na home), então não há página separada de "Save the Date". Pode tirar o `Save the Date.html` do repositório se quiser.

## Passo 1 — trocar o index

O `index.html` antigo ficou travado quando foi gerado. Do seu lado (Windows):

1. Apague o `index.html` atual.
2. Renomeie `index-atualizado.html` → `index.html`.

(Só muda uma coisa em relação ao seu original: o card "Confirmar presença" virou link pra `confirmar.html`.)

## Passo 2 — RSVP pelo Google Agenda

A página `confirmar.html` tem um botão que **adiciona o evento na agenda do convidado e confirma presença ao mesmo tempo**. Pra você receber as confirmações:

1. No Google Agenda, crie o evento (1/8/2026, 13h). Em **convidados**, ative *"Os convidados podem: ver a lista de convidados"* e deixe o evento aberto.
2. Abra o evento → **três pontos → Publicar evento** (ou copie o link do evento).
3. No arquivo `confirmar.html`, ache esta linha perto do fim e cole o link entre as aspas:
   ```js
   const EVENT_URL = "";
   ```
4. (Opcional) Pra aparecer o botão "vou dormir lá", preencha seu WhatsApp:
   ```js
   const WHATSAPP = "5511999999999";
   ```

Enquanto `EVENT_URL` estiver vazio, o botão ainda funciona — mas só adiciona na agenda do convidado, sem te devolver a confirmação. Com o link do seu evento, você vê quem respondeu "Sim".

## Passo 3 — publicar no GitHub Pages

1. Crie um repositório no GitHub (ex.: `daniversario`).
2. Suba todos os arquivos `.html` na raiz.
3. **Settings → Pages → Build and deployment → Deploy from a branch → `main` / `root` → Save.**
4. Em ~1 min o site fica em `https://SEU-USUARIO.github.io/daniversario/`.

### Observações
- Tudo é estático: sem servidor, sem banco. O RSVP vive no seu Google Agenda.
