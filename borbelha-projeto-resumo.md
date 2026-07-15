# Borbelha Doceria — Site (resumo do projeto)

## O que é
Site para a **Borbelha Doceria**, em Curitiba/PR, feito em HTML/CSS/JS puro, sem
frameworks. Duas páginas: `index.html` (principal) e `experiencia.html`. As imagens
ficam em `/images` (arquivos reais). **Já está no ar em www.borbelha.com.br.**

## Dados do negócio
- **Nome:** Borbelha Doceria
- **Endereço:** Av. Monteiro Tourinho, 467 — Tingui, Curitiba/PR
- **Horário:** terça a domingo, 13h às 20h (fechado às segundas)
- **WhatsApp:** 41 99211-1322 → usado no site como `5541992111322`
- **Domínio registrado:** www.borbelha.com.br (registro.br)
- **Repositório GitHub:** https://github.com/borbelha/Borbelhasite.git

## Identidade visual
- Paleta: roxo profundo (cor da logo real) + tons de lilás, rosa e dourado
- Fontes: Playfair Display (títulos), Cormorant Garamond (corpo de texto),
  Alex Brush (script/cursiva), Jost (labels/preços/UI)
- Logo real da marca recortada do material oficial (fundo transparente, embutida em base64)
- Estilo: clássico/chique, referências a jardim francês, SEM elementos "infantilizados"
  (usuária pediu para tirar ilustrações de flores fofas e usar traço fino/elegante)
- Removido a pedido da cliente: badge "Inspiração francesa" e ícones acima de
  "Feito artesanalmente" / "Ingredientes selecionados"

## Seções do site (nessa ordem)
1. **Nav** fixo (logo, links das seções, botão "Fazer Pedido")
2. **Hero** — logo, nome, tagline, horário/endereço/telefone, CTAs
3. **Nossa História** — texto da história da marca (mãe e filha, avós Jovelina e Ceci)
   + foto real das fundadoras
4. **Venha nos Visitar** — foto da fachada roxa + foto do balcão + endereço/mapa
5. **Galeria "Nossos Doces"** — 41 fotos reais dos produtos, grid com hover
6. **Encomendas** — construtor de pedido personalizado:
   - **Bolo por kg:** Dois Amores, Brigadeiro Belga, Cenoura c/ Brigadeiro Belga (R$110/kg,
     os 2 primeiros com opção de massa branca/chocolate) · Morango c/ Três Leites (R$120/kg) ·
     Marta Rocha e Red Velvet (R$130/kg) · Pistache (R$195/kg)
   - **Docinhos por cento (100un, ~18g cada):** Brigadeiro Belga, Ninho c/ Nutella, Nutella,
     Maracujá, Café (R$250/cento) · Cream Cheese c/ Geleia de Morango, Creme Brûlée (R$280/cento) ·
     Pistache (R$350/cento)
   - Cálculo de preço automático ao digitar peso/quantidade
7. **Cardápio completo** (Cookies, Signature, Mini Bolos, Potes, Especialidades, Doces
   Artesanais, Salgados, Cafés & Bebidas) — cada item tem botão "Adicionar" com stepper de
   quantidade
8. **Carrinho** — barra fixa no rodapé, modal de resumo com:
   - Nome, data desejada, horário (valida: fechado seg, só 13h-20h)
   - Retirada ou entrega
   - Forma de pagamento: integral ou 50% agora + 50% na entrega/retirada (calcula os valores)
   - Observações
   - Botão que monta a mensagem inteira e abre o WhatsApp já preenchido (não inclui frete,
     que é combinado no WhatsApp)
9. **Footer** — endereço, horário, contato, Instagram, menção ao iFood

