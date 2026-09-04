# Exemplo básico de RLS multi-tenant

```sql
-- Tabela de exemplo
create table tarefas (
  id uuid primary key default gen_random_uuid(),
  tenant_id uuid not null,
  user_id uuid not null default auth.uid(),
  titulo text not null,
  concluida boolean default false
);

-- Habilita RLS
alter table tarefas enable row level security;

-- Policy de leitura: só vê tarefas do próprio tenant
create policy "leitura por tenant"
on tarefas for select
using (
  tenant_id in (
    select tenant_id from membros_tenant where user_id = auth.uid()
  )
);

-- Policy de inserção: só cria tarefas no próprio tenant
create policy "insercao por tenant"
on tarefas for insert
with check (
  tenant_id in (
    select tenant_id from membros_tenant where user_id = auth.uid()
  )
);
```
