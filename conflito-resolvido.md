# Registro de conflito resolvido

## Onde ocorreu
Arquivo `README.md`, seção `## Objetivo`.

## Origem do conflito
A mesma linha foi editada de forma diferente em dois lugares:

- Na branch `main`, o texto foi ajustado para:
  > "Este guia apresenta os fundamentos teóricos e práticos de Row Level Security (RLS) no Supabase, aplicados a sistemas multi-tenant."

- Na branch `feature/ajuste-objetivo`, o texto foi ajustado para:
  > "Este guia apresenta uma introdução prática ao RLS no Supabase, com foco em cenários reais de aplicações SaaS multi-tenant."

Ao tentar mesclar `feature/ajuste-objetivo` em `main` com `git merge --no-ff`, o Git não conseguiu decidir automaticamente qual versão manter, pois a mesma linha foi alterada nas duas branches. Isso gerou os marcadores `<<<<<<<`, `=======` e `>>>>>>>` no arquivo.

## Como foi identificado
O comando `git merge` retornou `CONFLICT (content): Merge conflict in README.md` e `git status` mostrou o arquivo com o estado `UU` (unmerged, alterado nos dois lados).

## Decisão de resolução
Optei por unir as duas versões em uma frase só, preservando o conteúdo técnico da versão de `main` ("fundamentos teóricos e práticos... aplicados a sistemas multi-tenant") com o tom mais prático da versão da branch feature ("com foco em cenários reais de aplicações SaaS multi-tenant"), removendo os marcadores de conflito manualmente.

Resultado final:
> "Este guia apresenta os fundamentos teóricos e práticos de Row Level Security (RLS) no Supabase, com foco em cenários reais de aplicações SaaS multi-tenant."

## Como foi resolvido
1. Localizei os marcadores de conflito no `README.md`.
2. Editei a linha manualmente, combinando as duas propostas em um texto coerente.
3. Removi os marcadores `<<<<<<<`, `=======` e `>>>>>>>`.
4. Executei `git add README.md` para marcar o conflito como resolvido.
5. Finalizei com `git commit` para concluir o merge.
