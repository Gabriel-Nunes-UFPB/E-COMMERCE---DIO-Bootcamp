# E-COMMERCE---DIO-Bootcamp

#README: Projeto Conceitual de Banco de Dados para E-commerce

##Descrição do Projeto
----------------------------------------------------------------------------------------------------------------------------------------------------------------
Este projeto consiste no desenvolvimento de um modelo conceitual de banco de dados para um sistema de e-commerce. O objetivo é fornecer um rascunho para gerenciar todas as operações essenciais de um negócio online, incluindo clientes, pedidos, pagamentos, produtos, fornecedores, estoque e entregas.

##Entidades Principais
----------------------------------------------------------------------------------------------------------------------------------------------------------------
1. Cliente

    Descrição: Armazena informações sobre os clientes do e-commerce.

    Atributos:

        idCliente (INT): Identificador único do cliente.

        Nome (VARCHAR): Nome do cliente.

        Identificação (VARCHAR): CPF (para Pessoa Física) ou CNPJ (para Pessoa Jurídica).

        Endereço (VARCHAR): Endereço do cliente.

        Tipo Cliente (VARCHAR): Indica se o cliente é Pessoa Física (PF) ou Pessoa Jurídica (PJ).

2. Pagamento

    Descrição: Gerencia as transações financeiras realizadas pelos clientes.

    Atributos:

        idPagamento (INT): Identificador único do pagamento.

3. Pedido

    Descrição: Registra os pedidos feitos pelos clientes.

    Atributos:

        idPedido (INT): Identificador único do pedido.

        StatusDoPedido (VARCHAR): Status atual do pedido (por exemplo, "Pendente", "Enviado", "Entregue").

        Descrição (VARCHAR): Descrição do pedido.

        Cliente_idCliente (INT): Chave estrangeira que vincula o pedido ao cliente.

        Frete (FLOAT): Custo do frete associado ao pedido.

        Status da Entrega_idStatus da Entrega (VARCHAR): Chave estrangeira para o status da entrega.

4. Produto

    Descrição: Armazena informações sobre os produtos disponíveis para venda.

    Atributos:

        idProduto (INT): Identificador único do produto.

        Categoria (VARCHAR): Categoria do produto (por exemplo, "Eletrônicos", "Roupas").

        Descrição (VARCHAR): Descrição detalhada do produto.

        Valor (DECIMAL): Preço do produto.

5. Fornecedor

    Descrição: Gerencia os fornecedores dos produtos.

    Atributos:

        idFornecedor (INT): Identificador único do fornecedor.

        RazãoSocial (VARCHAR): Nome oficial do fornecedor.

        CNPJ (VARCHAR): CNPJ do fornecedor.

6. Estoque

    Descrição: Controla o estoque dos produtos.

    Atributos:

        idEstoque (INT): Identificador único do estoque.

        Local (VARCHAR): Localização do estoque.

7. Status da Entrega

    Descrição: Rastreia o status da entrega dos pedidos.

    Atributos:

        idStatus da Entrega (VARCHAR): Identificador único do status da entrega.

        Pedido_idPedido (INT): Chave estrangeira que vincula o status ao pedido.

        Pedido_Cliente_idCliente (INT): Chave estrangeira que vincula o status ao cliente.

        TempoParaEntrega (TIME): Tempo estimado para a entrega.

        Código de Rastreio (VARCHAR): Código de rastreio da entrega.

        Status Atual (VARCHAR): Status atual da entrega (por exemplo, "Em trânsito", "Entregue").

8. Terceiro - Vendedor

    Descrição: Gerencia vendedores terceirizados que também oferecem produtos no sistema.

    Atributos:

        idTerceiro - Vendedor (INT): Identificador único do vendedor.

        Razão Social (VARCHAR): Nome oficial do vendedor.

        Local (VARCHAR): Localização do vendedor.

        CNPJ/CPF (VARCHAR): CNPJ ou CPF do vendedor.

9. Forma de Pagamento

    Descrição: Define as formas de pagamento disponíveis (cartão de crédito, débito, PIX).

    Atributos:

        idCartaoCredito (INT): Identificador único para pagamentos com cartão de crédito.

        idCartaoDebito (INT): Identificador único para pagamentos com cartão de débito.

        idPix (INT): Identificador único para pagamentos via PIX.

Relacionamentos Principais

    Cliente_has_Pagamento:

        Relaciona Cliente com Pagamento.

        Um cliente pode ter vários pagamentos, e um pagamento está associado a um único cliente.

    Pagamento_has_Forma de Pagamento:

        Relaciona Pagamento com Forma de Pagamento.

        Um pagamento pode ser feito por uma ou mais formas de pagamento (cartão de crédito, débito, PIX).

    Relação de produto por pedido:

        Relaciona Produto com Pedido.

        Um pedido pode conter vários produtos, e um produto pode estar em vários pedidos.

    Disponibilizando um Produto:

        Relaciona Produto com Fornecedor.

        Um produto pode ser fornecido por um ou mais fornecedores.

    Produto_has_Estoque:

        Relaciona Produto com Estoque.

        Um produto pode estar em vários estoques, e um estoque pode conter vários produtos.

    Produtos por vendedor:

        Relaciona Produto com Terceiro - Vendedor.

        Um produto pode ser vendido por um ou mais vendedores terceirizados.

    Status da Entrega:

        Relaciona Pedido com Status da Entrega.

        Cada pedido tem um status de entrega associado.
