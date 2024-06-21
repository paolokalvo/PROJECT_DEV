Meu Projeto de Gerenciamento de Cruzeiros
Sobre
Este projeto é um sistema de gerenciamento de cruzeiros que permite associar passageiros a cruzeiros específicos. Utiliza MySQL como banco de dados e oferece funcionalidades para registrar passageiros e atribuí-los aos cruzeiros.

Índice
Sobre
Instalação
Desafio Proposto
SQL
Licença
Contato
Instalação
Clone o repositório:

bash
Copiar código
git clone https://github.com/seu-usuario/nome-do-repositorio.git
Configure seu ambiente conforme necessário.

Desafio Proposto
Neste desafio, você deve entender e comentar cada comando SQL usado para criar e popular as tabelas passageiro e cruzeiro_passageiro. Abaixo estão os comandos SQL:

SQL
sql
Copiar código
-- Criação da tabela cruzeiro_passageiro
CREATE TABLE `cruzeiro_passageiro` (
  `cruzeiro_codigo` int(11) NOT NULL,
  `passageiro_codigo` int(11) NOT NULL,
  KEY `FK7ACB9DA2547B48BD` (`passageiro_codigo`),
  KEY `FK7ACB9DA2E971C35D` (`cruzeiro_codigo`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

-- Inserção de dados na tabela cruzeiro_passageiro
INSERT INTO `cruzeiro_passageiro` (`cruzeiro_codigo`, `passageiro_codigo`) VALUES 
(1, 1),
(1, 2),
(2, 2),
(2, 3);

-- Criação da tabela passageiro
CREATE TABLE `passageiro` (
  `codigo` int(11) NOT NULL auto_increment,
  `cpf` varchar(255) NOT NULL,
  `dataNascimento` date NOT NULL,
  `nome` varchar(255) NOT NULL,
  `sexo` varchar(255) NOT NULL,
  PRIMARY KEY  (`codigo`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1 AUTO_INCREMENT=4;

-- Inserção de dados na tabela passageiro
INSERT INTO `passageiro` (`codigo`, `cpf`, `dataNascimento`, `nome`, `sexo`) VALUES 
(1, '111111111', '1986-01-22', 'Rafael', 'Masculino'),
(2, '111111111', '2014-09-08', 'Henrique', 'Feminino'),
(3, '11111111', '2014-09-22', 'Nathalia', 'Feminino');

-- Adicionando restrições de chave estrangeira na tabela cruzeiro_passageiro
ALTER TABLE `cruzeiro_passageiro`
  ADD CONSTRAINT `FK7ACB9DA2547B48BD` FOREIGN KEY (`passageiro_codigo`) REFERENCES `passageiro` (`codigo`),
  ADD CONSTRAINT `FK7ACB9DA2E971C35D` FOREIGN KEY (`cruzeiro_codigo`) REFERENCES `cruzeiro` (`codigo`);
Comentários dos Comandos SQL
CREATE TABLE cruzeiro_passageiro: Cria uma tabela que associa passageiros a cruzeiros, utilizando chaves estrangeiras para referenciar as tabelas passageiro e cruzeiro.

INSERT INTO cruzeiro_passageiro: Insere dados na tabela cruzeiro_passageiro, associando passageiros aos cruzeiros específicos.

CREATE TABLE passageiro: Cria uma tabela para armazenar informações dos passageiros, como código, CPF, data de nascimento, nome e sexo.

INSERT INTO passageiro: Insere dados na tabela passageiro, registrando informações de três passageiros diferentes.

ALTER TABLE cruzeiro_passageiro: Adiciona restrições de chave estrangeira na tabela cruzeiro_passageiro para garantir que os códigos de passageiros e cruzeiros estejam de acordo com os registros nas tabelas passageiro e cruzeiro, respectivamente.

Licença
Este projeto é licenciado sob [inserir licença]. Consulte o arquivo LICENSE para obter mais detalhes.

Contato
Para sugestões ou dúvidas, entre em contato através do email seu-email@exemplo.com.

Neste exemplo, substitua [inserir licença], [seu-email@exemplo.com], e outros placeholders com informações específicas do seu projeto. Certifique-se de adaptar o conteúdo para refletir precisamente o propósito e os detalhes do seu projeto.
