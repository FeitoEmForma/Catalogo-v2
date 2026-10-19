# Feito em Forma — atualização v5.1

## Antes de tudo: faça backup
1. No GitHub, baixe o ZIP da versão atual (Code > Download ZIP).
2. No Supabase, faça backup/exportação das tabelas `products`, `completed_orders` e `admins`. Preserve também os arquivos do Storage. Não apague o projeto atual.

## Banco de dados (passo obrigatório)
1. Abra https://supabase.com/dashboard e escolha o **mesmo projeto** usado no `config.js`.
2. Abra **SQL Editor > New query**.
3. Copie todo o conteúdo de `supabase.sql` (v5.1) e execute com **Run**.
4. Confira em **Table Editor** as tabelas `products`, `completed_orders` e `admins`. Em `products`, verifique `image_urls`.
5. Em **Storage**, confira os buckets públicos `product-images` e `completed-order-images`.
6. Não execute `importar-produtos.sql` se seus produtos já estão cadastrados, para evitar duplicatas.

## Publicação no GitHub Pages
1. Abra seu repositório `FeitoEmForma-New-Page`.
2. Confirme que `config.js` continua apontando para o projeto Supabase correto. A chave publishable/anon pode ficar no navegador; **nunca publique uma secret/service_role key**.
3. Na raiz do repositório, substitua os arquivos do site pelos do ZIP v5.1. **Não envie a pasta externa `FeitoEmForma-New-Page-main` como subpasta**: envie o conteúdo dela.
4. Aguarde o GitHub Actions / Pages terminar e atualize a página (Ctrl+F5).
5. Teste em uma janela anônima e também no celular.

## Testes rápidos
- Cliente: abrir catálogo sem login, filtrar produtos, escolher quantidades, adicionar ao carrinho, editar observações e enviar orçamento pelo WhatsApp.
- ADM: entrar em `/admin.html`, cadastrar um produto com duas fotos, editar preço, ocultar e excluir um produto de teste.
- Encomendas: cadastrar uma encomenda de teste, verificar a galeria pública e depois excluir.
- Carrinho: adicionar um item, alterar o preço no ADM e abrir o carrinho novamente; deve buscar o preço atual.
- Falha de rede: com Supabase configurado, o site não deve apresentar o catálogo antigo como se os preços ainda estivessem válidos.

## Sobre fotos excluídas
A exclusão de registros no painel não apaga automaticamente arquivos do Storage, para evitar excluir fotos que ainda possam estar em uso em outros produtos ou trabalhos. Para limpar arquivos, primeiro confira se nenhuma referência a eles permanece nas tabelas, depois use Storage > bucket > selecione a imagem > Delete. **Não apague fotos compartilhadas ou fotos locais `produto-XX.jpeg` e `trabalho-XX.jpg`**.

## Limitações
- O site é estático no GitHub Pages: pedidos continuam sendo enviados pelo WhatsApp, não gravados automaticamente como pedidos recebidos no banco.
- Os preços do carrinho são reconferidos antes de abrir e enviar, mas o WhatsApp ainda é um pedido de orçamento sujeito a confirmação.
- Testes de login, banco e WhatsApp devem ser realizados no ambiente publicado: o ZIP sozinho não permite simular as credenciais e dados da sua conta.
