# Perguntas Gerais

### **1. - Indique uma vantagem e um desafio a ter em conta quando se pretende seguir uma instalação distribuída para um dado componente de software. Justifique a sua resposta.**

Vantagem:
- **Modularidade:** Sistemas Distribuidos permitem modularidade e decoplação entre diferentes componentes de software. Modularidade envolve dividir um sistema em componentes mais pequenos e independentes. Estes módulos podem operar independentemente e comunicar através de interfaces bem definidas. Isto permite que equipas possam trabalhar em diferentes módulos concorrentemente sem as depêndencias normais, promovendo desenvolvimento em paralelo.

- **Escalabilidade:** uma vantagem significativa ao seguir uma arquitetura distribuida, por exemplo, para o MySQL, é a capacidade de escalabilidade horizontal. Isto permite distribuir a carga entre vários nós, facilitando a gestão de grandes volumes de dados e aumentando o desempenho à medida que mais recursos são necessários. Isto é particularmente útil em cenários onde o volume de dados ou o número de utilizadores pode aumentar significativamente.

Desafio:
- **Complexidade de configuração e Manutenção:** Coordenar e manter a consistência entre diferentes nós pode ser mais complexo do que gerir um sistema centralizado. Questões como sincronização, garantia de consistência e resolução de conflitos devem ser consideradas. Para além disso, a administração de múltiplos componentes distribuídos pode exigir um conhecimento mais aprofudndado e recursos dedicados.



### **2. - Give one example of a type of application or service where the use of containers is more appropriate. Justify your answer.**


Containers são particularmente adequados para aplicações que seguem uma arquitetura de microserviços. Neste tipo de aplicações, o sistema é composto por componentes folgadamente acopulados, independentemente deployable que funcionam em conjunto para constituir a funcionalidade total. Containers fornecem um ambiente leve e portável para microserviços individuais, encapsulando todas as dependências e libraries necessárias para executar o serviço. Isto permite que os microserviços sejam facilmente desenvolvidos, testados e implementados de forma independente. Containers também fornecem uma maneira eficiente de empacotar, distribuir e executar microserviços, permitindo que sejam facilmente escalados horizontalmente, simplificando a manutenção dos mesmos. Ao escolher containers para este tipo de aplicação, os developers podem usufruir de um ambiente de desenvolvimento mais consistente e fiável.

Vantagens:
- Isolamento
- Portabilidade
- Eficiência de recursos

Exemplo de uma aplicação que pode ser implementada com containers:
- Aplicação de E-commerce, composta por vários microserviços independentes, como por exemplo, um serviço de autenticação, um serviço de carrinho de compras, um serviço de gestão de pagamentos, um serviço de gestão de encomendas, etc. Isto permite aos developers desenvolver, fazer update, escalar e dar deploy destes micro serviços sem afetar a aplicação como um todo.



### **3. - Give one example of a type of application or service where the use of virtual machines is more appropriate. Justify your answer.**


Considerando um cenário no qual uma organização necessita de realizar análise de dados ou outro tipo de tarefas computacionalmente intensivo. Neste contexto, utilizar máquinas virtuais num modelo de Infraestrutura as a Service será adequado:
- Ambiente customizavel - Computação de alto nível geralmente necessita de um ambiente customizado com configurações especificas de software, libraries e dependências. Máquinas virtuais num ambiente IaaS permitem aos utilizadores customizar o ambiente de acordo com as suas necessidades.
- Escalabilidade - Computação de alto nível geralmente envolve processamento paralelo e computação distribuida. As plataformas IaaS permitem aos utilizadores escalar facilmente o número de máquinas virtuais para distribuir a carga de trabalho e aumentar o desempenho, permitindo aos utilizadores tratar de datasets maiores e mais complexos. Esta escalabilidade é essencial para computação de tarefas computacionalmente intensivas.


### **4. -  What functionalities would you suggest to improve data availability, improve space efficiency, optimize performance, and increase security in a storage system? Justify your answer.**

