
##  Parte 01 – Reverse Engineering

Nessa primeira parte, eu analisei o código para entender o que ele faz, já que ele não tinha uma documentação clara.

Percebi que a classe `PedidoProcessor` tem como principal função processar pedidos. Ela faz várias coisas ao mesmo tempo, como validar dados, calcular valores (subtotal, desconto, frete e juros), aplicar regras de negócio e gerar mensagens de retorno.

Também consegui identificar várias regras de negócio dentro do código, por exemplo:

* O desconto varia de acordo com o tipo de cliente
* O frete muda dependendo do país e do peso
* Existem cupons que alteram o valor do pedido
* O pagamento no cartão pode gerar juros
* Alguns cenários geram alertas, como pedidos muito altos ou suspeitos

Além disso, analisei os parâmetros do método principal e adicionei comentários no código explicando o que cada um representa.

---

##  Parte 02 – Redocumentação

Nessa etapa, eu foquei em deixar o código mais fácil de entender.

Fiz melhorias como:

* Troquei nomes de variáveis por nomes mais claros
* Organizei melhor o código em partes (validação, cálculo, pagamento)
* Adicionei comentários explicando as regras de negócio

Também criei um diagrama de classes simples para representar melhor as entidades envolvidas, como pedido, cliente e itens.

---

##  Parte 03 – Reestruturação

Na última parte, eu analisei a estrutura do código e percebi que a classe estava fazendo muitas coisas ao mesmo tempo.

Isso não é uma boa prática, porque dificulta a manutenção e o entendimento do sistema.

Então, propus uma melhoria separando as responsabilidades em diferentes classes, como:

* PedidoService
* FreteService
* DescontoService
* PagamentoService
* NotificacaoService
* LogService

Com isso, o código fica mais organizado, mais fácil de manter e mais próximo das boas práticas de desenvolvimento, como Clean Code e o princípio da responsabilidade única.

---

##  Conclusão

Com essa atividade, consegui entender melhor como analisar um código existente, melhorar sua documentação e propor melhorias estruturais. Isso é muito importante na Engenharia de Software, principalmente quando lidamos com sistemas já existentes.
Eu dividi o trabalho em três partes: primeiro eu analisei o código para entender como ele funciona, depois melhorei a organização e os comentários para facilitar o entendimento, e por fim propus uma nova estrutura separando as responsabilidades, deixando o código mais organizado e seguindo boas práticas.

