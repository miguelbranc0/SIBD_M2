# SIBD_M2
# C1: VENDE+ #  
## Grupo SIBD04 #
- Marco Amaro Oliveira @MarcoOliveira 
- A037262 Bárbara Oliveira  @a037262Barbara
-	A037005 Miguel Branco
-	A037353 Paula Rocha

##  Descrição #
Pretendemos abordar o sistema de vendas de uma marca de sapatos, criando uma base de dados que contempla:

- características do produto (nome, família, referência, cor, tamanho nas diferentes escalas, composição/materiais);

- Informação sobre as lojas (local, nome, número, vendedores (nome, número, loja associada), stock);

- Informação sobre os armazéns (local, número, stock)

- escritórios (nome, número, local, lojas que gerem, departamentos (nome/função)

- cliente (nome, número de telefone, morada, idade, género, compras(produto (nome, família, referência, cor, tamanho nas diferentes escalas, composição/materiais) data , preço, desconto(percentagem, valorAbsoluto, tipoDesconto))

É uma marca de sapatos americana com uma sede administrativa na península ibérica e fabrico em vários países como a China e o Brasil.

# C2: Interface do usuário

## Interface e Recursos Comuns
### Sketchs


## Utilizador

Utilizador: o utilizador deste sistema é um vendedor de uma das lojas que a marca possui na Península Ibérica. No seu dia-a-dia, o vendedor tem de:
-	esclarecer os clientes em relação aos produtos – disponibilidade, composição, tamanhos etc.; 
-	conhecer o contexto dos escritórios de forma a poder comunicar com os departamentos a quem tem de enviar relatórios, por exemplo;
-	Conhecer outras lojas para reencaminhar o cliente (em caso de limitações de stock) ou pedir transferência de produtos;
-	Conhecer os armazéns da empresa e ter acesso a stocks;
-	Pedir transferência, quando necessário;
-	Consultar as fichas de cliente, cujo acesso lhe revela informações importantes para a venda e outros procedimentos relacionados com as necessidades do cliente (trocas e devoluções).   





Tendo em conta o seu cargo, este utilizador precisa de todas as informações acima descritas. 


# MODELO EA


## Entidades:   
PRODUTO  
LOJA    
ARMAZÉM  
ESCRITÓRIO  
CLIENTE   
VENDEDOR  
DEPARTAMENTO  
COMPRA  
Atributos:  
PRODUTO (nomeProduto, família, referência, cor, tamanho, composição, quantidade)  
LOJA (moradaLoja (rua, numeroPorta, cidade, país), nomeLoja, númeroLoja)  
ARMAZÉM (moradaArmazem (rua, numeroPorta, cidade, país) númeroArmazem)  
ESCRITÓRIO (nomeEscritório, númeroEscritório, morada)  
CLIENTE (nome, númeroTLM, moradaCliente (rua, numeroPorta, cidade, país), idade, género)  
COMPRA (dataCompra, valorCompra, desconto (percentagem, valorAbsoluto, tipoDesconto))  
VENDEDOR (númeroVendedor, nomeVendedor)  
DEPARTAMENTO (nomeDepartamento)  
## Associações:  

inclui(ESCRITÓRIO, DEPARTAMENTO)   
comunicaCom(DEPARTAMENTO, VENDEDOR)  
contém(LOJA, PRODUTO)  
tem(ARMAZEM, PRODUTO)  
faz(CLIENTE, COMPRAS)  
de(COMPRA, PRODUTO)  
trabalhaEm(VENDEDOR, LOJA)  

## Mapa  do site

![image](https://user-images.githubusercontent.com/75800165/120381451-57878f80-c31a-11eb-89b7-d439064714a5.png)



# Regras de Negócio Adicionais

Quando um cliente pretende trocar ou devolver um produto, o vendedor que o recebe na loja acede à sua ficha de cliente para confirmar todos os dados da transação. 
Em caso de troca, só a poderá efetuar se a compra tiver sido feita há menos de 30 dias. A data da compra indica este período. 
Os produtos só são enviados para a loja quando o vendedor faz um pedido.

# Modelo Relacional

## Relações a partir das Entidades

![image](https://user-images.githubusercontent.com/75800165/120383000-3c1d8400-c31c-11eb-9d3b-84423134668c.png)

![image](https://user-images.githubusercontent.com/75800165/120383238-8e5ea500-c31c-11eb-973a-ec343f4903da.png)

![image](https://user-images.githubusercontent.com/75800165/120383374-b64e0880-c31c-11eb-930c-908c09820b32.png)

![image](https://user-images.githubusercontent.com/75800165/120383607-ff05c180-c31c-11eb-9afb-0c110ebf451d.png)

![image](https://user-images.githubusercontent.com/75800165/120392172-01b9e400-c328-11eb-8698-7a131de315f8.png)

![image](https://user-images.githubusercontent.com/75800165/120393243-80635100-c329-11eb-9245-16a8b7c359d6.png)

![image](https://user-images.githubusercontent.com/75800165/120393325-a38e0080-c329-11eb-93e3-61b09530d751.png)

![image](https://user-images.githubusercontent.com/75800165/120393409-cb7d6400-c329-11eb-8afe-5ca20c862c7b.png)

## Relações das associações

Da associação “contém”

![image](https://user-images.githubusercontent.com/75800165/120393577-0e3f3c00-c32a-11eb-84ce-8f5ccb6d7c97.png)

Da associação “tem”

![image](https://user-images.githubusercontent.com/75800165/120393940-ac330680-c32a-11eb-8c88-6e346b51a6af.png)

Da associação "inclui"

![image](https://user-images.githubusercontent.com/75800165/120394013-c4a32100-c32a-11eb-9d77-8a1e41bd15a5.png)

Da associação “trabalhaEm”

![image](https://user-images.githubusercontent.com/75800165/120394175-f916dd00-c32a-11eb-83f0-bd5a18fe83b5.png)

![image](https://user-images.githubusercontent.com/75800165/120394448-5743c000-c32b-11eb-8510-d7c79ac8f70a.png)

Da associação  “faz” Compra

![image](https://user-images.githubusercontent.com/75800165/120395410-d7b6f080-c32c-11eb-80ba-577c3d23b2e7.png)

![image](https://user-images.githubusercontent.com/75800165/120395559-164cab00-c32d-11eb-84e0-ca6d89f2c920.png)

![image](https://user-images.githubusercontent.com/75800165/120395646-3bd9b480-c32d-11eb-85c6-6ddd1f1b1874.png)

# Normalização

## Relação “Produto”

![image](https://user-images.githubusercontent.com/75800165/120395748-70e60700-c32d-11eb-9be9-e798f5029267.png)

![image](https://user-images.githubusercontent.com/75800165/120395840-92df8980-c32d-11eb-8df4-de4e40b65a1e.png)

![image](https://user-images.githubusercontent.com/75800165/120395866-9e32b500-c32d-11eb-8967-78d3151920eb.png)


2NF da Relação “Produto”  
Já está na 2NF

3NF da Relação “Produto”  

nomeProduto -> cor  
nomeProdutofamília

![image](https://user-images.githubusercontent.com/75800165/120395986-cd492680-c32d-11eb-96b9-d139776c66f5.png)

![image](https://user-images.githubusercontent.com/75800165/120396043-dcc86f80-c32d-11eb-97f3-243a898c785b.png)

## Relação “Loja”

![image](https://user-images.githubusercontent.com/75800165/120396141-f669b700-c32d-11eb-9b0f-3fdc228ca0b6.png)

1NF da Relação “Loja”  
Já está na 1NF  

2NF da Relação “Loja”  
Já está na 2NF  

3NF da Relação “Loja”  

nomeLoja-->rua  
nomeLoja-->numeroPorta  
nomeLoja-->cidade  
nomeLoja-->país  

![image](https://user-images.githubusercontent.com/75800165/120396482-87409280-c32e-11eb-82a7-1d6c99b6fc41.png)

![image](https://user-images.githubusercontent.com/75800165/120396517-932c5480-c32e-11eb-86c8-94b906bb74b1.png)

## Relação “Armazém”

![image](https://user-images.githubusercontent.com/75800165/120396562-a7705180-c32e-11eb-91f7-b3f08a4c7bcd.png)

1NF da Relação “Armazém”  
Já está na 1NF  

2NF da Relação “Armazém”  
Já está na 2NF  

3NF da Relação “Armazém”  
Já está na 3NF

## Relação “Escritório”

![image](https://user-images.githubusercontent.com/75800165/120396651-d981b380-c32e-11eb-8c42-c61e59dc8c88.png)

1NF da Relação “Escritório”   
 Já está na 1NF  

2NF da Relação “Escritório”   
Já está na 2  

3NF da Relação “Escritório”  

![image](https://user-images.githubusercontent.com/75800165/120396753-0209ad80-c32f-11eb-86da-753513a9198c.png)

## Relação “Cliente”

![image](https://user-images.githubusercontent.com/75800165/120396838-28c7e400-c32f-11eb-81ac-0af453808da9.png)

1NF da Relação “Cliente”   
Já está na 1NF  

2NF da Relação “Cliente”   
Já está na 2NF  

3NF da Relação “Cliente”   
Já está na 3NF  

## Relação “Compra”

![image](https://user-images.githubusercontent.com/75800165/120397009-79d7d800-c32f-11eb-8225-31e467030c90.png)

1NF da Relação “Compra”  
Já está na 1NF  

2NF da Relação “Compra”  
Já está na 2NF  

3NF da Relação “Compra”  

percentagemDesconto-->valorAbsolutoDesconto  

(o tipoDesconto não depende nem está dependente de nada. É uma indicação fornecida à parte sobre o tipo de desconto)  

![image](https://user-images.githubusercontent.com/75800165/120397117-9e33b480-c32f-11eb-8954-c77f2f1e5168.png)

## Relação “Vendedor”

![image](https://user-images.githubusercontent.com/75800165/120397154-af7cc100-c32f-11eb-9733-8149ce7c7647.png)

1NF da Relação “Vendedor”  
Já está na 1NF  

2NF da Relação “Vendedor”  
Já está na 2NF  
 
3NF da Relação “Vendedor”  
Já está na 3NF  

## Relação “Departamento”

![image](https://user-images.githubusercontent.com/75800165/120397206-ca4f3580-c32f-11eb-8ff7-da08eec91ce9.png)

1NF da Relação “Departamento”  
Já está na 1NF  

2NF da Relação “Departamento”  
Já está na 2NF  

3NF da Relação “Departamento”  
Já está na 3NF  

## Relação “Produto”

### Da Associação “contém”

1NF da Relação “Produto” Da associação “contém”  

númeroLoja depende de tamanho  
tamanho --> númeroLoja  

![image](https://user-images.githubusercontent.com/75800165/120397341-1a2dfc80-c330-11eb-922e-b94de8595097.png)

2NF da Relação “Produto” Da associação “contém”  
Já está na 2NF  

## Relação “Produto”

### Da Associação “tem”

1NF da Relação “Produto” Da associação “tem”

![image](https://user-images.githubusercontent.com/75800165/120397485-4e092200-c330-11eb-86ec-d43ebd6cfb8c.png)

2NF da Relação “Produto” Da associação “tem”  
Já está na 2NF  

## Relação “Departamento”

### Da Associação “inclui”

![image](https://user-images.githubusercontent.com/75800165/120397595-7d1f9380-c330-11eb-8346-8595ab15c4c1.png)

1NF da Relação “Departamento” Da associação “inclui”  
Já está na 1NF  


2NF da Relação “Departamento” Da associação “inclui”  
Já está na 2NF  

## Relação “Vendedor”

### Da Associação “trabalhaEm”

![image](https://user-images.githubusercontent.com/75800165/120397735-c374f280-c330-11eb-8006-3aa7aa6895b3.png)

1NF da Relação “Vendedor” Da associação “trabalhaEm”  
Já está na 1NF  


2NF da Relação “Vendedor” Da associação “trabalhaEm”  
Já está na 2NF  

## Relação “Vendedor”

### Da Associação “comunicaCom”

![image](https://user-images.githubusercontent.com/75800165/120397806-e901fc00-c330-11eb-863e-d79e010f2a66.png)


1NF da Relação “Vendedor” Da associação “comunicaCom”  
Já está na 1NF  


2NF da Relação “Vendedor” Da associação “comunicaCom”  
Já está na 2NF  

## Relação “Compra”

### Da Associação “faz”

![image](https://user-images.githubusercontent.com/75800165/120397874-0b941500-c331-11eb-9dfa-95ed95c5d6a2.png)

1NF da Relação “Compra” Da associação “faz”  
Já está na 1NF  


2NF da Relação “Compra” Da associação “faz”  
Já está na 2NF  

## Relação “Produto”

### Da Associação “de”

![image](https://user-images.githubusercontent.com/75800165/120397960-32eae200-c331-11eb-9403-cb623660227c.png)


1NF da Relação “Produto” Da associação “de”  
Já está na 1NF  


2NF da Relação “Produto” Da associação “de”  
Já está na 2NF  

## Relação “Solicitar”

### Da Associação “solicitaProdutoA”

![image](https://user-images.githubusercontent.com/75800165/120398042-5877eb80-c331-11eb-9011-3fea02f64926.png)

1NF da Relação “Solicitar” Da associação “solicitaProdutoA”  
Já está na 1NF  


2NF da Relação “Solicitar” Da associação “solicitaProdutoA”  
Já está na 2NF  

# SQL

-	Disponibilidade de um sapato de um certo tamanho e modelo  

SELECT: quantidade  
FROM: Produto  
WHERE: tamanho=37  
AND nomeProduto=Hilary  



-	Saber  composição deste produto (Hilary)  

SELECT: composição  
FROM: Produto  
WHERE: nomeProduto =Hilary  



-	Saber qual o escritório de Madrid  

SELECT: *  
FROM: Escritório  
WHERE: nomeEscritorio = nEscritórioMadrid  






-	Ver em que loja está o produto  

SELECT: #nímeroloja  loja  
FROM: OProduto  
WHERE: referência = 1  
AND quantidade = 1  
AND tamanho = 37  


-	Saber em que armazéns há sapatos altos  

SELECT: #numeroArmazém --> Armazem  
FROM: Produto  
WHERE: familia = SapatoAlto  



-	Consultar pedidos de transferência de um armazém  

SELECT: #referÊncia --> Produto  
FROM: Solicitar  
WHERE: #númeroArmazem  Armazém = 2  






-	Consultar compras de um cliente.  

SELECT: refCompra  
FROM: Compras  
WHERE: #numeroTLM  Cliente = 917564935  











































