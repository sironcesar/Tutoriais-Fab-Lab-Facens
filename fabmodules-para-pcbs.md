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

Trilhas

A imagem exportada para fresar as trilhas devem conter apenas as trilhas e pads, que devem estar na cor branca. Caso as trilhas e pads estejam em preto, e o restante da placa em branco, você pode inverter as cores utilizando o GIMP no menu Cores&gt;Inverter.

Caso você não utilize plano de terra, sua imagem deverá ficar semelhante à imagem abaixo, pois assim você fresará as partes em preto, isolando cada uma das trilhas.

![](/assets/top_traces.png)



Furos

Neste caso você deve fazer os furos em preto, e deixar todo o restante da placa com a cor branca. Sua imagem final para os furos deverá ficar semelhante à imagem abaixo.

![](/assets/top_drills.png)



Corte

Para o desenho do corte é importante gerar uma imagem com o centro da placa em branco e uma borda espessa em preto. Ressalto que a parte em branco é o formato final da sua placa. Caso sua placa seja retangular, ela deverá ter uma aparência semelhante a imagem abaixo.

![](/assets/top_cut.png)

A parte em branco geralmente pode ser conseguida exportando a borda ou a dimensão da placa.

No Eagle a dimensão vem apenas como uma linha. Neste caso você pode utilizar a ferramenta de preenchimento \(shift+B\) do gimp para preencher a parte interna de branco.

Caso a linha de dimensão venha junto ao limite da borda da imagem você deverá aumentar o tamanho da sua imagem





