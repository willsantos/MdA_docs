
# Documentação

Documentação para o ecossistema Metas do Ano, essa documentação é toda feita em markdown, mas está configurada para ser aberta no Obsidian para os que preferirem.
No caso da utilização do Obsidian, não esquecer de converter Wikilinks para o formato padrão do markdown.


A ideia principal é separar a documentação em um repositório a parte para cobrir todo o desenvolvimento.

  

# Objetivos do Sistema

O MdA é um sistema para definir e acompanhar suas metas durante o ano.

Baseado na [Roda da Vida](Roda%20da%20Vida.md), o objetivo é que o usuário possa dar notas para cada area da vida e depois estipular objetivos para cada area da vida.

Em um segundo momento o usuário poderá Criar e acompanhar tarefas para cada objetivo.


  

# Sistemas

  

API  [willsantos/MdA_api: Api do sistema Metas do Ano (github.com)](https://github.com/willsantos/MdA_api)

  

WEB https://github.com/willsantos/

  

Mobile

  
# Diagrama Entidade Relacionamento
![Diagrama Entidade Relacionamento v1.2](/Assets/Pasted%20image%2020230324210030.png)



# Ideias de Features

## Cadastro de usuarios
O usuário precisará se registrar para acessar o sistema, com email e uma senha que deve ser criptografada, alem disso o Id do usuario deve ser um GUID e não um int.

## Rodas da Vida

As rodas da vida terão a validade de um ano sendo duas por ano, uma no inicio e outra no final.
Assim o usuário pode avaliar como começou e como terminou aquele ano.

A segunda roda do ano deve ser gerada a partir da primeira, para não ter conflitos de dados.

É necessário ter uma propriedade para dizer se é uma roda de inicio do ano ou de revisão.

### Relacionamento entre Usuarios e Rodas da Vida

Um usuário pode ter infinitas rodas, mas o sistema deve limitar a 2 por ano, a roda não deve ser alterada depois de gravada, já que representa uma "foto" daquele momento.
Porem o usuário pode gostar de preencher ela aos poucos, então o "gravado" pode ser diferente de simplesmente salvar os dados no banco.

## Cadastro de Areas da vida

Cada Roda possui 12 areas da vida, que podem ser cadastradas no momento da criação pelo usuário e devem ser replicadas na roda de fim daquele ano.

Por padrão o sistema deve completar com as categorias padronizadas:

- Desenvolvimento Pessoal
- Profissional
- Finanças
- Lazer
- Relacionamento
- Casa
- Saúde
- Familia/Amigos
- Vida Social
- Espiritualidade
- Estudos
- Equilibrio Emocional

Cada área da vida possui um nome, e uma nota inicial e final.

### Relacionamento entre Areas da vida e Roda da vida.

Cada area da vida está relacionada a uma Roda da vida, dessa forma é possivel tirar a "fotografia" do Inicio e do fim do ano.

## Objetivos

O usuario pode definir n objetivos para cada area da vida, esses objetivos vão pautar a evolução ao longo do ano e também organizar claramente quais são os objetivos naquele ano.

O objetivo deve ter um nome, tipo de prazo, uma lista de bloqueios e uma lista de recursos necessários para alcançar.

Tipo de prazo: Curto prazo (1-2 anos), Medio prazo ( 2 - 5 anos), Longo Prazo (+5 anos)


## Projetos

Projetos são subdivisões de objetivos que o usuário pode concluir em até 1 ano.

Projetos devem ter um nome, data alvo para concluir, status (não iniciado, em progresso, concluido), progresso (% do projeto concluido)

## Tarefas

Tarefas são atividades para concluir um Projeto e são executadas em um dia, semana ou quinzena.

Tarefas tem um nome, status (não iniciado, em progresso, concluido), tempo gasto, prazo, prioridade (0-Urgente, 1-Importante, 2-Normal, 3-Quando der)


### Relacionamentos (Area>Objetivo>Projeto>Tarefa)


Acho que aqui fica um pouco mais claro, pois uma depende da outra:

- Cada area da vida pode ter infinitos objetivos.
- Cada Objetivo pode ter infinitos projetos.
- Cada Projeto pode ter infinitas Tarefas.
- Cada Tarefa concluida aumenta a porcentagem do Projeto.

## Revisão Anual


# Libs de Front-End que podemos usar


## Chartjs 
Essa parece ser uma boa lib para construir a interface da Roda da Vida 
https://www.chartjs.org/docs/latest/charts/polar.html
![Exemplo de grafico polar](/Assets/Pasted%20image%2020230323112737.png)





