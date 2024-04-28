# PonderadaMVC


# 1. Arquitetura MVC do projeto Abandono Zero

*1.1 Descrição:* 
No intuito de obter dados precisos acerca das relações entre humanos e animais no que tange principalmente o abandono, a compra ou a adoção de cães,o Instituto de Saúde e Psicologia Animal(INSPA), juntamente com o Instituto de Tecnologia e Lidença, de forma voluntária iniciaram o desenvolvimento da aplicação Web Abandono Zero. Nesse aspecto, para a realização desse projeto, a arquitetura MVC é essencial, para que de forma clara e objetiva, seja possível observar a relação de cada segmento do site com o banco de dados da plataforma.

*1.2 Arquitetura:* MVC (Model-View-Controller)

*1.3 Ferramenta de Diagramação:* draw.io

## 2. Modelos (Models):

2.1 **MVC Tutores**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A relação entre  usuários e tutores é responsável pela interação entre os tutores e a página inicial do site. 

1. **UsuarioTutor**: Armazena os dados do usuário.
* Id: Armazena o identificador do usuário.
* Nome: Armazena o nome dos usuários.
* Email: Armazena os emails dos usuários.
* Senha: Armazena as senhas dos usuários.
* Role: Armazena se o usuário é administrador ou não.


2.2 **MVC Login**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A arquitetura Login é voltada para direcionar o usuário para o seu cadastro no site, dessa forma, por meio de um formulário, dados como nome, email, senha e role são armazenados, além de guardar tambem o id e relacionar se ele é um administrador ou não. Essa arquitetura inclui a lógica para listar, gravar e procurar, sendo essencial para a interação do usuário e organização do banco de dados.
1. **Entidade Usuarios**: Armazena os inputs de cadastro do usuário e informações ocultas como id.
* Id: Armazena o identificador do usuário.
* Nome: Armazena o nome dos usuários.
* Email: Armazena os emails dos usuários.
* Senha: Armazena as senhas dos usuários.
* Role: Armazena se o usuário é administrador ou não.


2.3 **MVC Formularios**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A arquitetura Formulario é voltada para a gestão das perguntas que será mostrada ao usuário.Apresentando funcionalidades como lista e gravar os inputs, além de armazenar se o usuário ja respondeu ou não a pergunta. Assim, tal arquitetura é essencial para a conclusão efetiva do formulário. 

1. **RespostaFormsGeral**:
* Id: Armazena o identificador do usuário.
* Resposta: Armazena o input de resposta do usuário.

2. **RespostaFormsJaTem**:
* Id: Armazena o identificador do usuário.
* Resposta: Armazena o input de resposta do usuário.

3. **RespostaFormsJaTeve**: 

* Id: Armazena o identificador do usuário.
* Resposta: Armazena o input de resposta do usuário.

 4. **RespostaFormsQuerter**: 
* Id: Armazena o identificador do usuário.
* Resposta: Armazena o input de resposta do usuário.

 5. **RespostaFormsNulo**:
* Id: Armazena o identificador do usuário.
* Resposta: Armazena o input de resposta do usuário.


2.4 **MVC Administradores**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A arquitetura Administradores é responsável pela relação entre os dados e a sua vizualização para os administradores, isto é, a equipe responsável pela pesquisa do INSPA. Ela inclui a lógica para listar e procurar e mostrar aos usuários da maneira desejada e disponível. Essa arquitetura é fundamental para a boa experiência e vizualização dos dados para o possível pesquisador.

1. **Entidade Usuários**: Armazena os dados do usuário.
* Id: Armazena o identificador do usuário.
* Nome: Armazena o nome dos usuários.
* Email: Armazena os emails dos usuários.
* Senha: Armazena as senhas dos usuários.
* Role: Armazena se o usuário é administrador ou não.


2. **Entidade Relatorios**:
* Id: Armazena o identificador do usuário.
* Dados:  Representa todas as respostas dos inputs das perguntas
* FormularioEspecifico: Possibilita o filtro de um formulário específico.
* Respondeu?: Armazena se o usuário respondeu aquela pergunta específica ou não.


## 3. Controladores (Controllers):

3.1 **Tutor**

* Possui como responsabilidade gerir as lógicas as quais se relacionam com os tutores, como a criação, listagem e a sua busca.

* Possui como métodos:
    *  Listar: não havendo inputs mas havendo o output da listagem de objetos tutor  
    *  Buscar: havendo como entrada o nome do tutor e como saída a busca de objetos tutor que possuem aquele nome
    
