# Regras de Design para PCBs

A Fresadora de Precisão MDX-40A do Fab Lab Facens é ótima para fazer e prototipar placas de circuito impresso. Entretanto existem algumaas considerações importantes no processo de design da sua placa.

Este documento é feito para pessoas que já possuem alguma experiência do Design de PCBs. Se você ainda é novo neste assunto, recomendamos buscar alguns tutorias de softwares de design de placas eletrônicas como por exemplo o Eagle ou Proteus.

Vamos começar com uma lista básica das regras de design e depois vamos um pouco mais a fundo nos detalhes de cada regra.

### Lista de Regras de Design de PCBs

* Espessura mínima das trilhas: 0,3048mm \(0.012in / 12mil / T12\)
* Espaçamento mínimo das trilhas: 0,5mm \(0.020in / 20mil / T20\)
* Espessura mínima do anel de pads/vias: 0,3048mm \(0.012in / 12mil / T12\)
* Diâmetro mínimo dos furos: 0,5mm \(0.020in / 20mil / T20\)
* Tamanho mínimo de pad SMD: 0,3048mm \(0.012in / 12mil / T12\)

### Processo de produção de PCBs por fresadoras CNC

Antes de partirmos para os detalhes das regras de Design, é importante você entender um pouco da produção de PCBs através de máquinas CNC, e os tipos de ferramentas disponíveis no Fab Lab Facens.

O processo de produção de PCBs por fresadoras CNC acontece através da retirada de áreas de material de uma placa de cobre para isolar os pads e trilhas de condução de acordo com padrões e desenhos de um plano de placa de circuito eletrônico.

O processo de remoção do material do cobre para isolamento das trilhas é pads é feito através de ferramentas de fresamento que podem ser de diferentes tipos e tamanhos. Os dois tipos mais comuns de ferramentas são as fresas de topo reto e as de gravação piramidais.

![](/assets/Othermill-Tool-Shape-FlatEndMill-1.png) ![](/assets/Othermill-Tool-Shape-EngravingBit-1.png)

_Fresa de topo e fresa piramidal_

As fresas de topo reto deixam canais retos, já as fresas de gravação deixam canais em formato de V na placa. No geral as fresas de topo reto são melhores pois garantem diâmetros consistentes mesmo se a placa estiver um pouco empenada. Fresas de topo reto também são boas para limpara grandes áreas de materiais de maneira mais rápida.

Entretanto fresas de topo reto também têm seu lado ruim. Ferramentas muito pequenas, particularmente as menores que 0,8mm de diâmetro, são frágeis e quebram muito facilmente. Além disso são extremamente caras, podendo custar até 5 vezes mais que uma fresa de gravação piramidal. Para evitar que se quebrem durante a usinagem, é necessário diminuir a velocidade e podem resultar em trabalhos bem demorados.

Fresas de gravação piramidais são uma ótima alternativa para prototipagem das placas PCBs, pois são feitas com mais metal e menos propensas a quebrar. Mesmo as mais finas podem fresar com sucesso em uma boa velocidade em poucos passes. Isso as fazem uma boa solução para prototipagem rápida das placas de PCB.

Por outro lado as fresas piramidais não são propícias para limpar grandes áreas de material ou fazer furos e cortes de placas. Além disso em função do diâmetro da fresa variar em função da profundidade, placas empenadas podem resultar em trilhas imprecisas.

|  | Fresa de topo | Fresa Piramidal |
| :--- | :--- | :--- |
| Tempo de usinagem de áreas grandes | Rápido | Lento |
| Tempo de usinagem de traços e espaços finos | Lento | Rápido |
| Perfil de usinagem | Reto | Em V |
| Recursos de PCB | Trilhas, furos e cortes | Trilhas |

##### Devo usar uma fresa de topo ou uma fresa piramidal?

Como toda PCB é diferente, aqui estão algumas dicas ao escolher uma ferramenta para um protótipo:

* Se o espaçamento entre as trilhas e furos na sua PCB são igual ou maiores que 1mm ou mais, use uma fresa de topo, assim você não precisa trocar de ferramenta
* Se a placa exige trilhas e espaçamentos mínimos de 0,4mm, uma fresa piramidal será muito mais rápida.
* Se a placa tem forma irregular, tem furos use tanto a fresa piramidal quanto as de topo reto.

### Regras de Design

#### Espaçamento entre traços e componentes



### 



