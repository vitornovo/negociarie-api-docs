Baixa Manual
============

.. note::
   A BAIXA DE PARCELAS É APENAS UMA INDICAÇÃO AO SISTEMA, NÃO É NECESSÁRIO ENVIAR O VALOR PAGO À NEGOCIARIE POIS NÃO HAVERÁ REPASSE DOS VALORES DAS PARCELAS BAIXADAS.


Baixa de uma parcela
------------

Para efetuar baixas manuais em boletos emitidos utilize a URL abaixo::

    POST /api/v2/cobranca/baixa_manual


Para baixar apenas uma parcela, envie o ID_PARCELA gerado pela negociarie no momento da criação da cobrança simples::

    {
        "id_parcela": 8723
    }

**Em caso de erro (HTTP Status != 200)**::

    {
        "mensagem": "Parcela não encontrada"
    }


**Em caso de sucesso (Status = 200)**::

    {
        "mensagem": "Parcela baixada com sucesso"
    }



Baixa de todas as parcelas de uma cobrança
------------

Para baixar todos as parcelas de uma cobrança, enviar o IDENTIFICADOR GERAL da cobrança::

    {
        "identificador_geral": 55
    }


**Em caso de erro (HTTP Status != 200)**::

    {
        "mensagem": "Cobrança não encontrada"
    }


**Em caso de sucesso retorna a lista de parcelas baixadas**::

    {
        "parcelas": [
            {
                "id_parcela": "8723",
                "link": "https://sistema.negociarie.com.br/.../boleto-8723.pdf',
            },
            {
                "id_parcela": "8724",
                "link": "https://sistema.negociarie.com.br/.../boleto-8724.pdf',
            }
        ]
    }
