Neste repositório você irá encontrar códigos Front-end e Back-end de um site chamado PetDot que tem o propósito a adoção de animais. 
Front-End foi usado HTML, CSS e JS para sua construção e para o Back-end foi utilizado o framework Node.js, mais espeíficadamente o express generator juntamento com o banco de dados SQlite.
Agora detalhando um pouco mais sobre como executar o projeto. Recomendo que você execute o back-end e o front-end separadamente. 
Se for executar o sistema back-end comece instalando o framework do Node.js e siga essa sequência:
npx express-generator pasta --view ejs
cd pasta
npm i ou npm install 
npm install sequelize sqlite3
npm run nodemon
npm start

  O sistema back-end foi pensado em ser no estilo de formulário, no qual você se não tiver nenhum dado inserido poderá inserir, logo após inserir todos os seus dados nos conformes estabelecidos pelos campos, será resgitrado. 
  Tem como opção editar e excluir seus dados se julgar necessário. Obs: Quando for adicionar o seu número de telefone coloque os parênteses.
  
Para vizualizar o projeto digite localhost:3000 no browse.
