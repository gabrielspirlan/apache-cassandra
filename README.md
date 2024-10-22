# Trabalho de Banco de Dados Não Relacional - Apache Cassandra

- Gabriel Resende Spirlandelli
- 3° Semestre - Desenvolvimento de Software Multiplataforma


## Criação da column family Carros
create table fatec.carros (
    id uuid,
    marca text,
    placa text,
    modelo text,
    cor text,
    combustivel set<text>,
    ano_fabric int,
    preco decimal,    
    primary key (marca, placa)
);


## Inserções
insert into fatec.carros (id, marca, placa, modelo, cor, combustivel, ano_fabric, preco) values 
(uuid(), 'Toyota', 'ABC-1234', 'Corolla', 'Preto', {'Gasolina'}, 2020, 90000);

insert into fatec.carros (id, marca, placa, modelo, cor, combustivel, ano_fabric, preco) values 
(uuid(), 'Honda', 'XYZ-5678', 'Civic', 'Prata', {'Gasolina', 'Alcool'}, 2021, 110000);

insert into fatec.carros (id, marca, placa, modelo, cor, combustivel, ano_fabric, preco) values 
(uuid(), 'Ford', 'DEF-2345', 'EcoSport', 'Branco', {'Diesel'}, 2019, 80000);

insert into fatec.carros (id, marca, placa, modelo, cor, combustivel, ano_fabric, preco) values 
(uuid(), 'Chevrolet', 'GHI-3456', 'Onix', 'Vermelho', {'Alcool'}, 2022, 95000);

insert into fatec.carros (id, marca, placa, modelo, cor, combustivel, ano_fabric, preco) values 
(uuid(), 'Volkswagen', 'JKL-4567', 'Gol', 'Azul', {'Gasolina', 'Alcool'}, 2020, 70000);

insert into fatec.carros (id, marca, placa, modelo, cor, combustivel, ano_fabric, preco) values 
(uuid(), 'Fiat', 'MNO-5678', 'Argo', 'Cinza', {'Gasolina'}, 2021, 85000);

insert into fatec.carros (id, marca, placa, modelo, cor, combustivel, ano_fabric, preco) values 
(uuid(), 'Renault', 'PQR-6789', 'Duster', 'Preto', {'Diesel'}, 2018, 75000);

insert into fatec.carros (id, marca, placa, modelo, cor, combustivel, ano_fabric, preco) values 
(uuid(), 'Nissan', 'STU-7890', 'Kicks', 'Branco', {'Gasolina', 'Alcool'}, 2022, 100000);



## Atualizações
update fatec.carros
set combustivel = combustivel + {'Alcool'}
where placa = 'ABC-1234' and marca = 'Toyota';

update fatec.carros
set preco = 80000
where placa = 'MNO-5678' and marca = 'Fiat';

update fatec.carros
set modelo = 'Polo'
where placa = 'JKL-4567' and marca = 'Volkswagen';



## Exclusão de um registro
delete from fatec.carros 
where placa = 'GHI-3456' and marca = 'Chevrolet';


