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


Entidades:   
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
Associações  
inclui(ESCRITÓRIO, DEPARTAMENTO)   
comunicaCom(DEPARTAMENTO, VENDEDOR)  
contém(LOJA, PRODUTO)  
tem(ARMAZEM, PRODUTO)  
faz(CLIENTE, COMPRAS)  
de(COMPRA, PRODUTO)  
trabalhaEm(VENDEDOR, LOJA)  

