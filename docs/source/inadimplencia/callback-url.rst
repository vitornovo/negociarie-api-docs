URL de Callback
============

Quando houve baixa ou pagamento parcela da parcela de um acordo, o sistema da negociarie poderá enviar
uma notificação (POST) para uma URL cadastrada com os seguintes dados::

    {
        "documento": "99999999999",
        "parcela_paga": {
            "id_parcela": 123,
            "id_acordo": 10,
            "data_pagamento": "2022-04-15",
            "valor_pago": 200.00,
            "valor_abatido_divida_original": 120.00,

            "titulos_alterados": [
                {
                    "cod_titulo": "8723",
                    "valor_abatido": 100.00
                    "saldo_devedor_anterior": 100.00
                    "saldo_devedor_posterior": 0.00
                },
                {
                    "cod_titulo": "8723",
                    "valor_abatido": 20.00
                    "saldo_devedor_anterior": 50.00
                    "saldo_devedor_posterior": 30.00
                },
            ]
        }
    }
