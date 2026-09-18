# Convite de Casamento — Emilly & Lauriano

Convite digital (site de página única) para o casamento de **Emilly e Lauriano**,
em **31 de janeiro de 2027**, no **Imperial Pallace Buffet**, em Fortaleza/CE.

Basta abrir o `index.html` no navegador — não precisa instalar nada.

---

## 📁 Estrutura

```
index.html          → o convite inteiro (textos, estilos e funcionamento)
assets/
  textura.jpg       → textura de papel do fundo ✅
  monograma.png     → ⬅️ FALTA subir o monograma (PNG com fundo transparente)
  musica.mp3        → (opcional) música de reserva, caso o YouTube não abra
fotos/
  capa.jpg          → foto do casal, no topo do convite ✅
  local.jpg         → ⬅️ FALTA subir a foto do Imperial Pallace Buffet
presentes/
  01.jpg … 15.jpg   → fotos das 15 cotas de presente ✅
```

> Se alguma imagem ainda não existir, o convite **não quebra**: ele mostra um
> fundo em degradê no lugar da foto e segue funcionando normalmente. É o caso
> da foto do buffet e do monograma, que ainda não foram enviados.

---

## 🖼️ Fotos

As fotos enviadas já foram tratadas e colocadas no lugar certo. As fotos das
cotas foram montadas **inteiras** sobre um fundo desfocado delas mesmas, em vez
de recortadas: várias eram bem largas e o recorte cortaria a piada no meio
(os dois sapatinhos do "menino ou menina", a coroa, a mesa do buffet).

Ainda faltam duas, e o convite funciona normalmente sem elas:

| Arquivo | O que é | Formato sugerido |
|---|---|---|
| `fotos/local.jpg` | foto do Imperial Pallace Buffet | horizontal, 1200×800 px |
| `assets/monograma.png` | monograma do casal | PNG transparente, ~800 px de largura |

Para trocar uma foto depois, basta substituir o arquivo mantendo o mesmo nome
(tudo em minúsculo). A numeração das cotas segue a ordem da lista abaixo.

---

## 💳 Pagamentos e contatos

Está tudo configurado no bloco `CONFIG`, no topo do `<script>` do `index.html`.
Falta apenas **testar um link de cartão** (item 1) antes de enviar o convite:

1. **`infinitePayTag`** — ✅ já preenchida com `rumadevideos` (a InfiniteTag da
   conta **RUMA DE VIDEOS**, Conta Lojista CNPJ). O botão **Cartão** de cada cota
   já monta sozinho o link de pagamento com o valor daquela cota:
   `https://pay.infinitepay.io/rumadevideos/500,00/`

   > ⚠️ **Teste um link antes de enviar o convite.** Abra o convite, toque em
   > *Cartão* em qualquer cota e confira se o checkout da InfinitePay abre com o
   > **valor certo**. Se abrir com o valor errado (R$ 5,00 em vez de R$ 500,00,
   > por exemplo), é só trocar no `CONFIG` a linha
   > `infinitePayFormatoValor: 'reais'` para `'centavos'`. É a única mudança
   > necessária — os 15 links se ajustam juntos.

   **Para saber qual cota foi paga:** o link automático leva só o valor, e várias
   cotas têm o mesmo preço (R$ 500 aparece duas vezes, R$ 350 duas, R$ 250 duas,
   R$ 300 duas, R$ 400 duas). Ou seja, no extrato não dá para distinguir uma da
   outra. Se isso importar, gere os 15 links no app da InfinitePay (lá você
   escreve a descrição, ex.: *"Cota 01 — Mounjaro da Noiva"*) e cole cada um na
   cota correspondente, dentro de `PRESENTES`:

   ```js
   { id:1, nome:'Mounjaro da Noiva', ..., linkCartao:'https://pay.infinitepay.io/...' },
   ```

   O `linkCartao` tem prioridade sobre o link automático. Dá para fazer só em
   algumas cotas — as que não tiverem continuam usando o link automático.