Garantir alta disponibilidade:
- **Replicação:** A replicação é uma funcionalidade que oferece alta disponibilidade ao permitir a criação de réplicas de dados noutros nós. No caso de falhas num nó, os dados podem ser recuperados a partir de uma réplica, garantindo a disponibilidade do sistema. A replicação assíncrona também permite que os dados sejam replicados para locais remotos, o que pode ser útil para fins de backup e recuperação de desastres. Para além disso, a replicação assíncrona também reduz a latência, pois as transações não precisam de ser confirmadas imediatamente em todos os nós.
- **Erasure Codes:** Os códigos de apagamento, como o Reed-Solomon, oferecem uma forma eficiente de tolerância a falhas, permitindo a recuperação de dados perdidos devido a falhas em discos ou nós. Isto contribui para a alta disponibilidade, pois o sistema pode continuar a operar mesmo na presença de falhas.


Reduzir o espaço ocupado pelos dados persistidos:
- **Compression:** A compressão reduz o tamanho dos dados, economizando espaço de armazenamento. A compressão pode ser útil para reduzir o espaço ocupado pelos dados persistidos. Esta técnica contribui para armazenar mais dados num menor espaço, o que pode ser útil para reduzir os custos de armazenamento de grandes volumes de dados.
- **Deduplication:** A deduplicação elimina cópias redundantes de dados, reduzindo ainda mais o espaço ocupado. A deduplicação pode ser útil para reduzir o espaço ocupado pelos dados persistidos. Esta técnica contribui para armazenar mais dados num menor espaço, o que pode ser útil para reduzir os custos de armazenamento de grandes volumes de dados. Enquanto que compressão é uma técnica estática, a deduplicação pode ser feita de forma dinâmica, o que permite eliminar dados redundantes à medida que são adicionados.

Para otimizar o performance:
- **Data Locality:** Num sistema de armazenamento, a localidade de dados envolve aproximar as tarefas computacionais à localização física dos dados. Isto minimiza a transferência e movimento de dados através de uma rede, reduzindo a latência e melhorando o performance em geral. Ao alocar a computação e storage no mesmo servidor ou máquina, os dados podem ser processados sem a necessidade extensiva de transferẽncias de dados. Isto é particularmente beneficial para aplicações que requerem constante acesso a grandes datasets.
- **Caching:** Caching envolve guardar uma cópia de dados frequentemente acessados numa localização que fornece acesso mais rápido do que o armazenamento primário. Isto pode ser mais perto do cliente ou em armazenamento de velocidade superior, como por exemplo um ssd ou até RAM. Caching também ajuda a mitigar a latência associada à requisição de dados de um armazenamento lento, fornecendo uma alternativa mais rápida. Reduz o tempo de espera em geral.

Aumentar a segurança:
- **Encriptar dados Guardados:** Esta encriptação envolve encriptar a data antes de ser armazenada persistentemente numa máquina de armazenamento. Isto garante que mesmo que individuos não autorizados consigam ganhar acesso físico ao armazenamento, os dados guardados serão ilegíveis sem as decryption keys. Isto é essencial para proteger contra roubos do hardware físico e data breaches.
- **Controlo de Acesso:** Evitar acesso não autorizado aos dados dos utilizadores, utilizando mecanismos que restringem o acesso aos dados, permitindo apenas certos utilizadores interagir com a informação guardada. Isto protege dados privados e sensíveis de acessos não autorizados, apagamentos e manipulação, sendo essencial para garantir a confidencialidade, integridade e disponibilidade da informação armazenada.


### **5. IT engineers that manage applications in Kubernetes environments often use monitoring tools.**
#### **5.1 Identify one reason for combining Kubernetes with monitoring tools. Justify your answer.**
#### **5.2 Identify one advantage of adding a benchmarking tool to this environment that combines Kubernetes with monitoring tools. Justify your answer.**

5.1:

- Kubernetes é uma plataforma complexa para orquestração e gestão de containers. As ferramentas de monitorização são frequentemente combinadas com Kubernetes para oferecer visibilidade e insights sobre o desempenho, estado e utilização dos containers, pods e clusters. Isto permite aos engenheiros identificar problemas, otimizar recursos, realizar troubleshooting e garantir que as aplicações estão a funcionar corretamente.

