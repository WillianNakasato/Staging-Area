# Staging-Area

#Criando o usuário Schema da Staging Area 

CREATE TABLESPACE TBS_STAGE
LOGGING DATAFILE '/u01/app/oracle/oradata/orcl/TBS_STAGE.dbf' 
SIZE 1M AUTOEXTEND ON NEXT 10M MAXSIZE UNLIMITED EXTENT MANAGEMENT LOCAL SEGMENT SPACE MANAGEMENT AUTO;

# Cria o schema
CREATE USER starea IDENTIFIED BY starea0123;
GRANT CONNECT, RESOURCE TO starea;
GRANT UNLIMITED TABLESPACE TO starea;

# Garante privilégios para o usuário starea copiar dados das tabelas do usuário source
grant select on source.TB_CADASTRO_CLIENTE  to starea;
grant select on source.TB_ENDERECO to starea;
grant select on source.TB_PRODUTO  to starea;
grant select on source.TB_CATEGORIA to starea;
grant select on source.TB_LOCALIDADE to starea;
grant select on source.TB_PEDIDOS to starea;
grant select on source.TB_ITENS_PEDIDO to starea;

