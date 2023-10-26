Parcelas pagas
============

Consulta da situação de todas as parcelas pagas em um determinado dia::

    GET /api/v2/inadimplencia/parcelas-pagas


    {
        "data": "2020-01-12"
    }



**Em caso de erro (cobrança não encontrada)**::

    {
        "mensagem": "Erro desconhecido"
    }


**Em caso de sucesso (Status = 200)**::

    {
        "qtd_parcelas_pagas": 1,
        "valor_total": 330.5,,
        "parcelas_pagas": [
            {
                "data_vencimento": "2019-09-07",
                "data_pagamento": "2019-10-10,
                "data_baixa_manual": null,
                "valor_parcela": 312.5,
                "valor_pago": 330.5,
                "desconto_pontualidade": 20,
                "id_parcela": 37974,
                "valor_parcela_com_desconto": 250,
                "titulos_abatidos": [
                    {
                        "parcela_id": 181106,
                        "titulo_id": 54495,
                        "saldo_anterior": 220.29,
                        "saldo_posterior": 0
                    }
                ]
            }
        ]
    }
