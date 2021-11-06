# DESMO-J: Introdução ao framework de simulação

PLANEJAMENTO DE CAPACIDADE E AVALIAÇÃO DE SISTEMAS COMPUTACIONAIS

Prof. Claudio Correa

Engenharia de Software

PUCMINAS

## Integrantes

- Bruno Marini
- Daniel Henrique Vargas
- Lucas Rotsen Pereira
- Nayane Ornelas da Conceição
- Ravi Antônio Gonçalves de Assis

## Repositório com código final

[https://github.com/raviassis/discret_event_simulation](https://github.com/raviassis/discret_event_simulation)

## Introdução

O [DESMO-J](http://desmoj.sourceforge.net/home.html) é um framework orientado a objeto para o desenvolvimento de programas de simulação de modelos, desenvolvido pelo departamento de Ciência da Computação da universidade de Hamburg. Ele é implementado em Java e da suporte para o paradigma de simulação de eventos discretos.

Para este trabalho, foi disponibilizado o código fonte de um modelo que emula o funcionamento de uma lavanderia de roupas *self-service* com apenas uma máquina de lavar. O objetivo do trabalho era editar o código para obter métricas adicionais, utilizando do instrumental que o framework do DESMO-J dispõe.

## Modelo utilizado

O modelo que o código simula é o de uma lavanderia self-service com apenas uma máquina de lavar. Segue o diagrama representando o funcionamento do modelo

![Untitled](DESMO-J%20Introduc%CC%A7a%CC%83o%20ao%20framework%20de%20simulac%CC%A7a%CC%83o%200b9939580cbd48c7a490867a82915dde/Untitled.png)

Nesse modelo temos duas entidades, o Cliente e a Máquina de lavar, sendo o Cliente o responsável por trazer o trabalho a ser atendido (lavagem de suas roupas) e a Máquina de Lavar a provedora do serviço (lavar as roupas). Temos também a fila de clientes, onde os clientes que chegam são alocados enquanto aguardam a liberação da máquina de lavar, e a ocorrência de dois eventos, o evento de chegada de cliente e o evento de término da lavagem da roupa.

## Obtenção das métricas

A atividade propôs a obtenção de quatro novas métricas para mensurar o desempenho do nosso modelo, que foram:

- utilização da máquina de lavar-roupas
    - Criação de duas métricas utilizando a classe [Count](http://desmoj.sourceforge.net/doc/desmoj/core/statistic/Count.html) do DESMO-J
        - Quantidade de vezes que a máquina de lavar foi utilizada
        - Tempo total de utilização da máquina de lavar
- tamanho médio da fila de espera para uso dessa máquina de lavar
    - Utilizando as métricas padrões para filas ([Queue](http://desmoj.sourceforge.net/doc/desmoj/core/simulator/Queue.html)) do DESMO-J
        - Qavg
- tempo médio que um cliente gasta na lavanderia
    - Utilização da classe [Tally](http://desmoj.sourceforge.net/doc/desmoj/core/statistic/Tally.html) para obter dados de média, desvio padrão, valores mínimos e máximos do tempo do cliente dentro da lavanderia
        - Tempo médio do cliente na lavanderia
- *throughput* da lavanderia
    - Utilização da classe [Tally](http://desmoj.sourceforge.net/doc/desmoj/core/statistic/Tally.html) para obter dados de média, desvio padrão, valores mínimos e máximos do tempo de lavagem da máquina de lavar
        - Throughput da lavanderia

Segue abaixo um exemplo de resultado da simulação:

![Untitled](DESMO-J%20Introduc%CC%A7a%CC%83o%20ao%20framework%20de%20simulac%CC%A7a%CC%83o%200b9939580cbd48c7a490867a82915dde/Untitled%201.png)

## Referências Bibliográficas

- **DESMO- J - A Framework for Discrete-Event Modelling and Simulation**.Disponível em: [http://desmoj.sourceforge.net/home.html](http://desmoj.sourceforge.net/home.html), último acesso em 06 de novembro de 2021.
- **The DESMO-J Tutorial**. Disponível em: [http://desmoj.sourceforge.net/tutorial/overview/0.html](http://desmoj.sourceforge.net/tutorial/overview/0.html). Último acesso em 06 de novembro de 2021.
