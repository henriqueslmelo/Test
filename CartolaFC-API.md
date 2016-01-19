# CartolaFC API

Essas informações não são oficiais da API, portanto não é garantido que o padrão de consulta seja mantido ou que a disponibilidade da API seja uma garantia.
***

### Informações sobre a rodada atual

[http://api.cartola.globo.com/mercado/status.json](http://api.cartola.globo.com/mercado/status.json)

```json
{
	"mercado": {
		"status": 1,
		"times_escalados": 641864,
		"fechamento": {
			"hora": 16,
			"ano": 2015,
			"minuto": 30,
			"dia": 30,
			"mes": 5
		},
		"rodada": 4
	}
}
```

### Buscar times (consulta padrão)

[http://api.cartola.globo.com/time/busca.jsonp?nome=cartolafc](http://api.cartola.globo.com/time/busca.jsonp?nome=cartolafc)

A API retorna o total de times, nesse caso 178 e são exibidos os 20 primeiros que é o padrão de itens por página.

```json
busca (
{
	"start": 0,
	"total": 178,
	"times": [
	{
		"imagens_escudo": {
			"img_escudo_160x160": "http://s.glbimg.com/es/ca/escudos/times/9e/95/escudo_160x160_time_10031954.png",
			"img_escudo_32x32": "http://s.glbimg.com/es/ca/escudos/times/9e/95/escudo_32x32_time_10031954.png"
		},
		"sigla_escudo": "C.F.C",
		"cor_primaria_escudo": "f7f821",
		"nome": "CARTOLAFCS",
		"tipo_camisa": 1,
		"cor_secundaria_escudo": "d9d9d9",
		"cor_adorno": "050319",
		"tipo_escudo": 3,
		"slug": "cartolafcs",
		"tipo_adorno": 9,
		"cor_terciaria_escudo": "181818",
		"nome_cartola": "BRUNOCESAR",
		"img_escudo": 1,
		"cor_terciaria_camisa": "181818",
		"cor_secundaria_camisa": "d9d9d9",
		"clube_id": 262,
		"id": 10031954,
		"cor_primaria_camisa": "f7f821"
}
)
```


### Buscar times (paginação)

Caso queira retornar os próximos 20 times, utilize o parâmetro &start=21 e assim por diante.

[http://api.cartola.globo.com/time/busca.jsonp?nome=cartolafc&start=21](http://api.cartola.globo.com/time/busca.jsonp?nome=cartolafc&start=21)


### Buscar times (listando mais ou menos de 20 times por página)

Existe também a possibilidade de exibir mais ou menos times por página, utilize o parâmetro &rows=40. Claro, você pode exibir a quantidade que quiser!

[http://api.cartola.globo.com/time/busca.jsonp?nome=cartolafc&row=40](http://api.cartola.globo.com/time/busca.jsonp?nome=cartolafc&row=40)

[http://api.cartola.globo.com/time/busca.jsonp?nome=cartolafc&row=5](http://api.cartola.globo.com/time/busca.jsonp?nome=cartolafc&row=5)


### Informações sobre um time

Você pode utilizar o ID do time ou o CADUN_ID.

ID: 
[http://api.cartola.globo.com/time/cadun/40424774/info.json](http://api.cartola.globo.com/time/cadun/40424774/info.json)

CADUN_ID: 
[http://api.cartola.globo.com/time/id/9459952/info.json](http://api.cartola.globo.com/time/id/9459952/info.json)

### Buscar os jogadores do time

Essa busca retorna os jogadores do time que estão escalados na rodada atual, pode consultar com o ID do time ou o CADUN_ID.

CADUN_ID:
[http://api.cartola.globo.com/time_adv/cadun/40424774.json](http://api.cartola.globo.com/time_adv/cadun/40424774.json)

ID:
http://api.cartola.globo.com/time_adv/slb-encarnados.json

```json
{
	"atleta": [],
	"time": {
		"imagens_escudo": {
			"img_escudo_160x160": "http://s.glbimg.com/es/ca/escudos/times/23/b7/escudo_160x160_time_9459952.png",
			"img_escudo_32x32": "http://s.glbimg.com/es/ca/escudos/times/23/b7/escudo_32x32_time_9459952.png"
		},
		"esquema": 3,
		"nome": "SLB Encarnados",
		"patrimonio": 131.29,
		"rodada": 3,
		"cadun_id": 40424774,
		"nome_cartola": "Nome do cartola",
		"slug": "slb-encarnados",
		"pontuacao": "60.20"
	}
}
```

### Buscar rodada anterior do time

Você tem que utilizar o CADUN_ID do time após o parâmetro ID e o número da rodada após o parâmetro RODADA

Lembra?
CADUN_ID: http://api.cartola.globo.com/time/id/9459952/info.json

Rodada 1:
[http://api.cartola.globo.com/time/id/9459952/rodada/1/info.json](http://api.cartola.globo.com/time/id/9459952/rodada/1/info.json)

Rodada 2:
[http://api.cartola.globo.com/time/id/9459952/rodada/2/info.json](http://api.cartola.globo.com/time/id/9459952/rodada/2/info.json)

Rodada 3:
[http://api.cartola.globo.com/time/id/9459952/rodada/3/info.json](http://api.cartola.globo.com/time/id/9459952/rodada/3/info.json)

### Buscar Jogos da Rodada (Brasileirão)

Bem legal essa consulta, você consegue listar todas as informações dos jogos do brasileirão informando o número da rodada.

Rodada 1:
[http://api.cartola.globo.com/partidas/1.json](http://api.cartola.globo.com/partidas/1.json)

Rodada 2,3,etc...
[http://api.cartola.globo.com/partidas/2.json](http://api.cartola.globo.com/partidas/2.json)

....

Rodada 38
[http://api.cartola.globo.com/partidas/38.json](http://api.cartola.globo.com/partidas/38.json)


### Atletas mais pontuados da rodada atual
[http://api.cartola.globo.com/atletas/pontuados.json](http://api.cartola.globo.com/atletas/pontuados.json)

### Atletas mais escalados - TOP 10
[http://api.cartola.globo.com/atletas/top10maisescalados.json] (http://api.cartola.globo.com/atletas/top10maisescalados.json)