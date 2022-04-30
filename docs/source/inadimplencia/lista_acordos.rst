Acordos
============

Para listar todos os acordos efetuados utilize a URL abaixo::

    GET /api/v2/inadimplencia/acordos

**Em caso de erro (HTTP Status != 200)**::

    {
        "mensagem": "Falha ao processar sua solicitação"
    }


**Em caso de sucesso (Status = 200)**::

    {
        "acordos": [
            {
                "data_acordo": "2019-08-30 14:35:29",
                "quebrado": 1,
                "autorizado": 1,
                "quitado": 0,
                "boleto_pdf": "https://negociarie.nyc3.digitaloceanspaces.com/boletos/6722_PARCELAS_190830_5d696264bffd9.pdf",
                "id_acordo": 6722,
                "parcelas": [
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
                                "parcela_id": 181106,
                                "titulo_id": 54495,
                                "saldo_anterior": 220.29,
                                "saldo_posterior": 0
                            }
                        ]
                    },
                    {
                        "data_vencimento": "2019-10-10",
                        "data_pagamento": null,
                        "data_baixa_manual": null,
                        "valor_parcela": 312.51,
                        "valor_pago": null,
                        "boleto_pdf": "https://negociarie.nyc3.digitaloceanspaces.com/boletos/",
                        "desconto_pontualidade": 20,
                        "id_parcela": 37975,
                        "valor_parcela_com_desconto": 250.01
                    }
                ],
                "valor_total_com_desconto": 1750.06
            }
        ]
    }

