# Criação de um webhook no supabase via Edge Functions em TypeScript que recebe um Json e salva em uma tabela

## Instalação 
1. Instale o Docker CLI Desktop. 

2. Instalar o supabase CLI no Windows ou Linux (cmd/prompt/terminal/powershell):
```sh
npm install -g supabase
```
ou
```sh
npm install supabase --save-dev -->(executar comando direto na pasta local onde irá criar a função)
```

3. Execute o comando init para iniciar, dentro da pasta local
```sh
npx supabase init 
```

4. Fazer login no supabase
```sh
npx supabase login
```

5. Alterar o index.ts com o código do GIT.

7. Dentro do supabase: crie a tabela om o script abaixo:
```sql
create table public.webhook_data (
    id uuid default gen_random_uuid() primary key,
    payload jsonb not null,
    created_at timestamp with time zone default timezone('utc'::text, now()) not null
);
```
8. Executar o deploy dentro do supabase:
```sh
npx supabase functions deploy saveTypeFormWebhook --project-ref xyniruiylngpiffzxoxl
```

9. Caso queira remover a autorização de token, faça dentro do supabase, dentro da função:
Enforce JWT Verification
Require a valid JWT in the authorization header when invoking the function
