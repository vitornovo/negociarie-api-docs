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
                "id": 51346,
                "quebrado": 0,
                "autorizado": 1,
                "quitado": 0,
                "data_acordo": "2022-04-30 14:17:50",
                "boleto_pdf": null,
                "id_acordo": 51346,
                "parcelas": [
                    {
                        "data_vencimento": "2022-05-07",
                        "data_pagamento": null,
                        "valor_parcela": 167.11,
                        "boleto_pdf": "https://negociarie.nyc3.digitaloceanspaces.com/boletos/51346_248467_220430_626d6f3e8a094.pdf",
                        "desconto_pontualidade": 20,
                        "id_parcela": 248467,
                        "valor_parcela_com_desconto": 133.69,
                    }
                ],
                "valor_total_com_desconto": 133.69
            }
        ]
    }


