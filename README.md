Engenharia Reversa e Refatoração de Código

Este projeto tem como objetivo realizar a análise, redocumentação e reestruturação de um código legado responsável pelo processamento de pedidos.

🔎 Parte 01 – Reverse Engineering
✔ Responsabilidade da Classe

A classe PedidoProcessor é responsável por:

Processar pedidos
Validar dados do cliente
Calcular valores (subtotal, desconto, frete, juros)
Aplicar regras de negócio
Gerar alertas
Enviar notificações
Registrar logs
✔ Regras de Negócio Identificadas
Cálculo de subtotal com base nos itens
Adição de taxas por categoria (ALIMENTO, IMPORTADO)
Desconto baseado no tipo de cliente:
VIP: 15%
PREMIUM: 10%
NORMAL: 2%
NOVO: sem desconto
Aplicação de cupons:
DESC10, DESC20, FRETEGRATIS, VIP50
Cálculo de frete:
Nacional (BR) por peso
Internacional com valores maiores
Taxa adicional para entrega expressa
Cálculo de juros no cartão:
Até 6x: 2%
Acima de 6x: 5%
Regras de pagamento:
Boleto: desconto fixo
PIX: desconto maior
Validações:
Pedido válido
Cliente não bloqueado
Itens válidos
Email e endereço
Regras adicionais:
Total nunca pode ser negativo
Alerta para pedidos acima de 1000
Validação extra para pedidos acima de 5000 para clientes novos
Limite de boleto acima de 3000
Alerta para pedidos internacionais abaixo de 100
✔ Significado dos Parâmetros
pedidoId: Identificador do pedido
nomeCliente: Nome do cliente
emailCliente: Email do cliente
tipoCliente: Categoria do cliente (VIP, PREMIUM, etc.)
itens: Lista de produtos do pedido
cupom: Código promocional
formaPagamento: Tipo de pagamento
enderecoEntrega: Local de entrega
pesoTotal: Peso total para cálculo de frete
entregaExpressa: Indica frete rápido
clienteBloqueado: Status do cliente
enviarEmail: Define envio de notificação
salvarLog: Define registro de logs
pais: Define se é nacional ou internacional
parcelas: Número de parcelas
🧾 Parte 02 – Redocumentação
✔ Melhorias realizadas
Renomeação de variáveis para nomes descritivos
Organização do código por blocos (validação, cálculo, pagamento)
Substituição de estruturas menos legíveis
Adição de comentários explicativos
Separação lógica das regras de negócio
📊 Diagrama de Classes (Conceitual)
Pedido
- id
- cliente
- itens
- total

Cliente
- nome
- email
- tipo

ItemPedido
- nome
- categoria
- quantidade
- preco

Pagamento
- tipo
- parcelas

Frete
- tipo
- valor
🚀 Parte 03 – Reestruturação
❌ Problemas encontrados
Classe com muitas responsabilidades
Alto acoplamento
Difícil manutenção
Código pouco escalável
✅ Solução Proposta

Separação em múltiplos serviços:

PedidoService
DescontoService
FreteService
PagamentoService
NotificacaoService
LogService
💡 Benefícios da Reestruturação
Código mais organizado
Fácil manutenção
Melhor legibilidade
Possibilidade de testes unitários
Escalabilidade
🏆 Conclusão

Foi realizada a refatoração aplicando princípios de Clean Code e SOLID, principalmente o princípio da responsabilidade única (SRP), visando melhorar a organização, clareza e manutenção do sistema.