## Deploy — CONCLUÍDO (site no ar)
- **No ar em:** https://www.borbelha.com.br (e https://borbelha.com.br redireciona pro www)
- **Repositório:** https://github.com/borbelha/Borbelhasite.git (branch `main`)
- **Hospedagem:** Vercel, conectada ao repo → cada `git push` na `main` republica sozinho
- **DNS:** feito no registro.br via "Configurar zona DNS" (NÃO por nameservers da Vercel —
  os `ns1/ns2.vercel-dns.com` só funcionam pra domínio comprado na Vercel; deu "pesquisa
  recusada"). Registros usados:
  - `A` `@` → `76.76.21.21`
  - `CNAME` `www` → `cname.vercel-dns.com`
  - Sem registro MX de propósito (não usam e-mail no domínio)
- **Fluxo pra publicar mudanças:** editar → `git add`/`commit`/`push origin main`.
  O push por HTTPS pode abrir o Git Credential Manager pedindo login do GitHub; rodar
  em background pra não travar. Identidade git local: nome "Borbelha-git",
  email belobeatriz11@gmail.com.

## Estrutura de arquivos (atual)
- `index.html` (~90KB) — página principal
- `experiencia.html` — página "A Experiência Borbelha" (jornada de degustação; ver abaixo)
- `404.html` — página de erro personalizada no estilo da marca
- `robots.txt` + `sitemap.xml` — pra indexação no Google
- `/images/` — todas as fotos em arquivos reais (não mais base64):
  `logo.png`, `favicon.png`, `apple-touch-icon.png`, `og-image.jpg` (preview de
  compartilhamento, 1200x630 da fachada), `fachada.jpg`, `balcao.jpg`, `fundadoras.jpg`,
  e `doce-01.jpg`..`doce-41.jpg` (galeria).
- `.gitignore` ignora `.claude/`

## Página "A Experiência Borbelha" (experiencia.html)
Página independente sobre a jornada de degustação presencial na lojinha. Seções: hero,
"por que uma experiência", linha do tempo com 6 passos (boas-vindas, expresso especial
com licor artesanal, trilha de 6 cookies, mini bolo abacaxi/coco, café com licor de doce
de leite, mini brownie de lembrança), "leve a experiência com você", faixa de CTA e
rodapé. Mesmo sistema visual do site.

## Melhorias já feitas (além do site original)
- **Menu em gaveta:** a barra antiga de 12 links com scroll horizontal virou um botão
  (hambúrguer) no canto que abre uma gaveta lateral, com links agrupados em "A Borbelha",
  "Cardápio" e "Pedidos". Mesmo menu no index e na experiencia.
- **Peso:** imagens extraídas de base64 → index caiu de ~6.8MB pra ~90KB.
- **SEO:** meta description, canonical, theme-color, Open Graph/Twitter (cartão de preview
  ao compartilhar no WhatsApp/Insta), JSON-LD tipo `Bakery` (endereço/horário/telefone).
- **Favicon** (logo) na aba e ícone de iOS.
- **Google Search Console:** propriedade verificada (tag `google-site-verification` no
  `<head>` das duas páginas — NÃO REMOVER). Sitemap enviado + indexação solicitada.
- **Card na home** convidando pra página da Experiência (usa o selo/logo da marca).
- **Coração roxo:** o "we ♥ you" usa um SVG (não o caractere ♥, que virava emoji vermelho
  em vários celulares e ignorava a cor). Fica no lilás da marca em qualquer aparelho.
- **Lightbox na galeria:** clicar numa foto abre ampliada, com setas/teclado/swipe e o
  nome do doce como legenda.
- **Galeria nomeada:** as 41 fotos têm o nome real do doce no `alt` (bom pra Google
  Imagens e acessibilidade). Ordem das fotos = ordem que aparece no site.
- **width/height em todas as imagens** (evita layout shift).

## Pendências (dependem da usuária, não do código)
- **Depoimentos:** adiar. Falta a usuária mandar frases REAIS de clientes (Insta/WhatsApp/
  iFood) com primeiro nome. Não inventar depoimentos.
- **Perfil da Empresa no Google** (google.com/business): cadastrado como "Borbelha
  Doceria"; confirmar se a VERIFICAÇÃO foi concluída (só aparece publicamente depois de
  verificado). É o que cria o card com mapa/foto/horário na busca — maior alavanca de
  clientes locais.
- **Link do site na bio do Instagram** (@borbelha) — traz visitas e ajuda o Google a
  descobrir o site.
- **Indexação no Google:** leva de dias a ~2 semanas; acompanhar com `site:borbelha.com.br`
  na busca. Como "borbelha" é nome único, deve rankear bem assim que indexar.
