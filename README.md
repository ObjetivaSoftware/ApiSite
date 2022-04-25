# Documentação API - Site

Para consumir a API do site, precisa ser informado um **token-cliente**.
Para conseguir acesso a esse token do cliente, é necessário entrar em contato com o suporte do sistema.

E-mail: contato@objetivasoftware.com.br.

##### Endpoints
- [1 - Informações da Imobiliária](#1---Informações-da-Imobiliária)
	- [PHP](#11---)
	- [Python](#12---)
	- [Node](#13---)
	- [Shell](#14---)
	- [Resposta](#15---Resposta---Informações-da-Imobiliária)

- [2 - Buscar por imóveis](#2---Buscar-por-Imóveis)
	- [PHP](#21---)
	- [Python](#22---)
	- [Node](#23---)
	- [Shell](#24---)
	- [Resposta](#25---Resposta---Buscar-por-Imóveis)

- [3 - Ações de Imóveis (vendas, aluguéis, etc...)](#3---Ações-de-Imóveis)
	- [PHP](#31---)
	- [Python](#32---)
	- [Node](#33---)
	- [Shell](#34---)
	- [Resposta](#35---Resposta---Ações-de-Imóveis)

- [4 - Tipos de Imóveis (casa, partamento, etc...)](#4---Tipos-de-Imóveis)
	- [PHP](#41---)
	- [Python](#42---)
	- [Node](#43---)
	- [Shell](#44---)
	- [Resposta](#45---Resposta---Tipos-de-Imóveis)

- [5 - Cidades](#5---Cidades)
	- [PHP](#51---)
	- [Python](#52---)
	- [Node](#53---)
	- [Shell](#54---)
	- [Resposta](#55---Resposta---Cidades)

- [6 - Bairros](#6---Bairros)
	- [PHP](#61---)
	- [Python](#62---)
	- [Node](#63---)
	- [Shell](#64---)
	- [Resposta](#65---Resposta---Bairros)



## 1 - Informações da Imobiliária

### 1.1 - <a href="#Endpoints"><img src="/img/php.svg" /></a>

```php
 <?php
 
    $client = new http\Client;
    $request = new http\Client\Request;
    
    $body = new http\Message\Body;
    $body->addForm(NULL, NULL);
    
    $request->setRequestUrl('https://api.gestorimob.com.br/imobiliaria');
    $request->setRequestMethod('GET');
    $request->setBody($body);
    
    $request->setHeaders([
        'token-cliente' => 'XXXXXXXXXXXXXX'
    ]);
    
    $client->enqueue($request)->send();
    $response = $client->getResponse();
    
    echo $response->getBody();
    
```
### 1.2 - <a href="#Endpoints"><img src="/img/python.svg" /></a>
```Python

    import requests
    
    url = "https://api.gestorimob.com.br/imobiliaria"
    
    payload = ""
    headers = {
        'token-cliente': "XXXXXXXXXXXXXX",
        'content-type': "multipart/form-data; boundary=---011000010111000001101001"
    }
    
    response = requests.request("GET", url, data=payload, headers=headers)
    
    print(response.text)
    
```
### 1.3 - <a href="#Endpoints"><img src="/img/nodejs.svg" /></a>
```js

    var axios = require("axios").default;
    
    var options = {
        method: 'GET',
        url: 'https://api.gestorimob.com.br/imobiliaria',
        headers: {
            'token-cliente': 'XXXXXXXXXXXXXX',
            'content-type': 'multipart/form-data; boundary=---011000010111000001101001'
        }
    };
    
    axios.request(options).then(function (response) {
        console.log(response.data);
    }).catch(function (error) {
        console.error(error);
    });
    
```
### 1.4 - <a href="#Endpoints"><img src="/img/shell.svg" /></a>
```bash

    curl --request GET \
        --url https://api.gestorimob.com.br/imobiliaria \
        --header 'content-type: multipart/form-data; boundary=---011000010111000001101001' \
        --header 'token-cliente: XXXXXXXXXXXXXX'
    
```
### [1.5 - Resposta - Informações da Imobiliária](#Endpoints)
```js

{
 "r": "ok",
	"data": {
		"basico": {
			"codigo": xx,
			"ativo": 2,
			"cpfcnpj": "xx.xxx.xxx\/xxxx-xx",
			"razao": "Lorem Ipsum Dolor",
			"fantasia": "Lorem Ipsum",
			"logo": "logo.png",
			"creci": "XXXXXX"
		},
		"contato": {
			"telefone": "(xx) xxxx-xxxx",
			"emails": {
			"venda": "xxxxxx@domain.com",
			"locacao": "yyyyyyy@domain.com",
			"condominio": "zzzzzz@domain.com"
			}
		},
		"redessociais": {
			"instagram": "https:\/\/www.instagram.com\/xxxxx\/",
			"waze": "",
			"twitter": "",
			"youtube": "https:\/\/www.youtube.com\/results?search_query=xxxxx",
			"linkedin": "",
			"facebook": "https:\/\/www.facebook.com\/xxxxx\/"
		},
		"horarios": {
			"segsexmanha": "manhã das 09:00 às 12:00",
			"segsextarde": "tarde das 12:00 às 18:00",
			"sabadomanha": "manhã das 09:00 às 21:00",
			"sabadotarde": "tarde das 13:00 às 21:00"
		},
		"localizacao": {
			"completo": "Rua xxxxx, xxxx, yyyy, Centro, Rio de Janeiro, xx",
			"cidade": "Rio de Janeiro",
			"estado": {
				"uf": "xx",
				"nome": "Rio de Janeiro"
			},
			"pais": {
				"nome": "Brasil",
				"ddd": "55"
			},
			"numero": xxx,
			"endereco": "Rua xxxxx",
			"bairro": "Centro",
			"complemento": "yyyyy",
			"cep": "xxxxx-yyy",
			"mapa": {
				"latitude": "-xx.xxxxxx",
				"longitude": "-yy.yyyyyy"
			}
		},
		"dominios": {
			"site": "xxxxx.com.br",
			"img": "img.xxxxx.com.br",
			"tv": "tv.xxxxx.com.br",
			"externo": 1,
			"central": "central.xxxxx.com.br"
		},
		"google": {
			"analytics": {
				"id": "xxxxxxxxx",
				"propriedade": "UA-xxxxxxx-y",
				"verificacao": null
			}
		}
	}		 
}
```
## 2 - Buscar por Imóveis
### 2.1 - <a href="#Endpoints"><img src="/img/php.svg" /></a>
```php

<?php
    
    $client = new http\Client;
    $request = new http\Client\Request;
    
    $body = new http\Message\Body;
    $body->append('{}');
    
    $request->setRequestUrl('https://api.gestorimob.com.br/buscar');
    $request->setRequestMethod('GET');
    $request->setBody($body);
    
    $request->setHeaders([
        'token-cliente' => 'XXXXXXXXXXXXXXXXXXXX',
        'content-type' => 'application/json'
    ]);
    
    $client->enqueue($request)->send();
    $response = $client->getResponse();
    
    echo $response->getBody();
      
```
### 2.2 - <a href="#Endpoints"><img src="/img/python.svg" /></a>
```Python

    import requests
    
    url = "https://api.gestorimob.com.br/buscar"
    
    payload = "{}"
    headers = {
        'token-cliente': "XXXXXXXXXXXXXXXXXXXX",
        'content-type': "application/json"
     }
    
    response = requests.request("GET", url, data=payload, headers=headers)
    
    print(response.text)
      
```
### 2.3 - <a href="#Endpoints"><img src="/img/nodejs.svg" /></a>
```js

    var axios = require("axios").default;
    
    var options = {
        method: 'GET',
        url: 'https://api.gestorimob.com.br/buscar',
        headers: {
            'token-cliente': 'XXXXXXXXXXXXXXXXXXXX',
            'content-type': 'application/json'
        },
        data: {}
    };
    
    axios.request(options).then(function (response) {
        console.log(response.data);
    }).catch(function (error) {
        console.error(error);
    });
      
```
### 2.4 - <a href="#Endpoints"><img src="/img/shell.svg" /></a>
```bash
    curl --request GET \
        --url https://api.gestorimob.com.br/buscar \
        --header 'content-type: application/json' \
        --header 'token-cliente: XXXXXXXXXXXXXXXXXXXX' \
        --data '{}'
```
### [2.5 - Resposta - Buscar por Imóveis](#Endpoints)
```js

{
    "r": "ok",
    "data": [
        {
            "basico": {
                "codigo": "1",
                "ativo": {
                	"codigo": 2,
                	"nome": "Ativo"
                },
                "status": {
                  "codigo": 7,
                  "nome": "Pronto para morar"
                },
                "nacional": {
			"codigo": 1,
			"nome": "Nacional"
                },
                "cadastro": "31\/07\/2021",
                "destaque": "",
                "acao": {
			"codigo": 2,
			"nome": "Comprar",
			"plural": "Vendas"
                },
                "tipo": {
			"codigo": 5,
			"nome": "Casa"
                },
                "usu": 2,
                "moeda": {
			"codigo": 1,
			"nome": "Real"
                }
            },
            "seo": {
		"tags": null,
		"titulo": "titulo-imovel",
		"titulostr": "titulo-imovel-para-url",
		"acessos": 0,
		"descricao": "descricao do imóvel."
            },
            "informacoes": {
		"quarto": {
			"label": "Quartos",
			"icone": "<i class=\"icl ic-bed\"><\/i>",
			"quantidade": 4
                },
                "suite": {
			"label": "Suítes",
			"icone": "<i class=\"icl ic-bed\"><\/i>",
			"quantidade": 4
                },
                "banheiro": {
			"label": "Banheiros",
			"icone": "<i class=\"icl ic-shower\"><\/i>",
			"quantidade": 7
                },
                "cozinha": {
			"label": "Cozinha",
			"icone": "<i class=\"icl ic-knife-kitchen\"><\/i>",
			"quantidade": 1
                },
                "areaservico": {
			"label": "Área Serviços",
			"icone": "<i class=\"icr ic-tools\"><\/i>",
			"quantidade": 2
                },
                "pavimento": {
			"label": "Pavimentos",
			"icone": "<i class=\"icr ic-building\"><\/i>",
			"quantidade": 4
                }
            },
            "portais": {
		"publicado": []
            },
            "localizacao": {
                "completo": "Rua xxxxxx, yy, Centro, Rio de Janeiro, RJ",
                "cep": "22460-180",
                "numero": "yy",
                "endereco": "Rua xxxxxx",
                "complemento": null,
                "bairro": {
			"codigo": 10,
			"nome": "Centro"
                },
                "estado": {
			"codigo": xx,
			"sigla": "RJ",
			"nome": "RJ"
                },
                "cidade": {
			"codigo": xxx,
			"nome": "Rio de Janeiro"
                },
                "mapa": []
                },
                "valores": {
                "alteracaoprevia": 2,
                "valor": "yyyyyyyy.00",
                "valorstr": "R$ yy.yyy.yyy,00",
                "condominio": {
			"valor": "xx.00",
			"valorstr": "R$ xx,00",
			"descricao": "Teste"
                }
            },
            "outros": {
                "ano": null,
                "unidade": 1,
                "exclusividade": 1
            },
            "areas": {
                "vaga": null,
                "lote": "0.00",
                "total": "xxxx.xx",
                "externa": "0.00",
                "dimencao": null,
                "privativa": "0.00",
                "edificada": "yyyy.yy"
            },
            "aceita": [],
            "corretor": {
                "criou": {
			"codigo": xxxx,
			"nome": "Pedro Silva"
            },
            "alterou": {
			"codigo": null,
			"nome": null
                }
            },
            "imagens": [
                {
			"big": "\/\/img.dominiosite.com.br\/imoveis\/nome_imagem.jpg",
			"miniatura": "\/\/img.dominiosite.com.br\/imoveis\/thumb\/nome_imagem.jpg",
			"legenda": "",
			"codigo": x
                }
            ],
            "videos": [],
            "infraestruturas": []
        }
    ]
}
    
```
## 3 - Ações de Imóveis
### 3.1 - <a href="#Endpoints"><img src="/img/php.svg" /></a>
```php

<?php

  $client = new http\Client;
  $request = new http\Client\Request;
  
  $body = new http\Message\Body;
  $body->append('{}');
  
  $request->setRequestUrl('https://api.gestorimob.com.br/acoes');
  $request->setRequestMethod('GET');
  $request->setBody($body);
  
  $request->setHeaders([
        'token-cliente' => 'XXXXXXXXXXXXXXXXXXXX',
        'content-type' => 'application/json'
  ]);
  
  $client->enqueue($request)->send();
  $response = $client->getResponse();
  
  echo $response->getBody();
      
```
### 3.2 - <a href="#Endpoints"><img src="/img/python.svg" /></a>
```Python

    import requests
    
    url = "https://api.gestorimob.com.br/acoes"
    
    payload = "{}"
    headers = {
        'token-cliente': "XXXXXXXXXXXXXXXXXXXX",
        'content-type': "application/json"
    }
    
    response = requests.request("GET", url, data=payload, headers=headers)
    
    print(response.text)
      
```
### 3.3 - <a href="#Endpoints"><img src="/img/nodejs.svg" /></a>
```js

    var axios = require("axios").default;
    
    var options = {
        method: 'GET',
        url: 'https://api.gestorimob.com.br/acoes',
        headers: {
            'token-cliente': 'XXXXXXXXXXXXXXXXXXXX',
            'content-type': 'application/json'
        },
        data: {}
    };
    
    axios.request(options).then(function (response) {
        console.log(response.data);
    }).catch(function (error) {
        console.error(error);
    });
    
      
```
### 3.4 - <a href="#Endpoints"><img src="/img/shell.svg" /></a>
```bash
    curl --request GET \
        --url https://api.gestorimob.com.br/acoes \
        --header 'content-type: application/json' \
        --header 'token-cliente: XXXXXXXXXXXXXXXXXXXX' \
        --data '{}'
    }'
```
### [3.5 - Resposta - Ações de Imóveis](#Endpoints)
```js

{
	"r": "ok",
	"data": [
		{
			"label": "Alugar",
			"value": 1
		},
		{
			"label": "Comprar",
			"value": 2
		},
		{
			"label": "Lançamento",
			"value": 3
		}
	]
}

```
## 4 - Tipos de Imóveis
### 4.1 - <a href="#Endpoints"><img src="/img/php.svg" /></a>
```php

<?php
    
    $client = new http\Client;
    $request = new http\Client\Request;
    
    $body = new http\Message\Body;
    $body->append('{}');
    
    $request->setRequestUrl('https://api.gestorimob.com.br/tipos');
    $request->setRequestMethod('GET');
    $request->setBody($body);
    
    $request->setHeaders([
        'token-cliente' => 'xxxxxxxxxxxxxxxx',
        'content-type' => 'application/json'
    ]);
    
    $client->enqueue($request)->send();
    $response = $client->getResponse();
    
    echo $response->getBody();
      
```
### 4.2 - <a href="#Endpoints"><img src="/img/python.svg" /></a>
```Python

    import requests
    
    url = "https://api.gestorimob.com.br/tipos"
    
    payload = "{}"
    headers = {
        'token-cliente': "xxxxxxxxxxxxxxxx",
        'content-type': "application/json"
    }
    
    response = requests.request("GET", url, data=payload, headers=headers)
    
    print(response.text)
      
```
### 4.3 - <a href="#Endpoints"><img src="/img/nodejs.svg" /></a>
```js

    var axios = require("axios").default;
    
    var options = {
        method: 'GET',
        url: 'https://api.gestorimob.com.br/tipos',
        headers: {'token-cliente': 'xxxxxxxxxxxxxxxx', 'content-type': 'application/json'},
        data: {}
    };
    
    axios.request(options).then(function (response) {
        console.log(response.data);
    }).catch(function (error) {
        console.error(error);
    });
    
    axios.request(options).then(function (response) {
        console.log(response.data);
    }).catch(function (error) {
        console.error(error);
    });
      
```
### 4.4 - <a href="#Endpoints"><img src="/img/shell.svg" /></a>
```bash

    curl --request GET \
        --url https://api.gestorimob.com.br/tipos \
        --header 'content-type: application/json' \
        --header 'token-cliente: xxxxxxxxxxxxxxxx' \
        --data '{}'
        
```
### [4.5 - Resposta - Tipos de Imóveis]
```js

{
	"r": "ok",
	"data": [
		{
			"label": "Apartamento",
			"value": 1
		 },
		 {
		      "label": "Casa",
		      "value": 2
		}
	]
}
  
```
## 5 - Cidades
### 5.1 -<a href="#Endpoints"><img src="/img/php.svg" /></a>
```php

    <?php
    
    $client = new http\Client;
    $request = new http\Client\Request;
    
    $body = new http\Message\Body;
    $body->append('{}');
    
    $request->setRequestUrl('https://api.gestorimob.com.br/cidades');
    $request->setRequestMethod('GET');
    $request->setBody($body);
    
    $request->setHeaders([
        'token-cliente' => 'xxxxxxxxxxx',
        'content-type' => 'application/json'
    ]);
    
    $client->enqueue($request)->send();
    $response = $client->getResponse();
    
    echo $response->getBody();
      
```
### 5.2 - <a href="#Endpoints"><img src="/img/python.svg" /></a>
```Python

    import requests
    
    url = "https://api.gestorimob.com.br/cidades"
    
    payload = "{}"
    headers = {
        'token-cliente': "xxxxxxxxxxx",
        'content-type': "application/json"
    }
    
    response = requests.request("GET", url, data=payload, headers=headers)
    
    print(response.text)
      
```
### 5.3 - <a href="#Endpoints"><img src="/img/nodejs.svg" /></a>
```js

    var axios = require("axios").default;
    
    var options = {
        method: 'GET',
        url: 'https://api.gestorimob.com.br/cidades',
        headers: {'token-cliente': 'xxxxxxxxxxx', 'content-type': 'application/json'},
        data: {}
    };
    
    axios.request(options).then(function (response) {
        console.log(response.data);
    }).catch(function (error) {
        console.error(error);
    });
      
```
### 5.4 - <a href="#Endpoints"><img src="/img/shell.svg" /></a>
```bash
    curl --request GET \
        --url https://api.gestorimob.com.br/cidades \
        --header 'content-type: application/json' \
        --header 'token-cliente: xxxxxxxxxxx' \
        --data '{}'
```
### [5.5 - Resposta - Cidades](#Endpoints)
```js

{
	"r": "ok",
	"data": [
		{
			"label": "Rio de Janeiro",
			"value": xxxx
		}
	]
}

```
## 6 - Bairros
### 6.1 - <a href="#Endpoints"><img src="/img/php.svg" /></a>
```php

<?php
    
    $client = new http\Client;
    $request = new http\Client\Request;
    
    $body = new http\Message\Body;
    $body->append('{}');
    
    $request->setRequestUrl('https://api.gestorimob.com.br/bairros');
    $request->setRequestMethod('GET');
    $request->setBody($body);
    
    $request->setHeaders([
        'token-cliente' => 'xxxxxxxxxxx',
        'content-type' => 'application/json'
    ]);
    
    $client->enqueue($request)->send();
    $response = $client->getResponse();
    
    echo $response->getBody();
      
```
### 6.2 - <a href="#Endpoints"><img src="/img/python.svg" /></a>
```Python

    import requests
    
    url = "https://api.gestorimob.com.br/bairros"
    
    payload = "{}"
    headers = {
        'token-cliente': "xxxxxxxxxxx",
        'content-type': "application/json"
    }
    
    response = requests.request("GET", url, data=payload, headers=headers)
    
    print(response.text)
      
```
### 6.3 - <a href="#Endpoints"><img src="/img/nodejs.svg" /></a>
```js

    var axios = require("axios").default;
    
    var options = {
    method: 'GET',
    url: 'https://api.gestorimob.com.br/bairros',
    headers: {'token-cliente': 'xxxxxxxxxxx', 'content-type': 'application/json'},
    data: {}
    };
    
    axios.request(options).then(function (response) {
       console.log(response.data);
    }).catch(function (error) {
       console.error(error);
    });
      
```
### 6.4 - <a href="#Endpoints"><img src="/img/shell.svg" /></a>
```bash
    curl --request GET \
        --url https://api.gestorimob.com.br/bairros \
        --header 'content-type: application/json' \
        --header 'token-cliente: xxxxxxxxxxx' \
        --data '{}'
```
### [6.5 - Resposta - Bairros](#Endpoints)
```js

{
	"r": "ok",
	"data": [
		{
			"label": "Centro",
			"value": xxx
		}
	]
}
  

```

[Voltar ao topo](#Documentação-API---Site)
