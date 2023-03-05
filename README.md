# FastApi_Tutorial


FastAPI è una libreria per sviluppare API com Python basata Starlette.
Il suo funzionamento è molto simile a quello di Flask per alucni aspetti,
molto diverso sotto altri.

## Sintassi base

```python

from fastapi import FastAPI

app = FastAPI()


@app.get("/")
async def root():
    return {"message": "Hello World"}
    
```

Il codice è molto familiare, vediamo un'altro esempio:

```python
from typing import Union

from fastapi import FastAPI, Query

app = FastAPI()


@app.get("/items/")
async def read_items(q: Union[str, None] = Query(default=..., min_length=3)):
    results = {"items": [{"item_id": "Foo"}, {"item_id": "Bar"}]}
    if q:
        results.update({"q": q})
    return results
```

## Vediamo gli oggetti principali del Framework


### FastAPI:
```
Questa è la classe principale che rappresenta l'applicazione API. È qui che 
definiamo le rotte dell'API e le funzioni che verranno chiamate quando una rotta viene richiesta.
```
#### Ecco alcune delle proprietà e dei metodi più importanti della classe FastAPI:

- title: Questa proprietà viene utilizzata per impostare il titolo dell'API.

- description: Questa proprietà viene utilizzata per descrivere l'API.

- version: Questa proprietà viene utilizzata per impostare la versione dell'API.

- openapi_url: Questa proprietà viene utilizzata per impostare l'URL della documentazione OpenAPI dell'API.

- docs_url: Questa proprietà viene utilizzata per impostare l'URL della documentazione dell'API.

- redoc_url: Questa proprietà viene utilizzata per impostare l'URL della documentazione ReDoc dell'API.

- routes: Questa proprietà viene utilizzata per accedere alle rotte definite nell'API.

- add_route: Questo metodo viene utilizzato per aggiungere una nuova rotta all'API.

- dependency: Questo metodo viene utilizzato per definire una dipendenza per l'API, ad esempio un database o un servizio esterno.

- include_router: Questo metodo viene utilizzato per includere un sotto-insieme di rotte nell'API.

- run: Questo metodo viene utilizzato per avviare l'API e rendere disponibile la sua documentazione e le sue rotte.




### Route:  
```
Questa è la classe che rappresenta le rotte nell'API. Una rotta è 
un percorso che un utente può richiedere, come ad esempio "/user" o "/user/{id}"
```
####Ecco alcune delle proprietà e dei metodi più importanti della classe Route:

- path: Questa proprietà viene utilizzata per impostare il percorso della rotta, ad esempio "/user/{user_id}"

- method: Questa proprietà viene utilizzata per impostare il metodo HTTP da utilizzare per la rotta, ad esempio "GET" o "POST".

- status_code: Questa proprietà viene utilizzata per impostare il codice di stato HTTP da utilizzare per una rotta.

- dependency: Questa proprietà viene utilizzata per impostare una dipendenza per la rotta come ad esempio un database o un servizio esterno.

- response_model: Questa proprietà viene utilizzata per impostare il modello di risposta da utilizzare per la rotta.

- response_model_exclude: Questa proprietà viene utilizzata per escludere alcuni campi dal modello di risposta.

- response_model_include: Questa proprietà viene utilizzata per includere solo alcuni campi nel modello di risposta.

- response_model_by_alias: Questa proprietà viene utilizzata per impostare il modello di risposta da utilizzare per la rotta utilizzando un alias.

- response_model_skip_defaults: Questa proprietà viene utilizzata per indicare se i valori predefiniti devono essere ignorati nel modello di risposta.



### Depends:
```
Questa classe viene utilizzata per gestire dipendenze, ad esempio un 
database o un servizio di autenticazione in modo da iniettarle come
dipendency injection. 
```

#### proprietà e dei metodi più importanti della classe Depends:

- callable: Questa proprietà viene utilizzata per impostare una funzione o un oggetto che restituisce un valore per la dipendenza.

- scope: Questa proprietà viene utilizzata per impostare lo scope della dipendenza, ad esempio se la dipendenza deve essere a livello di sessione o di applicazione.

- use_cache: Questa proprietà viene utilizzata per impostare se la dipendenza deve essere memorizzata in cache o no.



# Work in Progress :)

