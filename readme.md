# CDC e KAFKA CONNECT

## O Que é Change Data Capture (CDC) ?
É bastante comum que banco de dados transacionais precisem ser replicados em um data lake, isso porque o data lake irá permitir que a sua organização importe qualquer quantidade de dados, de várias fontes, em seu formato original, economizando o tempo de definição de estruturas de dados, esquemas e transformações, e também permitindo que você execute com o framework da sua escolha as análises desses dados.

Uma forma de replicar os dados é fazer o que é chamado de replicação completa ou bulk load update, neste caso, o sistema faz a replicação de todos os dados de forma agendada, de acordo com certas condições a depender do caso de uso. Este método é relativamente simples de implementar mas possui as desvantagens de utilizar muito recurso computacional para bases de dados maiores e não fazer uma sincronização em tempo real.

Em contraste com a replicação completa da base de dados, que se torna mais e mais complicada conforme a quantidade de dados aumenta, existe o método conhecido por Change Data Capture – CDC, este processo, por sua vez, captura apenas as alterações adicionadas na base de dados entre uma versão e outra e pode transferir em tempo real essas mudanças para um outro destino, como por exemplo um data lake ou data warehouse, incluindo plataformas em nuvem como Amazon S3, Amazon Redshift, Google Cloud Storage, Snowflake e Microsoft Azure.

Na prática, o CDC sincroniza os bancos de dados instantânea e automaticamente assim que os dados de origem são alterados. Uma vez que os dados estejam replicados, é possível fazer as análises necessárias no data lake, sem sobrecarregar o banco de dados de produção. Atualmente, pela eficiência do processo de Change Data Capture, esse setup tem se tornado cada vez mais comum.

## Kafka Connect

O Apache Kafka é conhecido como um serviço de logs que se destaca pela sua capacidade de armazenamento. E os logs nada mais são do que eventos e dados que nós utilizamos para fazer com que outros serviços acessem as suas informações.

Já o Kafka Connect é uma estrutura utilizada para importar e exportar serviços. Seu objetivo é facilitar a conexão entre os nossos sistemas e aplicações de uma forma muito simples, rápida e eficiente utilizando o próprio Kafka.

## Sobre o Exemplo

O Exemplo a seguir tem como objetivo inserir em uma base Elasticsearch todas as alterações feitas em uma base de dados MySQL, conforme figura abaixo, desta forma poderemos ver em NRT (near real time) as modificações feitas no banco de dados MySQL irem para o Elasticsearch onde poderemos através do Kibana fazer vários trabalhos estatíscos e dashboards informativos.  