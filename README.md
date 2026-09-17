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

## ⚙️ O que ainda falta preencher

Tudo o que precisa ser editado está no topo do `<script>`, no bloco `CONFIG`
do `index.html` (por volta da linha 470). Os três itens pendentes:

1. **`pixChave`** — a chave Pix que vai receber os presentes.
   Enquanto estiver vazia, os cartões de presente aparecem **sem** o botão de Pix.
   Ao preencher, cada cota gera sozinha o código *Pix copia e cola* já com o valor.
   Escreva a chave no formato do banco: CPF só com números (`'12345678900'`),
   telefone com `+55` e DDD (`'+5585999998888'`), e-mail em minúsculo, ou a
   chave aleatória como o banco mostra. Ela aparece no convite exatamente assim.
   Preencha também `pixBanco` (ex.: `'Banco Itaú'`) e confira `pixTitular`.

2. **`whatsapp`** — o número que vai receber as confirmações,
   no formato `55` + DDD + número (ex.: `'5585999999999'`).
   Enquanto estiver vazio, a seção *Confirmação de presença* fica escondida.

3. **`mapCerimonia` / `mapRecepcao`** — *(opcional)* o link curto do Google Maps
   do buffet. Se ficarem vazios, o botão "Ver no mapa" abre a busca pelo
   endereço, que já funciona.

---

## 📋 O que já está configurado

- **Noivos:** Emilly & Lauriano
- **Data:** 31 de janeiro de 2027 (domingo)
- **Horário exibido no convite:** 15h30 *(a contagem regressiva usa o mesmo horário)*
- **Local:** Imperial Pallace Buffet — Rua S, 540, Mondubim, Fortaleza/CE
  *(cerimônia e recepção no mesmo endereço)*
- **Paleta:** azul serenity
- **Música:** https://youtu.be/E4a12Mxo3Kg *(toca ao abrir o convite, com botão de pausar)*
- **Frase de abertura:** "Querido e gentil leitor, há histórias que o destino tenta
  escrever. A nossa, porém, foi escrita pelas mãos do Senhor."
- **Dress code:** esporte fino, com orientações para damas e homens
- **Manual dos convidados:** 8 tópicos em lista sanfonada
- **Lista de presentes:** 15 cotas

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