3.2 **Login**

* Possui como responsabilidades o gerenciamento da autentificação dos usuários, verificando se é administrador ou não, além da criação das sessões específicas para cada uma das partes(usuários normais e administradores).
*Possui como métodos:
    * Tutor: havendo como input o nome e a senha do tutor, e como output a sessão pessoal do usuário.
        
    * Gravar: a qual grava os dados de login, havendo como input os dados do novo tutor e como saída o novo objeto tutor criado.

3.3 **Formulários**

* Possui como responsabilidades a gestão das interações entre usuários e formulários, gerenciando suas interações e a submissão de dados.

* Possui como métodos:
    * Listar: a qual lista formulários não havendo nada como entrada mas retornando uma lista de objetos formulários disponíveis.
    
    * Procurar: a qual procura formulários específicos, havendo o identificador do formulário como entrada e havendo a como saída o objeto formulário.

3.4 **Administradores**

* Possui como responsabilidades a administração do sistema, gerenciando os usuários e o acesso a página de estatísticas(dashboards).

* Possui como métodos:
    * Listar: a qual lista administradores, não havendo um input mas havendo a listagem de objetos usuarios administradores.

    * Dashboard: a qual lista os dados essenciais para o administrador, não havendo input mas havendo as informações estatísticas dos dados coletados para o administrador.



## 4. Views:

### 4.1 MVC Tutores

As views no padrão MVC são responsáveis pela apresentação dos dados ao usuário. Elas exibem informações formatadas e interagem com o usuário, representando a interface com a qual ele interage. Dessa forma, é possível descrever a view do projeto Abandono Zero da seguinte a maneira:

4.1.1 **TelaInicial**

* Navbar: Um guia que facilita a navegação do usuário por diferentes sessões da aplicação Web.

* Carrossel: Uma rolagem de imagens que apresenta algumas informações presentes no site.

* BotaoLogin: Botão que leva ao usuáio realizar o seu login na plataforma.

* ImagemSobre: Campo na qual apresenta imagens do projeto.

* TextoSobre: Apresenta informações sobre o Abandono Zero, como sua história e seus objetivos.

4.1.2 **TelaFormularioFinalizado**

* ImagemFinalizado:Imagem de confirmação acerca do preenchimento do formulário.

* TextoFinalizado: Texto de confirmação do preenchimento do formulário.

* BotaoVoltar: Botão para possibilitar o usuário  voltar para a tela inicial do site.

### 4.2 MVC Formulários

4.2.1 **FormularioGeral**

* Navbar: Um guia que facilita a navegação do usuário por diferentes sessões da aplicação Web.

* TextoPergunta: Pergunta que será feita ao usuário.

* InputResposta: Campo em que o usuário responderá a pergunta feita.

* BotaoEnviar: Botão que o usuário clicará para confirmar o envio da resposta.

4.2.2 **FormularioJaTem**

* Navbar: Um guia que facilita a navegação do usuário por diferentes sessões da aplicação Web.

* InputResposta: Campo em que o usuário responderá a pergunta feita.

* TextoPergunta: Pergunta que será feita ao usuário.

* BotaoEnviar: Botão que o usuário clicará para confirmar o envio da resposta.

4.2.3 **FormularioJaTeve**

* Navbar: Um guia que facilita a navegação do usuário por diferentes sessões da aplicação Web.

* InputResposta: Campo em que o usuário responderá a pergunta feita.

* TextoPergunta: Pergunta que será feita ao usuário.

* BotaoEnviar: Botão que o usuário clicará para confirmar o envio da resposta.

4.2.4 **FormularioQuerTer**

* Navbar: Um guia que facilita a navegação do usuário por diferentes sessões da aplicação Web.

* InputResposta: Campo em que o usuário responderá a pergunta feita.

* TextoPergunta: Pergunta que será feita ao usuário.

* BotaoEnviar: Botão que o usuário clicará para confirmar o envio da resposta.

4.2.5 **FormularioNulo**

* Navbar: Um guia que facilita a navegação do usuário por diferentes sessões da aplicação Web.

* InputResposta: Campo em que o usuário responderá a pergunta feita.

* TextoPergunta: Pergunta que será feita ao usuário.

* BotaoEnviar: Botão que o usuário clicará para confirmar o envio da resposta.