5.2:

- A adição de uma ferramenta de avaliação experimental (benchmark) ao ambiente com Kubernetes e monitorização proporciona uma abordagem holística para entender e otimizar o desempenho das aplicações. Através de testes de benchmark, os engenheiros podem simular condições de carga específicas, medir o desempenho em cenários controlados e identificar os possíveis bottlenecks. Isto é vantajoso para ajustar e otimizar o ambiente Kubernetes, fazer ajustes de escalabilidade e garantir que a infraestrutura pode lidar eficientemente com cargas de trabalho reais. Em conjunto com a monitorização, fornece uma abordagem abrangente para garantir que as aplicações estão a funcionar corretamente e a atender aos requisitos de desempenho.



### **6. - A complexidade da replicação de um serviço multi-camada não varia de acordo com o componente alvo (p.ex., servidor web, servidor aplicacional, base de dados) a replicar. Indique e justifiquese concorda ou não com esta afirmação.**

A afirmação não é verdadeira. A complexidade de um serviço multi-layered pode, de facto, variar significativamente com base no componente especifico a ser replicado. Diferentes componentes podrão ter caraterísticas, dependências, requisitos e desafios distintos associados à sua replicação. Como por exemplo:
- **Dependências de Dados:** replicar uma layer de base de dados envolve lidar com a consistência de dados, sincronização e potenciais conflitos. Por outro lado, replicar um servidor web poderá não ter estes desafios, focando-se mais em load balancing e content distribution.
- **Caraterísticas de Escalabilidade:** Servidores de web podem ser facilmente escalados horizontalmente, enquanto que servidores de base de dados podem ser mais difíceis de escalar, devido a dependências de dados e consistência, necessitando de estratégias mais complexas como sharding ou partitioning. 
- **Requisitos de Consistência:** Servidores de base de dados podem ter requisitos de consistência mais exigentes, enquanto que servidores de web podem ser mais tolerantes a inconsistências temporárias.  
- **Deployment e Configuração:** Cada camada poderá ter requisitos de deployment e configuração distintos, que podem afetar a complexidade da replicação. Por exemplo, replicar uma base de dados pode envolver a replicação de dados, enquanto que replicar um servidor web pode envolver a replicação de código e configuração.


###  **7. - As infraestruturas de computação em nuvem promovem uma utilização eficiente de recursos computacionais, de rede e armazenamento através da utilização de virtualização. Descreva, e justifique, duas vantagens e duas desvantagens da utilização desta tecnologia.**

Vantagens da virtualização em infraestruturas de computação em nuvem:
- **Transparência:** A virtualização fornece uma transparência nas interações com o utilizador. Os utilizadores interagem com os recursos virtuais de modo semelhante a recursos físicos. Isto garante uma experiência consistente, tornando a transição de ambientes físicos para virtuais fácil e intuitivo.
- **Isolamento:** A virtualização aumenta a segurança ao isolar recursos virtuais entre si. Quebras de segurança num ambiente virtualizado não afetam automáticamente os restantes, mitigando os riscos e controlando estas falhas. Para além da segurança, os mecanismos de virtualização também fornecem um controlo eficiente sobre a alocação de recursos. Isto previne a contenção de recursos, assegurando que o performance de um recurso virtual não é impactado negativamente pelas atividades de outros.
- **Otimização de Recursos:** A virtualização permite a utilização mais eficiente dos recursos físicos. Múltiplas instâncias podem partilhar o mesmo hardware, permitindo melhor utilização de recursos e escalabilidade. Para além disso virtualização também contribui para a redução de custos. Ao otimizar a utilização de recursos, melhoramos também a eficiência, acopulando a isto a redução de custo de manutenção devido à redução quantidade de hardware necessário. 