2. **`pixChave`** — ✅ já preenchida: `+5585981331368`.
   Cada cota gera sozinha o código *Pix copia e cola* com o valor daquela cota,
   e o convidado copia com um toque.

   A chave é um telefone, então fica gravada em **formato internacional**
   (`+55` + DDD + número) — é assim que o código precisa dela para o banco
   aceitar. No convite ela aparece formatada: **(85) 98133-1368**.

   Dois campos opcionais ao lado dela:
   - `pixBanco` — ex.: `'Banco Itaú'`. Aparece embaixo da chave; vazio, some.
   - `pixTitular` — hoje `'Emilly e Lauriano'`. É o nome que vai dentro do
     código Pix. Vale conferir se bate com o **titular real da conta** da chave;
     alguns bancos mostram esse nome na hora do pagamento.

3. **`whatsapp`** — ✅ já preenchido: `5585982166345`.
   O botão *Confirmar no WhatsApp* abre a conversa com a mensagem pronta.

4. **`mapCerimonia` / `mapRecepcao`** — *(opcional)* o link curto do Google Maps
   do buffet. Se ficarem vazios, o botão "Ver no mapa" abre a busca pelo
   endereço, que já funciona.

---

## 📋 O que já está configurado

- **Noivos:** Emilly & Lauriano
- **Data:** 31 de janeiro de 2027 (domingo)
- **Horários:** convite às **15h30**, cerimônia começa às **16h**
  *(a contagem regressiva usa o horário do convite)*
- **Local:** Imperial Pallace Buffet — Rua S, 540, Mondubim, Fortaleza/CE
  *(cerimônia e recepção no mesmo endereço)*
- **Paleta:** azul serenity
- **Música:** https://youtu.be/E4a12Mxo3Kg *(toca ao abrir o convite, com botão de pausar)*
- **Frase de abertura:** "Querido e gentil leitor, há histórias que o destino tenta
  escrever. A nossa, porém, foi escrita pelas mãos do Senhor."
- **Dress code:** esporte fino — evitar branco (noiva) e tons pastéis (cortejo),
  com orientações para damas e homens
- **Manual dos convidados:** 8 tópicos em lista sanfonada
- **Lista de presentes:** 15 cotas, com **Pix** (código copia e cola gerado na
  hora, já com o valor) e **cartão** via InfinitePay (crédito parcelado, Google
  Pay e Apple Pay) — tudo sem precisar de servidor
- **Confirmação de presença:** WhatsApp (85) 98216-6345, com mensagem pronta

### As 15 cotas

| # | Cota | Valor |
|---|---|---|
| 01 | Mounjaro da Noiva | R$ 500 |
| 02 | Aula: Como Gastar com Perfumes | R$ 450 |
| 03 | Palpite Oficial: Menino ou Menina? | R$ 250 |
| 04 | Patrocínio MASTER da Lua de Mel | R$ 1.500 |
| 05 | Dia de Noiva — Pós-Casamento | R$ 600 |
| 06 | Prioridade VIP na Fila do Buffet | R$ 400 |
| 07 | Cota Amigos Pra Sempre | R$ 350 |
| 08 | Título de Parente Preferido | R$ 500 |
| 09 | Um Mimo, Porque Casar é Caro | R$ 300 |
| 10 | Cota para 01 Ano de Faxina | R$ 700 |
| 11 | Brinde: Sobrevivemos à Organização | R$ 350 |
| 12 | O Buquê é Seu | R$ 250 |
| 13 | Vale Netflix | R$ 300 |
| 14 | Mão de Vaca | R$ 150 |
| 15 | Nome na Barra do Vestido | R$ 400 |

Para mudar um texto ou valor, edite a lista `PRESENTES` no `index.html`.

---

## 🎵 Sobre a música

O convite toca o vídeo do YouTube configurado em `musicaYoutube` (sem mostrar
a imagem, só o som), começando no primeiro toque da tela — que é o que os
navegadores exigem para liberar áudio.

Se preferir não depender do YouTube, coloque um arquivo em `assets/musica.mp3`:
ele é usado automaticamente como reserva caso o vídeo não carregue.

---

## 🌐 Publicando o convite

O jeito mais simples é o **GitHub Pages**:
*Settings → Pages → Source: Deploy from a branch → branch `main`, pasta `/ (root)`*.
Em poucos minutos o convite fica no ar em
`https://<usuario>.github.io/convite-emilly-lauriano/`.
