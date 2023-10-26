Parcelas pagas por dia
============

Consulta da situação de todas as parcelas pagas em um determinado dia::

    GET /api/v2/cobranca/parcelas-pagas

    {
        "data": "2020-01-12"
    }


**Em caso de erro (cobrança não encontrada)**::

    {
        "mensagem": "Erro desconhecido"
    }


**Em caso de sucesso (Status = 200)**::

    {
        "qtd_parcelas_pagas": 2,
        "valor_total": 100.90,
        "parcelas_pagas": [
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
            }
        ]
    }
