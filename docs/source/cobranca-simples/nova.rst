Nova
============

Para criar um novo cliente e emitir boletos, utilize esta URL::

    POST /api/v2/cobranca/nova

Deverá ser enviado na requisição um JSON, com as seguintes informações::

    {
        "cliente": {
            "documento": "999.999.999-99",
            "nome": "JOÃO DOS SANTOS",
            "razao_social": "",
            "cep": "14784-011",
            "endereco": "Avenida Brasil",
            "numero": "100",
            "complemento": "",
            "cidade": "Barretos",
            "uf" : "SP",
            "celular": "(17)99999-9999",
            "email": "email@email.com"
        },

        id_geral: 55,

        "parcelas": [
            {
                "id_parcela": "8723"
                "data_vencimento": "2020-01-30",
                "valor": 100.00,
                "mensagem": "linha 1\nlinha 2\nlinha 3\nlinha 4",

                "desconto_pontualidade": {
                    "valor_desconto": 20.00,
                    "data_limite": "2020-01-30"
                }
            },
            {
                "id_parcela": "8724"
                "data_vencimento": "2020-02-28",
                "valor": 100.00,
                "mensagem": "linha 1\nlinha 2\nlinha 3\nlinha 4",
                "desconto_pontualidade": {
                    "valor_desconto": 20.00,
                    "data_limite": "2020-02-28"
                }
            }
        ]
    }


O exemplo acima, possui alguns prarâmetros, que serão explicados abaixo:

Campos obrigatórios: *.

cliente: objeto com os dados do cliente que será criado as parcelas da cobrança simples
    - \* documento: CPF ou CNPJ, pode ser com pontos ou sem pontos. Caso seja um cliente que já possui cadastro na NEGOCIARIE, apenas o documento é obrigatório.
    - \* nome: Nome completo do cliente ou nome fantasia caso PJ
    - \* razao_social: Razão social caso PJ. Para PF não é necessário enviar.
    - \* cep: CEP do endereço, pode ser com ou sem traço.
    - \* endereco: Nome da rua (Logradouro).
    - \* numero: Número da residência
    - complemento: Complemento caso possua (ex: AP 105 B)
    - \* cidade: Nome da cidade,
    - \* uf: Estado com 2 letras (Ex: SP, MG)
    - \* celular: Celular do cliente, para este número será enviado os boletos gerados. Enviar DDD + número, com ou sem caracteres especiais.
    - email": E-mail do cliente

id_geral: Identificador da cobrança no sistema do cliente -> A cobrança pode ter X parcelas (boletos). Este ID_GERAL será a chave para identificar essa cobrança. Caso não seja enviado, o sistema gerará um ID_GERAL automaticamente. Armazene este número para futuras consultas.

parcelas: Lista (array) com as parcelas (boletos) que serão criadas no sistema
    - \* id_parcela: Identificador da parcela em questão no sistema do cliente (para consultas futuras)  -> DEVE SER ÚNICO****************
    - \* data_vencimento: Data de vencimento no formato Y-m-d (Ex:"2022-12-30")
    - \* valor: Valor da parcela, decimal (Ex: 100.52),
    - mensagem: máximo de 100 caracteres por linha e 4 linhas, cada linha é separado por \n. Caracteres adicionais serão ignorados.

    - desconto_pontualidade: desconto de pontualidade no boleto caso exista, atributo opcional.
        - valor_desconto: 20.00, // valor do desconto a ser aplicado
        - data_limite: data limite para aplicação do desconto no formato Y-m-d (Ex:"2022-12-30"). Deve ser menor ou igual a data de vencimento.



Em caso de erro::

    {
        "mensagem": "Documento inválido"
    }


Em caso de sucesso::

    {
        "id_geral": 55,
        "mensagem": "Boletos recebidos com sucesso, a confirmação de registro dos boletos será enviada para a URL cadastrada no sistema da NEGOCIARIE.",
        "carne_pdf": "link para o carne (3 boletos por página)",
        "boletos_pdf": "link para os boletos (1 boleto por página)",
        "parcelas": [
            {
                "id_parcela": "8723",
                "link": "https://sistema.negociarie.com.br/.../boleto-8723.pdf'
            },
            {
                "id_parcela": "8724",
                "link": "https://sistema.negociarie.com.br/.../boleto-8724.pdf'
            }
        ]
    }