Desvantagens:
- **Performance:** Virtualização pode introduzir um overhead adicional. A camada adicinal causada por exemplo por um hipervisor pode resultar numa redução na raw performance comparativamente a correr aplicações e software nativamente. Isto é particularmente notável em CPU e I/O de storage e network
- **Overprovisioning:** Overprovisioning ocorre quando mais recursos virtuais são deployed do que a infrastrutura subjacente consegue suportar. Isto pode levar a degradação à medida que os recursos físicos são sobrecarregados, levando à contenção de recursos e impactando o performance.
- **Dependability:** A dependência numa infraestrutura física partilhada em virtualização introduz uma vulnerabilidade: se um recurso físico falha, múltiplas instâncias virtuais a correr com esse recurso poderão ser afetadas. Esta dependência pode levar a falhas de grande escala.




### **8. - Nas aulas práticas recorreu às ferramentas ElasticSearch, Kibana e MetricBeat para observar a utilização de recursos de diferentes máquinas virtuais. Indique qual a função de cada uma destas ferramentas num ambiente de monitorização.** 

- **ElasticSearch:** Base de dados NoSQL que armazena os dados de monitorização. Permite a indexação e pesquisa de dados, bem como a agregação de dados para visualização. É utilizado como motor de busca para os dados de monitorização.

- **Kibana:** Ferramenta de visualização de dados que permite a criação de dashboards e gráficos para análise de dados. Permite a criação de visualizações personalizadas para os dados de monitorização. Funciona como uma interface de visualização e exploração dos dados armazenados no ElasticSearch.

- **MetricBeat:** Ferramenta de monitorização que recolhe métricas do sistema e envia-as para o ElasticSearch. Permite a monitorização de métricas de sistema, como CPU, memória, rede, etc. É utilizado para recolher dados de monitorização e enviá-los para o ElasticSearch.

Em suma: O ElasticSearch armazxena os dados de monitorização, o Kibana permite a visualização e exploração desses dados, e o MetricBeat recolhe os dados de monitorização, enviando-os para o ElasticSearch.


### **9. - Imagine que a Universidade do Minho lhe atribui a responsabilidade de instalar a aplicação WikiJS para servir todos os alunos da universidade. No entanto, antes do processo de instalação, ogestor financeiro da universidade pergunta-lhe quais os recursos computacionais que prevê serem necessários para esta instalação. Que estratégia(s) pode aplicar para responder a esta pergunta e ter um elevado grau de confiança que a aplicação será capaz de responder à carga computacional imposta em produção?**

Para fornecer uma resposta com um elevado grau de confiança sobre os recursos necessários para a instalação da aplicação poderemos aplicar as seguintes estratégias:

- **Análise de Requisitos do Sistema:** Avaliando os requisitos do sistema recomendados pela WikiJS, incluíndo específicacões de CPU, RAM, armazenamento e largura de banda de rede.
- **Load Testing:** Realizando testes de carga simulando condições reais de uso para avaliar o desempenho da aplicação e identificar potenciais problemas de escalabilidade. Para tal utilizaríamos ferramentas para simular múltiplos utilizadores a aceder à aplicação, e analisaríamos métricas como tempo de resposta, throughput, etc. para avaliar o desempenho da aplicação. Também deveríamos analisar o tempo de resposta e utilização de recursos.
- **Monitorização em Ambiente de Desenvolvimento (Staging):** Implementando a aplicação num ambiente de teste que simule o ambiente de produção. Utilizaríamos ferramentas de monitorização para recolher métricas de utilização de recursos e desempenho da aplicação, tais como o ElasticSearch, Kibana e MetricBeat, e analisaríamos os dados para detetar bottlenecks e padrões de utilização.
- **Escalabilidade Vertical e Horizontal:** Avaliando a possbilidade de escalabilidade Vertical (aumento de recursos numa única máquina) e horizontal (distribuição da carga entre várias máquinas). Isto permitiria aumentar a capacidade da aplicação em resposta a um aumento de carga. Para tal, deveríamos avaliar a arquitetura da aplicação e identificar potenciais limitações de escalabilidade.




### **10. - Discuta de que forma o particionamento (sharding) e replicação de dados podem contribuir para um melhor desempenho e tolerância a faltas de um sistema distribuído.**

