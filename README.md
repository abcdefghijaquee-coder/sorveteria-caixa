# Caixa Sorveteria — Vercel

Aplicação de caixa simples, feita para funcionar como site estático e ser publicada gratuitamente na Vercel.

## O que já tem
- Cadastro de produtos e categorias
- Produtos vendidos por unidade e por kg
- Carrinho/pedido atual
- Controle de picolés, sorvetes, lanches, bebidas e adicionais
- Venda por dinheiro, Pix, débito e crédito
- Cálculo de troco
- Histórico de vendas
- Relatório de vendas do dia e histórico
- Total por forma de pagamento
- Integração inicial com balança USB/serial usando Web Serial API
- Funciona sem banco de dados: os dados ficam no navegador via localStorage

## Publicar na Vercel
1. Crie uma conta na Vercel.
2. Suba esta pasta para um repositório no GitHub ou importe o projeto.
3. Na Vercel, escolha o repositório e faça o deploy.
4. Não é necessário configurar build command nem banco de dados.

## Balança
A integração depende do modelo da balança. A versão incluída tenta ler balanças USB/serial que enviem o peso como texto pela porta serial, usando 9600 baud.

No computador, use Chrome ou Edge. Em celulares, Web Serial normalmente não está disponível.

Se a balança enviar um protocolo diferente, altere a função `readScale()` em `app.js` para interpretar o protocolo do fabricante.

## Importante sobre armazenamento
Esta versão é gratuita e simples, mas salva os dados no navegador do dispositivo. Se você quiser usar dois computadores/caixas e ter os mesmos produtos e vendas sincronizados, o próximo passo é ligar o app a um banco gratuito, como Supabase.

## Novidades adicionadas
- Editar produtos já cadastrados (não só adicionar/excluir)
- Confirmação antes de excluir um produto
- Backup/restauração dos dados em arquivo .json (útil antes de trocar de dispositivo/navegador)
- Exportar histórico de vendas em .csv (abre no Excel/Google Sheets)
- Recibo de venda com botão de impressão ao finalizar cada pedido
- Correção do cálculo de "vendas de hoje" para usar o fuso horário local
- Ícone e manifest.json — dá pra "Instalar" o app na tela inicial do tablet/celular do caixa e ele abre em tela cheia
