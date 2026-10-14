# Dérica Presentes

Catálogo de roupas com filtros, busca, tamanhos, sacola persistente e solicitação de pedidos pelo WhatsApp **+55 92 98473-9015**. O cliente confirma estoque, pagamento e entrega diretamente com a loja; a aplicação não cobra pagamentos nem registra pedidos em um servidor.

## Desenvolvimento

Requer Node.js 22 ou superior.

```sh
npm ci
npm run dev
```

```sh
npm run check
```

## Cloudflare Workers

O projeto usa assets estáticos no Worker `catalogo`, configurado em `wrangler.jsonc`. Na integração Git do Worker, use:

- Diretório raiz: raiz do repositório.
- Comando de build: `npm run check`.
- Comando de deploy: `npm run deploy`.

O Wrangler serve diretamente a pasta `public`; não é necessário compilar o site. Para deploy manual, autentique sua conta Cloudflare com o fluxo oficial do Wrangler e execute `npm run deploy`. Nunca adicione tokens ao repositório.

## Catálogo real

Os seis produtos iniciais, preços e ilustrações são **demonstrativos**. Antes de divulgar a loja, substitua os itens em `public/app.js` por produtos, preços e tamanhos reais. O número de WhatsApp fica no objeto `STORE` do mesmo arquivo. Para usar fotos, substitua a função `illustration` por imagens locais na pasta `public` e inclua texto alternativo descritivo.

A sacola fica no navegador do cliente. Os preços enviados pelo WhatsApp são estimativas sujeitas à confirmação; não há controle de estoque automatizado. As fontes web são opcionais, com alternativas locais caso não carreguem.