**Sharding:**
- Partitioning envolve dividir data em múltiplas partições (ou shards) distribuídas por múltiplas máquinas no sistema. Esta técnica contribui significativamente para o desempenho do performance de um sistema distribuído de várias maneiras:
    - **Distribuição de Carga** - Pedidos de escrita e leitura podem ser distribuídos pelas várias partições, reduzindo a carga em cada partição. Isto resulta em opreções mais rápidas e menos congestionamento e latência.
    - **Paralelismo** - Com sharding, múltiplas operações podem ser executadas em simultâneo em diferentes partições, aumentando o throughput do sistema.
    - **Escalabilidade Horizontal** - À medida que a carga de dados aumenta, mais partições podem ser adicionadas para distribuir a carga e manter o desempenho do sistema.
- Tolerância de Falhas - 
    - **Isolamento de Falhas** - Em caso de falha num nó específico, outras partições continuam a funcionar normalmente, isolando o impacto da falha.
    - **Recuperação Rápida** - Recuperação de partições individuais é mais rápida do que recuperar um sistema inteiro, reduzindo o tempo de inatividade.


**Replicação:**
- Replicação envolve criar cópias idênticas de dados em múltiplos nós do sistema, resultando em benefícios significativos:
    - **Leitura Rápida** - Operações de leitura podem ser distribuídas por múltiplas réplicas, permitindo leituras mais rápidas e eficientes, em especial caso em cenários de leitura intensiva.
    - **Disponibilidade Melhorada** - Com réplicas, mesmo que um nó falhe, cópias dos dados ainda estão disponíveis em outros nós, permitindo que o sistema continue a funcionar normalmente.
- Tolerância de Falhas -
    - **Redundância** - As cópias dos dados fornecem redundância, permitindo que o sistema continue a funcionar normalmente mesmo que um nó falhe.





### **11. - Discuta quais as vantagens e desvantagens da utilização de máquinas virtuais nos modos paravirtualizado (paravirtualization) e de virtualização completa (full virtualization).**

**Paravirtualização:**
- Vantagens:
    - **Desempenho** - A paravirtualização permite comunicação direta entre o sistema operativo guest e o hypervisor, permitindo evitar a necessidade de emulação completa. Isto leva a um overhead reduzido comparado com a virtualização completa.
    - **Uso Eficiente de Recursos** - Visto que o Guest OS está ciente da virtualização, pode cooperar com o hypervisor de modo a otimizar o uso de recursos, como por exemplo, permitindo que o hypervisor aloque memória de forma mais eficiente.
    - **Sem necessidade de Extensões de Virtualização** - Paravirtualização não requer nenhuma extensão de virtualização de hardware específica, podendo correr em hardware que poderá não suportar virtualização completa.
- Desvantagens:
    - **Limitações de SO Guest** - Paravirtualização requer modificações no kernel do sistema operativo do Guest. Deste modo, poderá não ser compatível com todos os sistemas operativos, e alguns poderão de ser específicamente modificados para suportar paravirtualização.
    - **Implementações Específicas** - Diferentes Hypervisors poderão ter diferentes implementações de paravirtualização, o que poderá levar a problemas de portabilidade.

**Virtualização Completa:**
- Vantagens:
    - **Compatibilidade** - Virtualização Completa não precisa de modificações no kernel do sistema operativo do Guest visto que emula o ambiente de hardware completo. Isto torna-o compatível com uma grande gama de sistemas operativos.
    - **Facilidade de Deployment** - Virtualização Completa é geralmente mais fácil de dar deploy, específicamente quando se trata de sistemas operativos que não requerem modificações.
    - **Isolamento** - Virtualização Completa fornece um forte isolamento entre diferentes máquinas virtuais, aumentando a segurança através da prevenção de acesso não autorizado a dados de outras máquinas virtuais.
- Desvantagens:
    - **Maior Overhead** - Virtualização Completa introduz um maior overhead devido à necessidade de emulação completa do ambiente de hardware. Isto resulta num performance reduzido comparativamente à paravirtualização.
    - **Dependência em Extensões de Virtualização de Hardware** - Virtualização completa depende em extensões de virtualização de hardware como por exemplo Intel VT-x e AMD-V. Se o hardware não suportar estas extensões, virtualização completa poderá ser limitada ou não ser usada.
    - **Ineficiência de Recursos** - A emulação completa de hardware pode levar a um uso menos eficiente dos recursos, visto que o Guest OS não está ciente da virtualização e não pode cooperar com o hypervisor para otimizar o uso de recursos.

