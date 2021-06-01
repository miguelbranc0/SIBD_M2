# SIBD_M2
# Proposta de trabalho
Pretendemos abordar o sistema de vendas de uma marca de sapatos, criando uma base de dados que contempla:

- características do produto (nome, família, referência, cor, tamanho nas diferentes escalas, composição/materiais);

- Informação sobre as lojas (local, nome, número, vendedores (nome, número, loja associada), stock);

- Informação sobre os armazéns (local, número, stock)

- escritórios (nome, número, local, lojas que gerem, departamentos (nome/função)

- cliente (nome, número de telefone, morada, idade, género, compras(produto (nome, família, referência, cor, tamanho nas diferentes escalas, composição/materiais) data , preço, desconto(percentagem, valorAbsoluto, tipoDesconto))

É uma marca de sapatos americana com uma sede administrativa na península ibérica e fabrico em vários países como a China e o Brasil.

# Utilizador

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

![image](https://user-images.githubusercontent.com/75800165/120394294-1fd51380-c32b-11eb-9ff3-8a9d599fdf4b.png)

![image](https://user-images.githubusercontent.com/75800165/120394448-5743c000-c32b-11eb-8510-d7c79ac8f70a.png)

Da associação  “faz” Compra
















