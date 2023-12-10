# Teste 2022

### **1. - A complexidade da replicação de um serviço multi-camada não varia de acordo com o componente alvo (p.ex., servidor web, servidor aplicacional, base de dados) a replicar. Indique e justifiquese concorda ou não com esta afirmação.**

A afirmação não é verdadeira. A complexidade de um serviço multi-layered pode, de facto, variar significativamente com base no componente especifico a ser replicado. Diferentes componentes podrão ter caraterísticas, dependências, requisitos e desafios distintos associados à sua replicação. Como por exemplo:
- **Dependências de Dados:** replicar uma layer de base de dados envolve lidar com a consistência de dados, sincronização e potenciais conflitos. Por outro lado, replicar um servidor web poderá não ter estes desafios, focando-se mais em load balancing e content distribution.
- **Caraterísticas de Escalabilidade:** Servidores de web podem ser facilmente escalados horizontalmente, enquanto que servidores de base de dados podem ser mais difíceis de escalar, devido a dependências de dados e consistência, necessitando de estratégias mais complexas como sharding ou partitioning. 
- **Requisitos de Consistência:** Servidores de base de dados podem ter requisitos de consistência mais exigentes, enquanto que servidores de web podem ser mais tolerantes a inconsistências temporárias.  
- **Deployment e Configuração:** Cada camada poderá ter requisitos de deployment e configuração distintos, que podem afetar a complexidade da replicação. Por exemplo, replicar uma base de dados pode envolver a replicação de dados, enquanto que replicar um servidor web pode envolver a replicação de código e configuração.


###  **2. - As infraestruturas de computação em nuvem promovem uma utilização eficiente de recursos computacionais, de rede e armazenamento através da utilização de virtualização. Descreva, e justifique, duas vantagens e duas desvantagens da utilização desta tecnologia.**

Vantagens da virtualização em infraestruturas de computação em nuvem:
- **Eficiência no Uso de recursos:** A virtualização permite a criação de máquinas virtuais que partilham os recursos físicos de um servidor. Isto leva a uma utilização mais eficiente da capacidade de processamento, memória e armazenamento, permitindo que os recursos sejam partilhados por múltiplas máquinas virtuais. Ao otimizar o uso dos recursos físicos, a virtualização maximiza a utilização do hardware, reduzindo potencialmente os custos operacionais e energéticos.
- **Isolamento e Segurança:** Cada VM funciona como uma entidade isolada, o que significa que as aplicações numa VM não podem afetar as aplicações noutra VM. Isto permite que as VMs sejam usadas para isolar e proteger aplicações de terceiros, o que é especialmente útil em ambientes de computação em nuvem, onde os utilizadores podem executar aplicações não confiáveis.

Desvantagens:

- **Overhead:** A virtualização introduz overhead, uma vez que as VMs precisam de ser geridas e executadas por um hypervisor. Isto pode afetar o desempenho das aplicações comparativamente a uma execução nativa. Aplicações que requerem alta performance e baixa latência podem ser afetadas negativamente por este overhead introduzido pela virtualização.

- **Complexidade de Gestão:** Lidar com um ambiente virtualizado adiciona complexidade à gestão da uinfraestrutura. A gestão de VMs, snapshots, migração, etc. pode ser complexa e exigir conhecimentos especializados. Isto pode aumentar os custos operacionais e de gestão, especialmente em ambientes de grande escala.


### **3. - Nas aulas práticas recorreu às ferramentas ElasticSearch, Kibana e MetricBeat para observar a utilização de recursos de diferentes máquinas virtuais. Indique qual a função de cada uma destas ferramentas num ambiente de monitorização.** 

- **ElasticSearch:** Base de dados NoSQL que armazena os dados de monitorização. Permite a indexação e pesquisa de dados, bem como a agregação de dados para visualização. É utilizado como motor de busca para os dados de monitorização.

- **Kibana:** Ferramenta de visualização de dados que permite a criação de dashboards e gráficos para análise de dados. Permite a criação de visualizações personalizadas para os dados de monitorização. Funciona como uma interface de visualização e exploração dos dados armazenados no ElasticSearch.

- **MetricBeat:** Ferramenta de monitorização que recolhe métricas do sistema e envia-as para o ElasticSearch. Permite a monitorização de métricas de sistema, como CPU, memória, rede, etc. É utilizado para recolher dados de monitorização e enviá-los para o ElasticSearch.

Em suma: O ElasticSearch armazxena os dados de monitorização, o Kibana permite a visualização e exploração desses dados, e o MetricBeat recolhe os dados de monitorização, enviando-os para o ElasticSearch.


### **4. - Imagine que a Universidade do Minho lhe atribui a responsabilidade de instalar a aplicação WikiJS para servir todos os alunos da universidade. No entanto, antes do processo de instalação, ogestor financeiro da universidade pergunta-lhe quais os recursos computacionais que prevê serem necessários para esta instalação. Que estratégia(s) pode aplicar para responder a esta pergunta e ter um elevado grau de confiança que a aplicação será capaz de responder à carga computacional imposta em produção?**

Para fornecer uma resposta com um elevado grau de confiança sobre os recursos necessários para a instalação da aplicação poderemos aplicar as seguintes estratégias:

- **Análise de Requisitos do Sistema:** Avaliando os requisitos do sistema recomendados pela WikiJS, incluíndo específicacões de CPU, RAM, armazenamento e largura de banda de rede.
- **Load Testing:** Realizando testes de carga simulando condições reais de uso para avaliar o desempenho da aplicação e identificar potenciais problemas de escalabilidade. Para tal utilizaríamos ferramentas para simular múltiplos utilizadores a aceder à aplicação, e analisaríamos métricas como tempo de resposta, throughput, etc. para avaliar o desempenho da aplicação. Também deveríamos analisar o tempo de resposta e utilização de recursos.
- **Monitorização em Ambiente de Desenvolvimento (Staging):** Implementando a aplicação num ambiente de teste que simule o ambiente de produção. Utilizaríamos ferramentas de monitorização para recolher métricas de utilização de recursos e desempenho da aplicação, tais como o ElasticSearch, Kibana e MetricBeat, e analisaríamos os dados para detetar bottlenecks e padrões de utilização.
- **Escalabilidade Vertical e Horizontal:** Avaliando a possbilidade de escalabilidade Vertical (aumento de recursos numa única máquina) e horizontal (distribuição da carga entre várias máquinas). Isto permitiria aumentar a capacidade da aplicação em resposta a um aumento de carga. Para tal, deveríamos avaliar a arquitetura da aplicação e identificar potenciais limitações de escalabilidade.
