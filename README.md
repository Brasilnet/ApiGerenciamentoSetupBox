# ApiGerenciamentoSetupBox
Documentação dos métodos da API

brasilnet

Introdução
API para a criação de SetTopBox e adição do mesmo em planos

Autenticação
A autenticação para acesso às APIs são feitos por API Token ou Bearer Token. Para identificar o Token do usuário basta acessar a área administrative, e em Core Usuários basta selecionar algum e o token deste usuário é um dos ultimos campos.

Para adicionar o token de autenticação, o mesmo deve ser passado como HEADER http.
Exemplo via curl com Token:

curl --request \
  -H 'Authorization: Token 60aaXXXXXXXYYYYY9ca61074860' GET \
  --url 'http://{{servidor}}/api/settopbox/'
Exemplo via curl com Bearer Token:

curl --request \
  -H 'Authorization: Bearer 60aaXXXXXXXYYYYY9ca61074860' GET \
  --url 'http://{{servidor}}/api/settopbox/'
Language
STBs

GET Lista Settopbox 
http://{{servidor}}/api/settopbox/


Sample Request
Lista Settopbox
curl --request GET \
  --url 'http://{{servidor}}/api/settopbox/'
GET Lista Planos 
http://{{servidor}}/api/plan/


Sample Request
Lista Planos
curl --request GET \
  --url 'http://{{servidor}}/api/plan/'
POST Cadastra settopbox 
http://{{servidor}}/api/settopbox/
HEADERS
Content-Typeapplication/json
BODY
{
  "serial_number": "LALALA1",
  "mac": "00:1A:D0:30:A7:E6",
  "description": "Este é um teste por post 1",
  "plan": "empresa-plano"
}


Sample Request
Cadastra settopbox
curl --request POST \
  --url 'http://{{servidor}}/api/settopbox/' \
  --header 'Content-Type: application/json' \
  --data '{
  "serial_number": "LALALA1",
  "mac": "00:1A:D0:30:A7:E6",
  "description": "Este é um teste por post 1",
  "plan": "empresa-plano"
}'
GET Busca 1 STB pelo id 
http://{{servidoe}}/api/settopbox/56/
HEADERS
Content-Typeapplication/json

Sample Request
Busca 1 STB pelo id
curl --request GET \
  --url 'http://{{servidoe}}/api/settopbox/56/' \
  --header 'Content-Type: application/json'
simple

GET Cria STB ou modifica plano 
http://{{servidor}}/add_stb/?plan=empresa-plano&serial=MEUSUPERSERIAL&mac=00:00:00:00:00:00
PARAMS
planempresa-plano
serialMEUSUPERSERIAL
mac00:00:00:00:00:00

GET Busca STB pelo SERIAL e MAC

http://{servidor}/api/settopbox/?serial_number={SERIAL_NUMBER}&mac={MAC}

GET Busca STB pelo SERIAL

http://{servidor}/api/settopbox/?serial_number={SERIAL_NUMBER}

GET Busca STB pelo MAC

http://{servidor}/api/settopbox/?mac={MAC}