**Considerações Finais:**
- A escolha entre paravirtualização e paravirtualização completa depende de vários fatores como requirimentos de performance, compatibilidade de Guest OS e também do nível de isolamento necessário. Em muitos casos, uma combinação de ambas as técnicas pode ser usada para obter o melhor de ambos os mundos.



### **12. - A ferramenta Ansible fornece a noção de inventário (inventory) e módulo (module) para a criação de receitas de aprovisionamento. Descreve sucintamente o objetivo de cada um destes mecanismos.**

**Inventário:**
- **Objetivo** - O inventário de Ansible é um ficheiro ou conjunto de ficheiros que contém informação sobre os hosts sobre os quais o Ansible irá executar tarefas. O inventário permite organizar e gerir a infraestrutura, especificando detalhes como hostnames, endereços IP e grupos de hosts. O inventário fornece uma maneira estruturada de representar o ambiente objetivo e auxilia o Ansible a identificar os hosts com os quais irá interagir.

**Modules**
- **Objetivo** - Os módulos são scripts standalone ou programas que o Ansible usa para realizar tarefas nos nós do sistema. Cada módulo é responsável por uma tarefa específica, como por exemplo, gerir ficheiros, instalar packages ou configurar as definições do sistema. Os módulos abstraem os detalhes da implementação subjacente e fornecem uma interface consistente para realizar tarefas. Encapsulam a lógica necessária para alcançar certos objetivos nos nodos que estão a ser geridos. Os módulos de Ansible são invocados nos playbooks para definir o estado desejado do sistema.

**Conclusão**
- O inventário de Ansible ajuda a organizar e identificar os hosts na infraestrutura, servindo como o ponto de partida para operações Ansible. Por outro lado, os módulos de Ansible são blocos de construção que realizam tarefas específicas nos nós geridos, abstraíndo a complexidade e fornecendo uma interrface simples para execução de tarefas. Em conjunto, o inventário e os módulos de Ansible permitem a automatização de provisionamento e configuração de tarefas num ambiente.


### **13. - Na avaliação experimental de um sistema pode utilizar sequências de operações obtidas de um sistema real (traces) ou sintetizar uma sequência de operações. Discutas as vantagens/desvantagens de cada uma destas alternativas.**

**Traces:**
- **Vantagens:**
    - **Realismo** - Traces capturados de um ambiente de produção representam os padrões de utilização reais do sistema e comportamentos dos utilizadores. Isto assegura que a avaliação é baseada em cenários autênticos e realistas.
    - **Complexidade** - Traces reais capturam as complexidade e nuances das interações do sistema, fornecendo um entendimento mais profundo do comportamento do sistema.
    - **Relevância** - Utilizar traces reais permite avaliar o sistema em cenários que estão diretamente alinhados com as caraterísticas específicas do sistema alvo.
- **Desvantagens:** - 
    - **Controlo Limitado** - O developer tem controlo limitado sobre o conteúdo e diversidade dos traces reais. Isto pode levar a uma avaliação incompleta do sistema, visto que o developer não pode garantir que todos os cenários relevantes são cobertos.
    - **Privacidade** - Traces reais contêm dados sensíveis e privados, apresentando riscos de privacidade e segurança. Isto pode ser mitigado através de técnicas como anonimização, mas ainda assim pode ser um problema.
    - **Problemas com Escalabilidade** - Escalar traces reais para simular cenários de grande escala poderá ser difícil ou imprático.

**Síntese:**
- **Vantagens:**
    - **Controlo** - Os developers têm controlo absoluto sobre as sequências geradas, permitindo-lhes criar cenários específicos e fazer stress test dos diferentes componentes do sistema.
    - **Reprodutibilidade** - Sequências sintetizadas garantem que as experiências de avaliação podem ser repetidas e reproduzidas, permitindo uma avaliação mais rigorosa e precisa, auxiliando a validação e verificação dos resultados.
    - **Escalabilidade** - Criar sequências sintéticas permite a fácil criação de cenários de escalas variadas, permitindo avaliar o sistema em diferentes níveis de carga.
