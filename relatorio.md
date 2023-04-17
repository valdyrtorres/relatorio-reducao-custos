# RELATÓRIO DE IMPLEMENTAÇÃO DE SERVIÇOS AWS

Data: 02/05/2023
Empresa: Abstergo Industries
Responsável: Valdir Torres Borges

## Introdução
Este relatório apresenta o processo de implementação de
ferramentas na empresa Abstergo Industries, realizafo por
Valdir Torres Borges. O objetivo do
projeto foi elencar 3 serviços AWS, com a finalidade de
realizar diminuição de custos imediatos.

## Descrição do Projeto
O projeto de implementação de ferramentas foi dividido
em 3 etapas, cada uma com seus objetivos específicos a 
seguir, serão descritas as etapas do projeto:

Etapa 1:
- AWS Migration Hub
- fornece um local central para coletar dados de inventário de servidores e aplicações para avaliação
- A Abstergo possui vários servidores e aplicações on-premises, nesse sentido há ainda
necessidade de importar informações que permitam realizar um plano de migração. Pode 
também existir a necessidade de executar uma descoberta mais profunda usando o Agente
de descoberta da AWS ou o Coletor de descobertas da AWS, uma abordagem sem agente para
ambientes VMware. O objetivo do plano a ser elaborado é realizar a migração para a nuvem AWS e obter redução dos custos operacionais em 51% e um aumento da produtividade de TI em 62%, bem como uma redução de tempo de inatividade em 94%. Além desses números, existem vários benefícios que esse serviço na nuvem traz para o negócio da Abstergo.

Etapa 2:
- AWS Marketplace
- O AWS Marketplace permite que parceiros qualificados comercializem e vendam seus softwares para clientes da AWS. O AWS Marketplace é uma loja de software on-line que ajuda os clientes a encontrar, comprar e começar a usar imediatamente o software e os serviços executados na AWS.
- A Abstergo nesse início precisa de quatro instâncias reservadas r4.large para migrar paulatinamente servidores e aplicações prioritárias. Nesse sentido, se encontrar instâncias no AWS Marketplace com um desconto de 75% em comparação com os preços sob demanda, vai haver redução de custos pois a AWS o momento vende o mesmo tipo de instância reservada com um desconto de 62%.
Com o AWS Marketplace é possível comprar instâncias reservadas padrão com preços muito mais acessíveis em comparação com a compra diretamente da AWS. A razão para isso é simples; as empresas às vezes têm instâncias supérfluas de que não estão mais sendo usadas e ainda pagam por isso. Reduzir o preço de tabela é uma ótima maneira de acelerar o processo de venda.


Etapa 3:
- AWS Lambda
- O AWS Lambda é um serviço de computação que executa suas aplicações em um modelo serverless, em que é possível desenvolver sem a necessidade de se preocupar com servidores. Além disso, é possível utilizar as principais linguagens do mercado, como Java, Pyhton, Node.JS, .NET Core, e Go, podendo expandir essa lista para outras linguagens utilizando um custom Lambda Runtime, adicionando suporte até para COBOL.

Com o Lambda você só se paga o que é consumido para executar sua função. Não é necessário pagar por capacidade ociosa e, por fim permite publicar a aplicação de forma mais ágil. 
- Na migração, além de migrar aplicações legadas, como a Abstergo é muito dinâmica, surge
a necessidade de novas apliações todo momento para atender o negócio e nesse sentido,
muitos objetivos podem ser atendidos por aplicações baseadas em pequenas funções, com uma responsabilidade única iniciada a partir de eventos em vez de aplicações web, pois em muitos casos da Abstergo, basta o código implementar somente o que é necessário para ser executado, e aí o seriço de AWS Lambda atende plenamente. Abaixo, segue os benefícios do Lambda:

- Quantidade de código reduzida: Ao contrário de uma aplicação web MVC, onde temos que configurar conexões com banco de dados, configurar rotas, entre outros, podemos ir direto ao ponto e executar só o que é necessário no Lambda. O gerenciamento de rotas, bem como conexões com o banco de dados, e outras configurações são delegados para outros serviços, como um API Gateway, e são configurados fora do seu código.

- Escalabilidade instantânea: Para os casos onde nossa função recebe um pico de acessos, é possível escalar automaticamente sua função para atender um número maior de clientes. Como a AWS é responsável por gerenciar nossa infraestrutura, podemos delegar essa responsabilidade sem precisar se preocupar alocar previamente mais servidores.

- Sem cobrança de recursos ociosos: Para soluções com tráfego pequeno ou pouco constante, temos um grande potencial economia, pois com o Lambda nós não precisamos pagar por recursos ociosos de uma EC2, mesmo com a menor máquina possível.

Nota importante:
Quando não utilizar Lambda:
Existem algumas situações onde não é interessante utilizar Lambda. A primeira situação é rodar uma aplicação web tradicional. Você até consegue fazer isso, mapeando os eventos enviados com uma requisição web que sua aplicação utiliza, porém você estará subutilizando o potencial do Lambda, publicando uma aplicação completa dentro de uma única função e executando trechos de código que podem ser redundantes, como a configuração de rotas.

Processos de longa duração também não são recomendados. O tempo limite de execução de uma função é de 15 minutos. Isso pode acontecer ao processar um grande volume de dados de uma só vez. O ideal nesse caso é quebrar esse processo em partes menores, e executar somente uma unidade por função, ao invés de processar várias unidades de uma vez.

Uma função lambda também não tem acesso a um disco permanente. A manipulação de arquivos pelo lambda acontece em um disco efêmero e de baixa capacidade, tornando impossível manipular arquivos muito grandes numa função. Dessa forma é necessário recorrer a um serviço de armazenamento externo como o S3.

Por fim, temos que considerar o vendor lock-in. Em outras palavras, ao desenvolver uma função lambda não será possível migrar o código para outro provedor no futuro. Para migrar o Lambda para Azure Functions, por exemplo, posteriormente você precisa reimplementar toda a lógica que trata os eventos e suas integrações com outros serviços. Praticamente, você irá criar uma nova função. 

## Conclusão
A implementação de ferramentas na empresa Abstergo tem como esperado redução de custos inerentes da utitlização de cloud após a migração,
emprego melhor e otimizado com obtenção instências e softwares no AWS Marketplace e aplicações construídas sem servidor com benefícios 
advindos dessa tecnologia o que aumentará a eficiência e a produtividade da
empresa. Recomenda-se a continuidade da utilização das
ferramentas implementadas e a busca por novas
tecnologias que possam melhorar ainda mais os processos
da empresa.

## Anexos
https://aws.amazon.com/pt/cloud-migration/ acessado em 17/04/2023
https://aws.amazon.com/marketplace
https://aws.amazon.com/pt/migration-hub/features/?nc=nsb&pg=ln
https://aws.amazon.com/pt/lambda/
https://www.treinaweb.com.br/blog/o-que-e-aws-lambda


Assinatura do Responsável pelo Projeto:

Valdir Torres Borges