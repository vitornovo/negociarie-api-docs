Autenticação da API
============

**Necessário**

Para autenticar na API, será necessário possuir os seguintes dados: ``client_id`` e ``client_secret``

Para fazer a autenticação na API é necessário fazer uma requisição POST na rota::

	https://sistema.negociarie.com.br/api/login

Deverá ser enviado na requisição um JSON, com as seguintes informações::

	{
		"client_id":"3",
		"client_secret":"ONe7Ns48Y30tB",
	}

O resultado da requisição da rota /api/login será semelhante a este::

	{
		"token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImp0a"
		"token_type":"Bearer"
	}

Nesse momento, você já possui todos os dados necessário para iniciar as chamadas na rota da API.
Em todas as rotas da API, será necessário enviar o TOKEN que foi recebido na rota /api/login.
O TOKEN que deve ser enviado no Authorization no header do request, é formado pelo token_type + access_token, no caso do exemplo acima o token ficaria da seguinte forma::

	Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImp0a

Exemplo de chamada em uma rota, enviando os dados do Token::

	curl -X GET
	--header "Accept:application/json"
	--header "Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImp0aSI6Ijg0MTM2O"
	--header "Content-Type: application/json"
	https://sistema.negociarie.com.br/api/v2/teste

.. warning::

	IMPORTANTE: Veja que o token foi enviado no HEADER da requisição HTTP. Conforme o exemplo acima, podemos observar que o token é enviado sempre no header ``Authorization``. Caso o Token não esteja presente no header ``Authorization`` a API irá responder com o código ``HTTP 401 (Unauthorized)``, não permitindo a utilização da API.