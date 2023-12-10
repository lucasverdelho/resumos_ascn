# Teste 2023

### **1. - Durante o semestre foram utilizados diferentes componentes de software, tais como o Swap, Ghost, MySQL, e Redis, que podiam ser configurados e instalados seguindo uma arquitetura distribuída. Indique uma vantagem e um desafio a ter em conta quando se pretende seguir uma instalação distribuída para um dado componente de software. Justifique a sua resposta.**

Vantagem:
- **Escalabilidade:** uma vantagem significativa ao seguir uma arquitetura distribuida, por exemplo, para o MySQL, é a capacidade de escalabilidade horizontal. Isto permite distribuir a carga entre vários nós, facilitando a gestão de grandes volumes de dados e aumentando o desempenho à medida que mais recursos são necessários. Isto é particularmente útil em cenários onde o volume de dados ou o número de utilizadores pode aumentar significativamente.

Desafio:
- **Complexidade de configuração e Manutenção:** Coordenar e manter a consistência entre diferentes nós pode ser mais complexo do que gerir um sistema centralizado. Questões como sincronização, garantia de consistência e resolução de conflitos devem ser consideradas. Para além disso, a administração de múltiplos componentes distribuídos pode exigir um conhecimento mais aprofudndado e recursos dedicados.

### **2. - Embora ambas sejam consideradas tecnologias de virtualização, máquinas virtuais e containers adequamse a diferentes tipos de aplicações e serviços. Indique um tipo de aplicação ou serviço onde é mais apropriada a utilização de containers. Justifique a sua resposta.**

Microserviços:
- Containers são mais apropriados para ambientes onde a aplicação é composta por microserviços independentes. Em arquitetura de microserviços, a aplicação é dividida em pequenos serviços modulares que podem ser desenvolvidos, implementados e escalados de forma independente. Containers oferecem um ambiente leve e isolado que facilita um deployment consistente e rápido desses serviços. Containers também fornecem uma maneira eficiente de empacotar, distribuir e executar microserviços, permitindo que sejam facilmente escalados horizontalmente, simplificanto a manutenção dos mesmos. Ao escolher containers para este tipo de aplicação, os developers podem usufruir de um ambiente de desenvolvimento mais consistente e fiável.

### **3. - Imagine que tem de escolher as melhores configurações para um sistema de armazenamento que tem como principais propósitos garantir alta disponibilidade e, simultaneamente, reduzir o espaço ocupado pelos dados persistidos. Das funcionalidades tipicamente suportadas por sistemas de armazenamento que estudou, quais é que sugeria? Justifique a sua resposta**

Garantir alta disponibilidade:
- **Replicação Assíncrona:** A replicação assíncrona é uma funcionalidade que oferece alta disponibilidade ao permitir a criação de réplicas de dados noutros nós. No caso de falhas num nó, os dados podem ser recuperados a partir de uma réplica, garantindo a disponibilidade do sistema. A replicação assíncrona também permite que os dados sejam replicados para locais remotos, o que pode ser útil para fins de backup e recuperação de desastres. Para além disso, a replicação assíncrona também reduz a latência, pois as transações não precisam de ser confirmadas imediatamente em todos os nós.
- **Erasure Codes:** Os códigos de apagamento, como o Reed-Solomon, oferecem uma forma eficiente de tolerância a falhas, permitindo a recuperação de dados perdidos devido a falhas em discos ou nós. Isto contribui para a alta disponibilidade, pois o sistema pode continuar a operar mesmo na presença de falhas.

Reduzir o espaço ocupado pelos dados persistidos:
- **Compressão e Deduplicação:** A compressão reduz o tamanho dos dados, economizando espaço de armazenamento. A deduplicação elimina cópias redundantes de dados, reduzindo ainda mais o espaço ocupado. Estas funcionalidades podem ser úteis para reduzir o espaço ocupado pelos dados persistidos. Ambas as técnicas contribuem para armazenar mais dados num menor espaço, o que pode ser útil para reduzir os custos de armazenamento de grandes volumes de dados. Enquanto que compressão é uma técnica estática, a deduplicação pode ser feita de forma dinâmica, o que permite eliminar dados redundantes à medida que são adicionados.


### **4. - Os engenheiros informáticos responsáveis por gerir aplicações em ambientes Kubernetes recorrem muitas vezes a ferramentas de monitorização.**
#### **4.1 Indique uma das razões pela qual as Kubernetes são frequentemente combinadas com ferramentas de monitorização. Justifique a sua resposta.**
#### **4.2 Indique uma vantagem de, ao ambiente com Kubernetes e monitorização, acrescentar também uma ferramenta de avaliação experimental (benchmark). Justifique a sua resposta.**

4.1:
- Kubernetes é uma plataforma complexa para orquestração e gestão de containers. As ferramentas de monitorização são frequentemente combinadas com Kubernetes para oferecer visibilidade e insights sobre o desempenho, estado e utilização dos containers, pods e clusters. Isto permite aos engenheiros identificar problemas, otimizar recursos, realizar troubleshooting e garantir que as aplicações estão a funcionar corretamente.

4.2:
- A adição de uma ferramenta de avaliação experimental (benchmark) ao ambiente com Kubernetes e monitorização proporciona uma abordagem holística para entender e otimizar o desempenho das aplicações. Através de testes de benchmark, os engenheiros podem simular condições de carga específicas, medir o desempenho em cenários controlados e identificar os possíveis bottlenecks. Isto é vantajoso para ajustar e otimizar o ambiente Kubernetes, fazer ajustes de escalabilidade e garantir que a infraestrutura pode lidar eficientemente com cargas de trabalho reais. Em conjunto com a monitorização, fornece uma abordagem abrangente para garantir que as aplicações estão a funcionar corretamente e a atender aos requisitos de desempenho.