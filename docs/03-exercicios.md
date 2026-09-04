# 3. Exercícios

## Exercício 1
Escreva a policy de `SELECT` para uma tabela `tarefas` que possui a coluna `user_id`, garantindo que cada usuário veja apenas suas próprias tarefas.

## Exercício 2
Adapte a policy do exercício 1 para um cenário multi-tenant, onde a tabela `tarefas` tem uma coluna `tenant_id` e o usuário pertence a um tenant registrado em uma tabela `membros_tenant`.

## Exercício 3
Explique por que a `service_role` nunca deve ser usada diretamente no código do frontend de uma aplicação.

## Exercício 4 (desafio)
Escreva a policy de `INSERT` que impede um usuário de criar uma linha com `tenant_id` diferente do seu próprio tenant.
