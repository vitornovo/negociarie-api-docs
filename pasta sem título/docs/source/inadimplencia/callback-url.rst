URL de Callback
============

Quando houve baixa ou pagamento parcela da parcela de um acordo, o sistema da negociarie poderá enviar
uma notificação (POST) para uma URL cadastrada com os seguintes dados::

    {
        "documento": "99999999999",
        "parcela_paga": [
            {
                "data_vencimento": "2019-09-07",
                "data_pagamento": "2019-10-10,
                "data_baixa_manual": null,
                "valor_parcela": 312.5,
                "valor_pago": 330.5,
                "boleto_pdf": "https://negociarie.nyc3.digitaloceanspaces.com/boletos/",
                "desconto_pontualidade": 20,
                "id_parcela": 37974,
                "valor_parcela_com_desconto": 250,
                "titulos_abatidos": [
                    {
                        "id_titulo": 52067,
                        "saldo_anterior": 220.29,
                        "saldo_posterior": 0
                    }
                ]
            }
        ]
    }
