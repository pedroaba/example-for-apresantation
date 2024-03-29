# Prisma Apresentação

## O que é o prisma?

O prisma eh uma biblioteca javascript para interação com banco de dados como MySQL, Postgresql, SQLite, MongoDB. O prisma é constitúido o seu uso em facilitar a vida dos desenvolvedores à criarem API's Services, com banco de dados, com isso cometendo menos erros.

## O poder do prisma

O prisma têm uma forma declarativa de criar os seus models, também se você tiver uma base de dados complexa ou não, já estruturada, você precisará apenas do seu banco de dados para que o prisma monte todo o arquivo de schema com os modelos de forma legível de todo seu relacionamento dos models.

O prisma também disponibiliza as migrations em sql para que o desenvolvedor consiga alterar algo se for necessário.

## Iniciar o projeto em Prisma

Para iniciar qualquer projeto em prisma, primeiro você precisa ter o Node.JS na 12.6 ou mais. Depois basta usar o próprio gerenciador de pacotes do node ou utilizar outros. Recomendo utilizar o ***Yarn***, nesse passo a passo é usado apenas o Yarn, mas funciona com qualquer gerenciador de pacotes.

Para instalar o Yarn basta rodar `npm install -g yarn`. Já para o projeto basta seguir estes comandos.

```shell
    > yarn init -y ou npm init -y
    > yarn add prisma @prisma/client
    > yarn prisma init
```

Com esses comandos já estará com o Prisma instalado, bastando apenas configurar a uri do banco de dados, para que ele possa gerar as tabelas colocadas no `schema.prisma` ou gerar o conteúdo do schema a partir de sua base de dados com o comando `yarn prisma introspect`.  

Depois do schema pronto e gerado as migrations com o comando `yarn prisma migrate dev` (para desenvolvimento) ou `yarn prisma migrate deploy` (para produção). Chegou a hora de gerar o **client** do Prisma, para gerar ele rode `yarn prisma generate`, esse comando vai ler todo o seu arquivo ***schema.prisma*** e gerar dentro da node_modules uma "interface" para comunicação do seu backend em JavaScript/TypeScript com o seu banco de dados, cuidando de rollbacks e alguns outros erros, diminuindo assim erros no que podem acontecer em sua base de dados.

## Extras

Essa estratégia de utilizar o Prisma para acelerar o desenvolvimento de um backend, juntamente com o **NextJS** da Vercel, com suas formas de entrega de single pages applications, o seu site ganhará um desempenho tremendo. Utilizando o sistema de geração de páginas no Back **(Server Side Rendering)** ou até mesmo o sistema de revalidação deles **(Static Side Generation)**, irá diminuir o accesso ao banco e com consequência diminuir o estresse do mesmo.
