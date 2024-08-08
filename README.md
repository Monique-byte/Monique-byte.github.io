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


Minha contribuição foi a integração do banco de dados SQlite, bem como a ligação das telas do sistema no sequelize. Primeiramente comecei pegando um modelo de projeto exemplar que o professor disponibilizou no moodle, a partir dele comecei a construir e interligar com o trabalho previamente realizado anteriormente. Criei um folder models e integrei SQlite usando este código: const { Sequelize, DataTypes } = require("sequelize");

const sqlite = new Sequelize({
  dialect: "sqlite",
  storage: "../models/db.sqlite", 
});

const Dados = sqlite.define("Dados",
  {
-------- Aqui comecei a puxar minhas entidades do banco (acredito que é isso pq deu certo)
    // Model attributes are defined here
    id: {
      type: DataTypes.INTEGER,
      autoIncrement: true,
      primaryKey: true,
    },
    nome: {
      type: DataTypes.STRING,
      allowNull: false,
    },
    tel: {
      type: DataTypes.STRING,
    },
    email: {
      type: DataTypes.STRING,
    },
    cpf:{
      type: DataTypes.STRING,
    },
    relato:{
      type: DataTypes.TEXT,
    },
  },
  {
    timestamps: true, // habilita os campos de data e hora de criação e atualização
  }
);

// CREATE TABLE IF NOT EXISTS
try {
  Dados.sync();
} catch (error) {
  console.error("Erro ao sincronizar tabela:", error);
}

module.exports = Dados;



Além disso adicionei as devidas rotas necessárias que estão no código back-end. As telas do formulário preferi colocar como POST. E fiz funcionar o textArea.
