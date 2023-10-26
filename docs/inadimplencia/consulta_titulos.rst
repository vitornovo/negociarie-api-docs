Consulta Títulos
============

Consulta os títulos que estão em cobrança de um determinado devedor::

    GET /api/v2/inadimplencia/titulos


Com os seguintes parâmetros::

    {
        "documento": "99999999999"
    }


**Em caso de erro**::

    {
        "mensagem": "Cliente não encontrado"
    }

**Em caso de sucesso (Status = 200)**::

    {
        "titulos": [
            {
                "id_titulo": 403061,
                "cod_titulo": "8723",
                "valor_original": 100,
                "saldo_devedor": 30,
                "data_vencimento": "2020-01-30",
                "possui_acordo": 1,
                "status": {
                    "id": 800,
                    "descricao": "EM ABERTO"
                }
            },
            {
                "id_titulo": 403062,
                "cod_titulo": "8723",
                "valor_original": 100,
                "saldo_devedor": 100,
                "data_vencimento": "2020-02-28",
                "possui_acordo": 0,
                "status": {
                    "id": 800,
                    "descricao": "EM ABERTO"
                }
            }
        ]
    }

