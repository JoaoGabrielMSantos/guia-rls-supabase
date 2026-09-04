# 1. Introdução ao RLS

## O que é Row Level Security (RLS)?

RLS é um recurso do PostgreSQL (usado pelo Supabase) que permite restringir, linha por linha, quais registros de uma tabela um usuário pode ler ou modificar. Em vez de filtrar dados na aplicação, o próprio banco garante o isolamento.

## Por que RLS importa em aplicações multi-tenant?

Em um SaaS multi-tenant, vários clientes (tenants) compartilham a mesma tabela. Sem RLS, um erro de lógica na aplicação pode expor dados de um tenant para outro. Com RLS habilitado, mesmo uma query mal filtrada é bloqueada pelo banco.

## Fluxo básico

1. Habilitar RLS na tabela: `ALTER TABLE tabela ENABLE ROW LEVEL SECURITY;`
2. Criar uma policy que define quem pode ver/alterar cada linha
3. A policy geralmente compara uma coluna (ex: `tenant_id`) com o usuário autenticado (`auth.uid()`)

Sem uma policy explícita, a tabela fica bloqueada para todos por padrão — isso é intencional e é a base da segurança do modelo.
