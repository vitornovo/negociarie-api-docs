Consulta
============

Consulta da situação atual de cobrança, essa chamada trás as parcelas da cobrança que possui o IDENTIFICADOR GERAL informado::

    GET /api/v2/cobranca/consulta


Com os seguintes parâmetros::

    {
        "identificador_geral": 55
    }


**Em caso de erro (cobrança não encontrada)**::

    {
        "mensagem": "Cobrança não encontrada"
    }


**Em caso de sucesso (Status = 200)**::

    {
        "parcelas": [
            {
                "id_parcela": "8723",
                "id_status": 800,
                "status": "PAGA",
                "link": "https://sistema.negociarie.com.br/.../boleto-8723.pdf', "status": "Liquidação",
                "data_vencimento": "2020-01-10",
                "data_pagamento": "2020-01-12",
                "valor": 100.00,
                "valor_pago":103.00,
                "valor_mora": 2.00,
                "valor_multa": 1.00
            },
            {
                "id_parcela": "8724",
                "id_status": 801,
                "status": "EM ABERTO",
                "link": "https://sistema.negociarie.com.br/.../boleto-8724.pdf' "status": "Entrada Confirmada",
                "data_vencimento": "2020-01-10",
                "data_pagamento": null,
                "valor": 100.00,
                "valor_pago": null,
                "valor_mora": null,
                "valor_multa": null
            }
        ]
    }
