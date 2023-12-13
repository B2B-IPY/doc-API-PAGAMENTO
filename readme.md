# API 📜

Com API você pode integrar meios de pagamentos e recebimento ao seu sistema.

obs: TODOS os valores devem ser informados como centavos

## URL BASE

 `https://pag.b2btecnologia.io`

## Rotas 


 `post` **/login**
<br>
body:
```
{
	"user":"gustavo",
	"password":"exemplo123"
}
```

<br>
<br>
<br>

## ACCOUNT

 `get` **/account/history/:limit**
<br>

Exemplo: /account/history/:2


Headers:
```
{
	"x-access-token":"token recebido pela rota /login",
}
```
<br>
<br>
<br>

 `post` **/account/historyDate**
<br>

body:
```
{
	"after":"2020-01-01",
	"before":"2023-03-01"
}
```
<br>

Headers:
```
{
	"x-access-token":"token recebido pela rota /login",
}
```
<br>
<br>
<br>

 `get` **/account/pix-key**
<br>

Verifica suas chaves pix

Headers:
```
{
	"x-access-token":"token recebido pela rota /login",
}
```
<br>
<br>
<br>

 `get` **/account/pix-key/:key**
<br>

Exemplo: /account/pix-key/779919221432

Verifica uma chave pix especifica

Headers:
```
{
	"x-access-token":"token recebido pela rota /login",
}
```
<br>
<br>
<br>

 `get` **/account/workspace**
<br>

Verifica informações do seu workspace

Headers:
```
{
	"x-access-token":"token recebido pela rota /login",
}
```
<br>
<br>
<br>

 `get` **/balance**
<br>
Verifica o saldo disponivel em conta

Headers:
```
{
	"x-access-token":"token recebido pela rota /login",
}
```
<br>
<br>
<br>

## PAYMENT
<br>

 `post` **/payment/transfers**


Headers:
```
{
	"x-access-token":"token recebido pela rota /login",
}
```

<br>

Body:
```
{
	"amount": 100,
	"bankCode": "20018183",
	"branchCode": "0001",
	"accountNumber": "10000-0",
	"accountType": "salary",
	"externalId": "my-internal-id-12345",
	"taxId": "276.685.415-00",
	"name": "Tony Stark",
	"tags": ["iron", "suit"]
}
```

<br>
<br>
<br>





 `post` **/payment/request**


Body:
```
{
"amount": 100,
"bankCode": "20018183",
"name": "Tony Stark",
"accountNumber": "10000-0",
"branchCode": "0001",
"centerId": "5657967261122560",
"taxId": "276.685.415-00"
}
```
<br>
Headers:
```
{
	"x-access-token":"token recebido pela rota /login",
}
```

<br>
<br>
<br>









 `post` **/payment/boleto**


Body:
```
{
"taxId": "38.435.677/0001-25",
"description": "Payment for killing white walkers",
"barCode": "34191.09107 05447.947309 71544.640008 8 84660000011631"
}
```
<br>
Headers:
```
{
	"x-access-token":"token recebido pela rota /login",
}
```

<br>
<br>
<br>





 `post` **/payment/preview**


Body:
```
{
	"pixkey":"00020101021226890014br.gov.bcb.pix2567brcode-h.sandbox.starkinfra.com/v2/ace289aac1ce453b9ca64fb12ec525855204000053039865802BR5925Stark Bank S.A. - Institu6009Sao Paulo62070503***63044DDF"
}
```
<br>
Headers:
```
{
	"x-access-token":"token recebido pela rota /login",
}
```

<br>
<br>
<br>



 `post` **/payment/utility**


Body:
```
{
	"taxId": "38.435.677/0001-25",
	"description": "Payment for killing white walkers",
	"barCode": "34191.09107 05447.947309 71544.640008 8 84660000011631"
}
```
<br>
Headers:
```
{
	"x-access-token":"token recebido pela rota /login",
}
```

<br>
<br>
<br>



 `post` **/payment/tax**


Body:
```
{
	"taxId": "38.435.677/0001-25",
	"description": "Payment for killing white walkers",
	"barCode": "34191091070544794730971544640008884660000011631"
}
```
<br>
Headers:
```
{
	"x-access-token":"token recebido pela rota /login",
}
```

<br>
<br>
<br>



 `post` **/payment/transaction**


Body:
```
{
	"amount": 100, 
  	"receiverId": "1029378109327810",
  	"description": "Transaction to dear provider",
  	"externalId": "12345",  
  	"tags": ["provider"]
}
```
<br>
Headers:
```
{
	"x-access-token":"token recebido pela rota /login",
}
```

<br>
<br>
<br>

 `post` **/payment/qr-code**


Body:
```
{
"brcode": "00020101021226890014br.gov.bcb.pix2567brcode-h.sandbox.starkinfra.com/v2/ace289aac1ce453b9ca64fb12ec525855204000053039865802BR5925Stark Bank S.A. - Institu6009Sao Paulo62070503***63044DDF",
"taxId": "012.345.678-90",
"description": "this will be fast"
}
```
<br>
Headers:
```
{
	"x-access-token":"token recebido pela rota /login",
}
```

<br>
<br>
<br>

 `post` **/payment/darf**


Body:
```
{
	"revenueCode": "1240",
	"taxId": "12.345.678/0001-95",
	"competence": "2021-03-01",
	"nominalAmount": 1234,
	"fineAmount": 12,
	"interestAmount": 34,
	"due": "2021-05-12",
	"description": "take my money"
}
```
<br>
Headers:
```
{
	"x-access-token":"token recebido pela rota /login",
}
```

<br>
<br>
<br>

## RECEIVABLE

`post` **/receivable/qr-code/:id**

Exemplo: /receivable/qr-code/12


Headers:
```
{
	"x-access-token":"token recebido pela rota /login",
}
```

<br>
<br>
<br>

`post` **/receivable/boleto**


Body:
```
{
	"amount":"400000",
	"name":"Iron Bank S.A.",
	"taxId":"20.018.183/0001-80", 
	"streetLine1":"Av. Faria Lima, 1844", 
	"streetLine2":"CJ 13",
	"district":"Itaim Bibi", 
	"city":"São Paulo",
	"stateCode":"SP",
	"zipCode":"01500-000"
}
```
<br>
Headers:
```
{
	"x-access-token":"token recebido pela rota /login",
}
```

<br>
<br>
<br>

`get` **/receivable/boleto-holmes/:id**

Exemplo: /receivable/boleto-holmes/5129079703470080


Headers:
```
{
	"x-access-token":"token recebido pela rota /login",
}
```

<br>
<br>
<br>



