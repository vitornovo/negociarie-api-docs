Bem vindo à documentação da API Negociarie!
===================================

**Negociarie** é uma empresa de cobrança que possui esta API para permitir
que sistemas de terceiros enviem e recebam informações de forma automática.

Para obter as informações necessárias para utilziar esta API, entre em contato com
a NEGOCIARIE (contato@negociarie.com.br) e solicite suas credenciais.

Para autenticação da API, deve ser enviado um token em todos os requests, para obter o token veja a seção Autenticação.

.. success::
    Todas as requisições bem succedidas serão retornadas com ``HTTP 200 (OK)``

.. error::
    As requisições mal succedidas possuem o atributo ``mensagem`` informando o erro e poderão ter diversos tipos de retorno a depender do erro, exemplos:
    ``HTTP 400 (Bad Request)``, ``HTTP 401 (Unauthorized)``, ``HTTP 403 (Forbidden)``, ``HTTP 406 (Not Acceptable)``.


.. toctree::

    autenticacao
    cobranca-simples/index
    inadimplencia/index
