# Reflexão final

## O que aprendi

Trabalhar neste projeto me deixou mais confortável com o fluxo de branches: em vez de commitar tudo direto na `main`, cada seção do guia (README, introdução, conceitos, exercícios, referências, exemplo e revisão de linguagem) foi desenvolvida em uma branch própria, com `git checkout -b` e depois integrada com `git merge --no-ff`, o que manteve o histórico rastreável por funcionalidade.

## O conflito

A parte mais reveladora foi provocar e resolver um conflito de verdade: editei a mesma linha do `README.md` (a seção "Objetivo") de formas diferentes em `main` e em `feature/ajuste-objetivo`, e ao mesclar as branches o Git não conseguiu decidir sozinho — apareceram os marcadores `<<<<<<<`, `=======` e `>>>>>>>`. Resolver manualmente, unindo o melhor dos dois textos e documentando a decisão em `conflito-resolvido.md`, deixou claro que um conflito não é um erro do Git, e sim o Git pedindo uma decisão humana.

## Sobre commits atômicos

Padronizar as mensagens (`docs:`, `feat:`, `fix:`, `chore:`) e manter cada commit restrito a uma mudança específica tornou o `git log --oneline` muito mais legível do que teria sido com commits genéricos como "mudanças" ou "final_final_2".

## Próximos passos

Pretendo reaproveitar este guia sobre RLS no meu projeto de portfólio (SaaS multi-tenant), já que o conteúdo técnico documentado aqui é diretamente aplicável ao que estou construindo com Supabase.