- **Desvantagens:**
    - **Simplificação** - Sequências sintéticas poderão simplificar excessivamente a complexidade do mundo real e falhar em capturar todos os edge cases e nuances do sistema.
    - **Risco de Bias** - Depender nas decisões e premissas do developer pode levar a um bias na avaliação, podendo resultar em resultados enviesados e não representativos.
    - **Falta de Realismo** - Apesar dos esforços para imitar os cenários reais, sequências sintéticas poderão não ser realistas o suficiente para representar a imprevisibilidade e diversidade de comportamentos reais dos utilizadores.


### **14. - Defina as vantagens e desvantagens de Infrastructure as a Service, dando um exemplo de um serviço** 

**Vantagens:**
- Escalabilidade - IaaS permite a fácil e rápida escalabilidade de recursos. Organizações conseguem facilmente aumentar ou diminuir a  sua infraestrutura com base nas necessidades.
- Redução de Custos - Utilizadores pagam pelos recursos que consomem, evitando a necessidade de investimentos em hardware físico. Isto pode resultar em redução de custos significativa.

**Desvantagens**
- Segurança - Encarregar uma third party com dados sensíveis e confidenciais pode ser um enorme risco de segurança. Mesmo que os fornecedores de IaaS tenham medidas de segurança, é crucial que os utilizadores implementem as suas próprias medidas de segurança.
- Dependência - A dependência numa conexão de Internet estável é essencial. Se houverem problemas com a conexão, pode impactar a acessibilidade e performance das aplicações que estão a ser hosted nas plataformas IaaS

**Exemplo:**
Amazon Web Service permitem utilizadores alugar servidores virtuais na cloud, fornecendo grande capacidade de computação e escalabilidade.

### **15. - Defina as vantagens e desvantagens de Platform as a Service, dando um exemplo de um serviço**

**Vantagens:**
- Desenvolvimento Simplificado - PaaS abstrai a infraestrutura subjacente, permitindo que os developers se foquem totalmente em programar e desenvolver aplicações. Isto acelera o processo de desenvolvimento.
- Escalabilidade - Semelhante a IaaS, plataformas PaaS também permitem a fácil e rápida escalabilidade. Developers podem facilmente aumentar ou diminuir os recursos com base nas necessidades, evitando ter que gerir a infraestrutura subjacente.

**Desvantagens:**
- Limitações de Customização - Apesar de plataformas PaaS oferecerem grande conveniência, estas limitam a customização permitida em comparação a setups de infraestruturas mais tradicionais. Isto pode ser um problema para aplicações que têm requisitos especializados.
- Segurança - Organizações poderam não ter controlo total sobre a segurança dos dados, visto que estes são armazenados na cloud de um terceiro. Isto pode ser um problema para dados sensíveis e confidenciais.

**Exemplo:**
Google App Engine fornece uma plataforma para construir e dar deploy de aplicações, fornecendo uma infraestrutura escalável e gerida.


### **16. - Defina as vantagens e desvantagens de Software as a Service, dando um exemplo de um serviço**

**Vantagens:**
- Acessibilidade e Conveniência - Aplicações SaaS são acessíveis por um browser web, tornando-as extremamente convienentes e fáceis de utilizar em qualquer lugar com uma conexão de Internet. Esta acessibilidade é particularmente benéfica para equipas remotas ou distribuídas.
- Cost Effective - SaaS típicamente segue um modelo de subscrição, permitindo organizações evitar custos de licenciamento e manutenção de software. 

**Desvantagens:**
- Dependência - Aplicações SaaS dependem fortemente numa conexão à internet estável. Se existirem problemas de conectividade, os utilizadores poderão não conseguir aceder à aplicação.
- Customização Limitada - Aplicações SaaS são tipicamente desenhadas para serem genéricas e abrangentes, estando limitadas em termos de customização em comparação com aplicações on-premise. Organizações poderão não ter controlo total sobre o código e infraestrutura subjacente.