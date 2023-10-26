Baixa de Parcelas
============

A baixa de parcelas é utilizada para baixar manualmente um boleto de um acordo caso o devedor pague diretamente para o credor.

.. warning::
   ATENÇÃO: BAIXA DE PARCELAS GERAM HONORÁRIOS COM BASE NO VALOR DA PARCELA COM DESCONTO, INDEPENDENTE DO VALOR RECEBIDO DIRETAMENTE DO DEVEDOR.

.. note::
    BAIXA DE PARCELAS GERAM ABATIMENTO NOS TÍTULOS QUE ESTÃO EM COBRANÇA.


Baixa de uma parcela
------------

Para efetuar baixas manuais em parcelas de um acordo utilize esta URL::

    POST /api/v2/inadimplencia/baixa_parcela


Para baixar uma parcela, envie o ID_PARCELA e ID_ACORDO gerados pela NEGOCIARIE::

    {
        "id_acordo": 10,
        "id_parcela": 245
    }

**Em caso de erro (HTTP Status != 200)**::

    {
        "mensagem": "Parcela não encontrada"
    }


**Em caso de sucesso (Status = 200)**::

    {
        "mensagem": "Parcela baixada com sucesso"
    }




Baixa de todas parcelas do acordo (Quitação total)
------------

Para realizar a quitação total de um acordo envie o ID_ACORDO e uma intrução de quitação total::

    {
        "id_acordo": 55,
        "quitacao_total": 1
    }


**Em caso de erro (HTTP Status != 200)**::

    {
        "mensagem": "Acordo não encontrado"
    }


**Em caso de sucesso (Status = 200)**::

    {
        "mensagem": "Quitação do acordo realizada"
    }
