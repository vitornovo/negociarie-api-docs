Devolução de Títulos
============

.. warning::
   ATENÇÃO: DEVOLUÇÃO DE TÍTULO GERA HONORÁRIO COM BASE NO SALDO DEVEDOR DO TÍTULO.


Para efetuar devolução (baixas) em títulos que estão em cobrança, utilize URL abaixo::

    POST /api/v2/inadimplencia/devolucao


Para devolver um título, envie o seguintes parâmetros::

    {
        "id_titulo": 1234,
        "valor_devolvido": 50.00,
        "motivo": "Motivo da devolução"
    }

- id_titulo: fornecido pela negociarie na consulta de títulos.
- valor: Valor que está sendo retirado da cobrança, deve ser menor ou igual ao saldo devedor, caso seja enviado um valor MENOR que o valor devido.
- motivo: Motivo da devolução para registro no sistema.

.. note::
    Um título pode ser devolvido por completo ou parcialmente. Nos casos de devolução parcial o valor remanescente continuará sendo cobrado do devedor.

**Em caso de erro (HTTP Status != 200)**::

    {
        "mensagem": "O valor informado é maior que o saldo devedor"
    }


**Em caso de sucesso (Status = 200)**::

    {
        "mensagem": "Devolução solicitada"
    }
