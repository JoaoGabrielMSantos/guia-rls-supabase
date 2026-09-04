# 2. Conceitos essenciais

## Policies (políticas)

Uma policy define uma regra de acesso para operações específicas (`SELECT`, `INSERT`, `UPDATE`, `DELETE`).

```sql
CREATE POLICY "usuarios veem apenas seus dados"
ON tarefas
FOR SELECT
USING (auth.uid() = user_id);
```

## auth.uid()

Função do Supabase que retorna o ID do usuário autenticado na sessão atual. É a base para amarrar linhas da tabela ao usuário (ou ao tenant) correto.

## Roles

O Supabase usa roles do PostgreSQL (`anon`, `authenticated`, `service_role`) para diferenciar o nível de acesso. `service_role` ignora RLS — por isso nunca deve ser exposta no frontend.

## Isolamento multi-tenant

Para multi-tenant, normalmente adiciona-se uma coluna `tenant_id` (ou `organization_id`) e a policy compara essa coluna com o tenant do usuário logado, geralmente obtido de uma tabela de membros.
