Inadimplência
============

.. danger::
    ATENÇÃO: API EM CONSTRUÇÃO, MÉTODOS INDISPONÍVEIS. REQUESTS E RETORNOS PODERÃO SER ALTERADOS.

**Necessário**

Para fazer requisições, você necessita do TOKEN obtido na etapa Autenticação


As requisições sobre inadimplência (Envio de títulos vencidos para a cobrança), devem ser feitos na rota::

	/api/v2/inadimplencia


Abaixo estão todas as funções que serão implementadas


.. toctree::
    :caption: Funções da API de inadimplência

    nova
    consulta_titulos
    devolucao_titulos
    lista_acordos
    baixa_parcelas
    callback-url