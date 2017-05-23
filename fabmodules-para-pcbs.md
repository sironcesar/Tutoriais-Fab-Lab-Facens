# Preparando suas PCBs com o Fab Modules

O FabModules é uma ferramenta on-line, feita por professores, estudantes e pesquisadores do MIT que oferece uma série de recursos para fabricação digital, com o objetivo de usar com maquinas comuns em Fab Labs. Ele pode ser acessado em fabmodules.org e tem uma interface bem simplista.

O FabModules inclui:

* Ferramentas para desenhos 2D e 3D
* Funções para gerar caminhos de ferramentas em 2D e 3D
* Interface gráfica de usuário para ir de arquivos de design para comandos de máquinas.

Na produção de PCBs com o Fab Modules, além de respeitar as regras de design, é importante exportar as suas imagens da maneira correta para evitar problemas durante a usinagem das placas.

### Resumo

* Crie seus arquivos de imagens .png para trilhas, furos e cortes
* Configure e gere o arquivo .rml para as trilhas
* Configure e gere o arquivo .rml para os furos
* Configure e gere o arquivo .rml para o corte

### Passo 1: exportando o layout de sua PCB para imagem

Utilizando o software de sua preferência, você deverá exportar o layout de sua PCB em formato de imagem. Você deverá ter duas ou três imagens dependendo da sua PCB: trilhas, furos e corte.

As imagens finais deverão respeitar as seguintes regras:

* Alta resolução \(500dpi ou maior\)
* Formato .png
* Cores Monocromáticas \(preto e branco\)

O FabModules funciona através de processamento de imagem, onde ele reconhece a diferença de cores \(branco e preto\) e define o caminho da ferramenta tangenciando as linhas das diferença de cores.

Caso necessário, você pode fazer ajustes nas suas imagens utilizando um software de edição de imagens. Recomendamos o GIMP, que é gratuito, de fácil utilização e que mantém as configurações de dpi da sua imagem.

Para cada tipo de processo \(trilhas, furos ou cortes\) deve ser gerada uma imagem com características diferentes. Vale destacar que o FabModules configura para retirar o material das áreas em preto da imagem, e isso define como deveremos fazer cada uma delas.

##### Trilhas

A imagem exportada para fresar as trilhas devem conter apenas as trilhas e pads, que devem estar na cor branca. Caso as trilhas e pads estejam em preto, e o restante da placa em branco, você pode inverter as cores utilizando o GIMP no menu Cores&gt;Inverter.

Caso você não utilize plano de terra, sua imagem deverá ficar semelhante à imagem abaixo, pois assim você fresará as partes em preto, isolando cada uma das trilhas.

![](/assets/top_traces.png)

##### Furos

Neste caso você deve fazer os furos em preto, e deixar todo o restante da placa com a cor branca. Sua imagem final para os furos deverá ficar semelhante à imagem abaixo.

![](/assets/top_drills.png)

##### Corte

Para o desenho do corte é importante gerar uma imagem com o centro da placa em branco e uma borda espessa em preto. Ressalto que a parte em branco é o formato final da sua placa. Caso sua placa seja retangular, ela deverá ter uma aparência semelhante a imagem abaixo.

![](/assets/top_cut.png)

A parte em branco geralmente pode ser conseguida exportando a borda ou a dimensão da placa. Entretanto para a borda em preto você precisará ajustar o "Tamanho da Tela de pintura". Caso você faça isso, terá de repetir o mesmo processo para as imagens de furos e de trilhas, para que todas as imagens fiquem do mesmo tamanho.

No Eagle a dimensão vem apenas como uma linha. Neste caso você pode utilizar a ferramenta de preenchimento \(shift+B\) do GIMP para preencher a parte interna de branco.

Caso a linha de dimensão venha junto ao limite da borda da imagem você deverá aumentar o tamanho da sua imagem, utilizando a ferramenta "Imagem&gt;Tamanho da tela de pintura". Aumente a sua imagem em 100px na altura e 100 px na largura.

![](/assets/pcb1.png)

Após mudar o tamanho da tela de pintura, crie uma nova camada e pinte ela de preto utilizando a "Ferramenta de preenchimento" no menu lateral esquerdo. Arraste a sua camada para baixo da imagem.

![](/assets/pcb2.png)![](/assets/pcb3.png)Após este processo, exporte sua imagem com extensão .png mantendo a mesma resolução original. Para exportar aimagem basta ir em "Arquivo&gt;Exportar como". Escolha o nome do arquivo e digite .png na frente, e o software irá automaticamente exportar a imagem como PNG.



Passo 2: Gerando códigos com o Fab Modules

Após exportar as imagens, você deverá carregá-las no Fab Modules e escolher as configurações do equipamento, processo e ferramentas utilizados. Para isso acesse o site http://fabmodules.org e siga os passos a seguir:

1\) Selecione o tipo de imagem para carregar em "input format&gt;image\(.png\)" e carregue a imagem

2\) Selecione o tipo de saída do código em "output format \(.rml\)

3\) Selecione o tipo de processo em "process&gt;PCB traces \(1/64\)" para trilhas ou "process&gt;PCB outline" para furos ou cortes







4\) Confira o valor da resolução e dimensões da imagem. \(ATENÇÃO!\)





* O Proteus exporta imagens somente em .BMP. Utilizando o GIMP você pode exportar como .PNG, porém a imagem perde o registro da resolução de imagem. Portanto altere para o valor original de resolução exportado \(recomendo 600 dpi\).
* Alguns modelos de computadores como o Macbook Pro Retina exportam as imagens do software Eagle com o dobro da resolução registrada na imagem, deixando a sua placa com o dobro das dimensões totais. Assim se você exportou sua imagem com 500 dpi de resolução, sua imagem terá na verdade 1000 dpi de resolução. 







































5\)

* 




















![](/assets/pcb5.png)







