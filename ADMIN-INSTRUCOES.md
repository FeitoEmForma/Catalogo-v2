# Ativação do painel administrativo

O catálogo mantém sua aparência original e continua aberto para clientes. O botão **Acesso ADM** aparece no rodapé. As alterações no painel são salvas no Supabase e ficam disponíveis para todos os visitantes.

## Passo a passo

1. Crie um projeto em https://supabase.com.
2. No **SQL Editor**, execute o conteúdo de `supabase.sql`.
3. Em **Authentication > Users**, crie um usuário com seu e-mail e uma senha forte. Copie o UUID desse usuário.
4. No **SQL Editor**, execute `insert into public.admins(user_id) values ('COLE_AQUI_O_UUID');` substituindo pelo UUID real. Não inclua credenciais ou senhas no código.
5. Em **Project Settings > API** (ou **Connect**), copie a **Project URL** e a chave pública **anon/publishable**. Preencha `config.js`. **Nunca coloque a service_role ou secret key no site.**
6. No **SQL Editor**, importe os 16 produtos antigos executando as instruções SQL de `importar-produtos.sql`. Esse arquivo usa as imagens originais `produto-XX.jpeg` que já estão no GitHub Pages. Depois, novas imagens são enviadas diretamente pelo painel para o Supabase Storage.
7. Publique todos os arquivos do ZIP atualizado na raiz do mesmo repositório GitHub Pages. Aguarde a publicação e abra `admin.html` pelo link no rodapé.

**Importante:** o painel precisa do Supabase configurado para funcionar. Enquanto `config.js` estiver vazio, o catálogo original continua visível, mas o login não estará habilitado. Após configurar o Supabase, o catálogo passa a usar os registros do banco. O GitHub Pages sozinho não oferece banco de dados nem login seguro.

**Segurança:** as permissões de alteração são verificadas pelo banco (RLS), não apenas pela interface. Somente IDs registrados em `admins` podem alterar produtos. Não compartilhe sua senha. Imagens enviadas são públicas para visualização no catálogo. A exclusão de um produto remove seu registro, mas não apaga automaticamente o arquivo de imagem do Storage.
