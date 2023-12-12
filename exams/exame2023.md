# Perguntas Gerais

### **1. - Identify an advantage and a challenge to be taken into account when following a distributed installation for a given software component. Justify your answer.**

Vantagem de Sistema Distribuído:
- **Escalabilidade:** Uma enorme vantagem de um sistema distribuído é a grande escalabilidade. Numa arquitetura distribuída, a carga de trabalho é distribuída por vários nós ou servidores, permitindo ao sistema lidar com grandes volumes de pedidos e utilizadores. Esta escalabilidade é crucial para aplicações com um crescente número de utilizadores ou de cargas de trabalho variável, visto que assegura que podem facilmente ser adicionados mais recursos para lidar com o aumento de pedidos.

Desafio de Sistema Distribuído:
- **Complexidade:** Um desafio significativo ao seguir uma arquitetura distribuída é a complexidade de configuração e manutenção entre todos os componentes. Assegurar que todos os componentes funcionam sem falhas, partilham dados de forma eficiente e conseguem lidar com transações distribuídas pode ser um grande desafio. Para além disso, problemas como a latência da rede e os potenciais pontos de falha têm de ser levados em consideração. Manter e gerir esta complexidade requer um design arquitectural robusto, protocolos de comunicação eficientes e mecanismos tolerantes a falhas para garantir a integridade e fiabilidade do sistema.

### **2. - Give one example of a type of application or service where the use of containers is more appropriate. Justify your answer.**


Containers são particularmente adequados para aplicações que seguem uma arquitetura de microserviços. Neste tipo de aplicações, o sistema é composto por componentes folgadamente acopulados, independentemente deployable que funcionam em conjunto para constituir a funcionalidade total. Containers fornecem um ambiente leve e portável para microserviços individuais, encapsulando todas as dependências e libraries necessárias para executar o serviço. Isto permite que os microserviços sejam facilmente desenvolvidos, testados e implementados de forma independente. Containers também fornecem uma maneira eficiente de empacotar, distribuir e executar microserviços, permitindo que sejam facilmente escalados horizontalmente, simplificando a manutenção dos mesmos. Ao escolher containers para este tipo de aplicação, os developers podem usufruir de um ambiente de desenvolvimento mais consistente e fiável.

Vantagens:
- Isolamento
- Portabilidade
- Eficiência de recursos

Exemplo de uma aplicação que pode ser implementada com containers:
- Aplicação de E-commerce, composta por vários microserviços independentes, como por exemplo, um serviço de autenticação, um serviço de carrinho de compras, um serviço de gestão de pagamentos, um serviço de gestão de encomendas, etc. Isto permite aos developers desenvolver, fazer update, escalar e dar deploy destes micro serviços sem afetar a aplicação como um todo.



### **3. - Give one example of a type of application or service where the use of vris more appropriate. Justify your answer.**






### **3. - Imagine that you have to choose the best configurations for a storage system that has as main purposes to ensure high availability and, simultaneously, reduce the space occupied by the persisted data. Of the functionalities typically supported by storage systems that you studied, which ones would you suggest? Justify your answer.**

Garantir alta disponibilidade:
- **Replicação:** A replicação é uma funcionalidade que oferece alta disponibilidade ao permitir a criação de réplicas de dados noutros nós. No caso de falhas num nó, os dados podem ser recuperados a partir de uma réplica, garantindo a disponibilidade do sistema. A replicação assíncrona também permite que os dados sejam replicados para locais remotos, o que pode ser útil para fins de backup e recuperação de desastres. Para além disso, a replicação assíncrona também reduz a latência, pois as transações não precisam de ser confirmadas imediatamente em todos os nós.
- **Erasure Codes:** Os códigos de apagamento, como o Reed-Solomon, oferecem uma forma eficiente de tolerância a falhas, permitindo a recuperação de dados perdidos devido a falhas em discos ou nós. Isto contribui para a alta disponibilidade, pois o sistema pode continuar a operar mesmo na presença de falhas.


Reduzir o espaço ocupado pelos dados persistidos:
- **Compression:** A compressão reduz o tamanho dos dados, economizando espaço de armazenamento. A compressão pode ser útil para reduzir o espaço ocupado pelos dados persistidos. Esta técnica contribui para armazenar mais dados num menor espaço, o que pode ser útil para reduzir os custos de armazenamento de grandes volumes de dados.
- **Deduplication:** A deduplicação elimina cópias redundantes de dados, reduzindo ainda mais o espaço ocupado. A deduplicação pode ser útil para reduzir o espaço ocupado pelos dados persistidos. Esta técnica contribui para armazenar mais dados num menor espaço, o que pode ser útil para reduzir os custos de armazenamento de grandes volumes de dados. Enquanto que compressão é uma técnica estática, a deduplicação pode ser feita de forma dinâmica, o que permite eliminar dados redundantes à medida que são adicionados.

### **4. IT engineers that manage applications in Kubernetes environments often use monitoring tools.**
#### **4.1 Identify one reason for combining Kubernetes with monitoring tools. Justify your answer.**
#### **4.2 Identify one advantage of adding a benchmarking tool to this environment that combines Kubernetes with monitoring tools. Justify your answer.**

4.1:

- Kubernetes é uma plataforma complexa para orquestração e gestão de containers. As ferramentas de monitorização são frequentemente combinadas com Kubernetes para oferecer visibilidade e insights sobre o desempenho, estado e utilização dos containers, pods e clusters. Isto permite aos engenheiros identificar problemas, otimizar recursos, realizar troubleshooting e garantir que as aplicações estão a funcionar corretamente.

4.2:

- A adição de uma ferramenta de avaliação experimental (benchmark) ao ambiente com Kubernetes e monitorização proporciona uma abordagem holística para entender e otimizar o desempenho das aplicações. Através de testes de benchmark, os engenheiros podem simular condições de carga específicas, medir o desempenho em cenários controlados e identificar os possíveis bottlenecks. Isto é vantajoso para ajustar e otimizar o ambiente Kubernetes, fazer ajustes de escalabilidade e garantir que a infraestrutura pode lidar eficientemente com cargas de trabalho reais. Em conjunto com a monitorização, fornece uma abordagem abrangente para garantir que as aplicações estão a funcionar corretamente e a atender aos requisitos de desempenho.