4.2.6 **TelaFormularioFinalizado**

* ImagemFinalizado: Imagem confirmando que o usuário relizou o preenchimento do formulário.

* TextoFinalizado: Texto confirmando que o usuário realizou o preenchimento do formulário.

* BotaoVoltar: Botão para possibilitar o usuário voltar para a tela inicial do site.

### 4.3 MVC Administradores

4.3.1 **Home**

* Navbar: Serve como barra de navegação para facilitar o acesso a diferentes partes do site.

* Graficos: Graficos que possibilitam ao administrador vizualizar os dados de uma forma mais lúdica

* Dropbox: Caixa de opções que vai mostrar as estatísticas da pesquisa.

* Estatisticas: Mostra uma caixa de texto com as informações da seção dropbox.

* BotaoDownloadRelatorio: Permite ao administrador baixar o relatório provido em arquivo csv.


### 4.4 MVC Login

4.4.1 **TelaLogin**

* Navbar: Serve como barra de navegação para facilitar o acesso a diferentes partes do site.

* ImagemLogin: Logo do site

* InputsNomeEmailSenha: Sessão para o usuário preencher nome, email e senha.

* CheckboxAdmin: Checkbox para verificar se o usuário é administrador ou não.

* BotaoFormulario: Botão para confirmação de envio e ir para os formulários.


## 5. Infraestrutura:
### Banco de Dador:
Um banco de dados é um sistema organizado para armazenar e gerenciar grandes quantidades de dados de forma estruturada. Ele permite que informações sejam inseridas, acessadas, modificadas e excluídas de maneira eficiente, facilitando a recuperação e manipulação de dados conforme necessário para diversas aplicações.

Analisando fatores como escabilidade, familiaridade, desempenho e materiais de consultas disponíveis, escolhemos o banco de dados relacional PostgreSQL.

A integração do banco de dados é feita a partir do Models, pelas entidades so sistemas que interagem com o banco de dados para a realização das operações  de Create, Read, Update, Delete(CRUD). Os models representam a estrutura dos dados e definem como os dados são armazenados, validados e acessados pela aplicação. Os models encapsulam a lógica relacionada aos dados, garantindo sua integridade e consistência.

### APIs Externas:

Para um melhor desempenho que complementariedade do projeto, será utilizada APIs externas, como API dos correios, que permite a obtenção de informações geográficas de usuários, como cidades e bairros, com base no CEP fornecido.

Integradas ao MVC, as APIs externas se relacionam com os Controllers, nas quais recebem as requisições dos usuários, processam e convocam as APIs necessárias, decidindo a partir daí qual view será exibida. Os controllers implementam a lógica de controle da aplicação, decidindo como cada requisição deve ser tratada e coordenando as operações entre as views e os models.


## 6. implicações da Arquitetura:

Utilizando a arquitetura MVC do Sails.js, é permitido uma arquitetura organizada e com um bom desempenho, aumentando a eficiencia do desenvolvimento da aplicação Web.

Dessa forma:

* **Estrutura Organizada**: O Sails segue o padrão MVC, o que facilita a organização e separação de responsabilidades no desenvolvimento da aplicação. Isso torna o código mais modular, fácil de entender e de dar manutenção.

* **Flexibilidade e Escalabilidade:** O Sails é flexível e permite integrar facilmente com diferentes tecnologias e bibliotecas.

* **Comunidade Ativa**: O Sails possui uma comunidade ativa e uma vasta documentação que facilita o aprendizado e solução de problemas. Há uma grande variedade de plugins e extensões disponíveis que ampliam as capacidades do framework.



# Conclusão

O projeto Abandono Zero utiliza a arquitetura MVC (Model-View-Controller) com o framework Sails.js para desenvolver uma aplicação web focada em combater o abandono de animais.

Essa escolha arquitetural proporciona uma estrutura organizada e modular, facilitando o desenvolvimento, manutenção e escalabilidade da aplicação. 

Com a separação clara de responsabilidades entre models, view e controllers, o projeto está preparado para oferecer uma experiência eficiente e funcional aos usuários, enquanto busca seu objetivo de entender e mitigar o problema do abandono de animais.





## Recursos Adicionais:
Documentação do Sails.js: https://github.com/balderdashy/sails Tutorial do draw.io: https://m.youtube.com/watch?v=w3zm-wbmlpc Exemplos de diagramas MVC: https://www.lucidchart.com/pages/templates