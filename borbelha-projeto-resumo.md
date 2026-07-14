# Borbelha Doceria — Site (resumo do projeto)

## O que é
Site de página única (`index.html`) para a **Borbelha Doceria**, em Curitiba/PR.
Feito em HTML/CSS/JS puro, sem frameworks — um arquivo só, com todas as imagens
embutidas em base64 (por isso o arquivo tem ~7MB).

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

## Próximo passo: deploy
- Repositório já criado: `https://github.com/borbelha/Borbelhasite.git`
- Plano: subir `index.html` no repo → importar na Vercel → apontar domínio
  `www.borbelha.com.br` (registro.br) via DNS:
  - CNAME `www` → `cname.vercel-dns.com`
  - A `@` (raiz) → `76.76.21.21`
- Ainda não foi feito o deploy — Claude não tem acesso a internet/GitHub/Vercel para
  fazer isso diretamente, precisa ser feito manualmente pelo usuário (passo a passo já
  foi passado numa mensagem anterior desta conversa).

## Possível otimização futura
O arquivo está pesado (~7MB) porque todas as imagens (logo, fachada, balcão, 41 fotos
da galeria, foto das fundadoras) estão em base64 dentro do próprio HTML. Isso funciona,
mas deixa o carregamento mais lento em conexões ruins. Se quiser, dá pra separar as
imagens em arquivos próprios (pasta `/images`) e referenciar por caminho relativo —
melhora a performance sem mudar nada visualmente.

## Onde está o arquivo
O `index.html` final (site completo, pronto pra subir) foi gerado e baixado pelo
usuário nesta conversa. Ele precisa ser reenviado/reanexado na nova sessão do
Claude Code para continuar a edição, pois o Claude não retém arquivos entre sessões.
