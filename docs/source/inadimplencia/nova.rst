Nova
============

Para criar um novo devedor ou adicionar títulos a um devedor existente, utilize esta URL::

    POST /api/v2/inadimplencia/nova

Para adicionar títutos para cobrança envie na requisição um JSON com as seguintes informações::

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
            "telefones": [
                "(17)99999-9999",
                "(17)99999-9999",
                "(17)99999-9999"
            ],
            "email": "email@email.com"
        },

        "titulos": [
            {
                "cod_titulo": "8723",
                "data_vencimento": "2020-01-30",
                "valor_original": 100.00,
                "saldo_devedor": 30.00,
                "numero_parcela": 1
            },
            {
                "cod_titulo": "8723",
                "data_vencimento": "2020-02-28",
                "valor_original": 100.00,
                "numero_parcela": 2
            }
        ]
    }


O exemplo acima, possui alguns prarâmetros, que serão explicados abaixo:

Campos obrigatórios: *

cliente: objeto com os dados do cliente que será criado as parcelas da cobrança simples
    - \* documento: CPF ou CNPJ, pode ser com pontos ou sem pontos. Caso seja um cliente que já possua cadastro na NEGOCIARIE, apenas o documento é obrigatório.
    - \* nome: Nome completo do cliente ou nome fantasia caso PJ
    - razao_social: Razão social caso PJ. Para PF não é necessário enviar.
    - cep: CEP do endereço, pode ser com ou sem traço.
    - endereco: Nome da rua (Logradouro).
    - numero: Número da residência
    - complemento: Complemento caso possua (ex: AP 105 B)
    - cidade: Nome da cidade,
    - uf: Estado com 2 letras (Ex: SP, MG)
    - \* telefones: Lista (array) com os telefones
    - email:  **CAMPO OPICIONAL** E-mail do cliente

titulos: Lista (array) com as títulos que serão incluídos no sistema para cobrança
    - \* codigo Identificador do título em questão no sistema do cliente.
    - \* data_vencimento: Data de vencimento no formato Y-m-d (Ex:"2022-12-30")
    - \* valor: Valor original da dívida sem atualização
    - saldo_devedor: **CAMPO OPICIONAL** - Exemplo de uso: Dívida de 100,00. Cliente pagou 10,00, o saldo devedor é 90. Ou seja, o documento da dívida é de 100,00 mas já existiu um pagamento. A cobrança, valor do honorários e correção para cobrança serão feitos baseados no saldo devedor.
    - numero_parcela: Número da parcela caso seja parcela (para facilitar identificação)
    - observacao: **CAMPO OPICIONAL** -  Informações adicionais que possam ser relevantes para a cobrança.


Em caso de erro::

    {
        "mensagem": "Documento inválido"
    }


Em caso de sucesso::

    {
        "mensagem": "Títulos incluídos com sucesso"
    }