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

#### Espaçamento entre trilhas e componentes

Ao fazer o design do circuito na sua placa, independente do software utilizado, é importante levar em consideração a distância entre cada um dos elementos na sua placa, pois o espaço entre estes elementos devem ser dedicados ao tamanho da ferramenta que você precisará para fresar a placa.

Por exemplo, se você deseja utilizar uma fresa de topo reto de 1mm, suas trilhas, pads e furos devem ter espaços entre eles iguais ou maiores que 1mm.

O mesmo vale para furos - o  diâmetro interno de cada furo precisa ser maior que a ferramenta que você planeja utilizar para fura-lo.

Se você for utilizar componentes SMD os pads precisam ter espaço suficiente para a ferramenta passar entre eles e isolar cada pad.

#### Vias em placas dupla-face

Se sua placa é dupla face e contém vias \(conexões elétricas entre as duas faces da placa\) você precisará criar uma conexão entre eles manualmente quando for soldar os componentes.

#### Planos de Terra/VCC

Se a sua placa é projetada com um plano de terra, confira se a isolação dos em relação aos traços estão configurados para ter ao menos a mesma dimensão da menor ferramenta que você pretende utilizar.

#### Espessura das trilhas

A espessura mínima das trilhas que sugerimos é de 0,3048mm \(0.012in / 12mil / T12\) pois trilhas mais finas que isso têm maior propensão a se descolar da placa. Recomendamos utilizar as trilhas mais largas que sua placa pode suportar, desde que respeite também os espaçamentos entre os elementos da placa.

Além disso, trilhas muito finas poder ser um problema ao fazer sua placa com fresas piramidais, pois caso a placa esteja empenada, nos pontos mais altos da placa a fresa piramidal retirará mais material, deixando sua trilha mais fina.

![](/assets/policy_abso1.jpg)

Outra consideração importante sobre a espessura da trilha é a corrente que ela deve suportar. Abaixo, temos uma tabela que ajudará no dimensionamento da largura de trilha para uma determinada corrente.

| Corrente | Largura da trilha \(mil/th\) | Largura da trilha \(mil/th\) |
| :--- | :--- | :--- |
| \(A\) | para 1 oz | para 2 oz |
| 1 | 10 | 5 |
| 2 | 30 | 15 |
| 3 | 50 | 25 |
| 4 | 80 | 40 |
| 5 | 110 | 55 |
| 6 | 150 | 75 |
| 7 | 180 | 90 |
| 8 | 220 | 110 |
| 9 | 260 | 130 |
| 10 | 300 | 150 |

Oz é a unidade de medida espessura do cobre do laminado \(fenolite, fibra de vidro etc\) para PCBs.

A espessura do cobre do laminado é especificado pelo fabricante da placa de circuito impresso, o mais comum é 1 oz \(0.0347 mm\).

Exemplificando, para uma largura de trilha de 30 mils, usando-se uma placa com espessura de 1 oz, essa trilha suportará 2 A.

