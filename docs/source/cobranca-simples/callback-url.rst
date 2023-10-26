URL de Callback
============

Quando houve baixa, cancelamento ou qualquer movimentação de uma parcela, o sistema da negociarie poderá enviar
uma notificação (POST) para uma URL cadastrada com os seguintes dados::

    {
        "client_id": "ID FORNECIDO PELA NEGOCIARIE",
        "parcelas": [
            {
                "id_parcela": "8723",
                "link": "https://sistema.negociarie.com.br/.../boleto-8723.pdf',
                "status": "Liquidação",
                "data_vencimento": "2020-01-10",
                "data_pagamento": "2020-01-12",
                "valor": 100.00,
                "valor_pago":103.00,
                "valor_mora": 2.00,
                "valor_multa": 1.00
            },
            {
                "id_parcela": "8724",
                "link": "https://sistema.negociarie.com.br/.../boleto-8724.pdf',
                "status": "Entrada Confirmada",
                "data_vencimento": "2020-01-10",
                "data_pagamento": null,
                "valor": 100.00,
                "valor_pago": null,
                "valor_mora": null,
                "valor_multa": null
            }
        ]
    }

Os valores de status_id / status podem ser:
- 1 - Baixa
- 2 - Liquidação
- 3 - Títulos em Carteira (Em Ser)
- 4 - Entrada Confirmada
- 5 - Aguardando confirmação de registro do banco
- 6 - Outros
