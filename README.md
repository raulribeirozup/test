# Implementando task final da seção 2

## Definindo o background

1. Começaremos, a partir de um projeto iOS novo, vamos definir as duas cores de fundo principais

- Abrir a pasta do projeto e selecionar Assets
- Clicar com o botão direito no Document Outline e selecionar New Folder
- Nomear a nova pasta para Colors
- Botão direito na pasta criada e selecionar New Color Set
- Nomear o primeiro color set para Black Haze
- Mudar a opção de Appearances para None
- Clicar no quadrado da cor ao lado direito do Document Outline e selecionar Show Color Panel no Inspetor de Atributos
- Selecionar Color Sliders -> RGB Sliders e definir os valores para 243, 245 e 245 respectivamente, apertar Enter
- Repetir o mesmo processo para o color set Sawtooth Aak (241, 144, 102) a partir do passo para criar um novo Color Set

1. Clicamos então em Main.storyboard e vamos configurar as views de fundo.

- Abrir o projeto pelo Document Outline e procurar pela view principal
- Selecionar a view principal e abrir o Inspetor de Atributos
- Na opção Background, procurar a nossa nova color set Black Haze e seleciona-la

1. Vamos precisar de mais uma view para poder fazer a parte de cima do background da app.

- Abrir então a biblioteca de componentes no botão direito superior + do XCode, ou selecionar Command + Shift + L
- Digitar uiview, drag and drop para o canvas, de preferência de forma centralizada com a view mãe
- Selecionar a nova view e alterar o nome dela para HeaderView
- No Inspetor de Atributos, selecionar o Background e trocar para a color set Sawtooth Aak

1. Agora precisamos definir as constraints dessa view.

- Com a view selecionada, no canto inferior direito selecionar o ícone Add New Constraints
- Setar o valor de margem 0 para o topo, direita e esquerda, relacionados com a superview
- Desmarcar a caixa Constrain to margins
- Selecionar Add 3 Constraints
- Com o botão control pressionado, Drag and Drop a partir da HeaderView para a view mãe e selecionar Equal Heights
- Clicar na HeaderView e selecionar o Inspetor de Tamanho, para acessar as constraints
- Duplo clique na constraint Proportional Height e alterar o multiplicador dela para 0.35

## Implementando o conteúdo da HeaderView

1. Podemos começar adicionando os color sets que precisaremos para essa parte

- Com as instruções prévias passadas nesse passo-a-passo, adicionar dois novos color sets: Cornflower(84, 109, 229) e Summertime(245, 205, 121)

1. Então começaremos com a logo da Zup no canto direito superior. Para trabalharmos de forma mais fácil com as margens, escolhi trabalhar com uma view container.

- Abrir então a biblioteca de componentes no botão direito superior + do XCode, ou selecionar Command + Shift + L
- Digitar uiview, drag and drop para o canvas, de preferência dentro da HeaderView
- Selecionar a nova view e renomeá-la para ContainerView
- Selecionar Add New Constraints no canto inferior direito
- Setar o valor de margem superior em relação a HeaderView 0, mas deixar selecionado a caixa Constrain to margins
- Selecionar Add 1 Constraint
- Selecionar Add New Constraints novamente
- Setar o valor das margens direita, esquerda e inferior em relação a HeaderView para 0 e desmarcar a caixa Constrain to margins
- Selecionar Add 3 Constraints

1. Dessa forma, devemos ter uma ContainerView dentro da HeaderView que a parte superior segue a safe area e os outros lados fiquem no mesmo posicionamento da HeaderView. Agora vamos adicionar o logo.

- Abrir então a biblioteca de componentes no botão direito superior + do XCode, ou selecionar Command + Shift + L
- Digitar uiview, drag and drop para o canvas, de preferência dentro da ContainerView
- Selecionar a nova view e renomeá-la para LogoView
- Selecionar Add New Constraints no canto inferior direito
- Setar o valor da margem superior e margem direita para 24 em relação a ContainerView
- Setar o valor de altura para 72
- Selecionar Add 3 Constraints
- No Inspetor de Tamanhos, alterar o valor da largura para 72
- Selecionar Add New Constraints novamente
- Selecionar Aspect Ratio e Add 1 Constraint
- No inspetor de identidate, clicar no + na caixa User Defined Runtime Attributes
- Adicionar um novo atributo com os valores layer.cornerRadius, Number, 12, respectivamente para keyPath, type e value
- No Inspetor de Atributos podemos selecionar a cor de background e definir para Cornflower

1. Agora, para a logo, falta apenas definir a label que terá o nome da Zup dentro da logo

- Abrir então a biblioteca de componentes no botão direito superior + do XCode, ou selecionar Command + Shift + L
- Digitar label, drag and drop para dentro da LogoView
- Selecionar a label e alterar o valor para "Zup"
- Alterar a cor para o color set Summertime
- Alterar a fonte para a System Heavy 24.0
- Selecionar Add New Constraints no canto inferior direito
- Setar o valor das margens esquerda, direita e inferior para 8 em relação ao LogoView

1. Agora vamos adicionar os textos principais

- Abrir então a biblioteca de componentes no botão direito superior + do XCode, ou selecionar Command + Shift + L
- Digitar label, drag and drop para dentro da HeaderView, preferencialmente abaixo da LogoView
- Alterar o valor da label para "Boas vindas"
- Alterar a cor para a custom color Black Haze
- Selecionar a fonte System, tamanho 36, espessura Heavy
- Selecionar a label e selecionar Add New Constraints no canto inferior direito
- Setar margens esquerda e direita para o valor 24 em relação a view mãe
- Abrir a biblioteca novamente e drag and drop de um label abaixo do "Boas vindas"
- Alterar o valor da label para "Faça login com a sua conta"
- Alterar a cor para a custom color Black Haze
- Selecionar a fonte System, tamanho 18, espessura Normal
- Selecionar a label e selecionar Add New Constraints no canto inferior direito
- Setar margens esquerda e direita para 24 em relação a view mãe, margem superior para 4 em relação ao label "Boas vindas" e a margem inferior para 88 (24 da especificação mais 64 da View principal que em breve será implementada)

## Implementando a view principal com os campos e botões para login



